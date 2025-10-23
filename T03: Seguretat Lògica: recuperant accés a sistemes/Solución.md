# Guía Técnica: Configuración de Máquina Virtual y Protección del GRUB

---

## 📘 Índice

1. [Creación de la máquina virtual](#1-creación-de-la-máquina-virtual)  
2. [Acceder al menú GRUB y establecer la raíz en la partición correcta](#2-acceder-al-menú-grub-y-establecer-la-raíz-en-la-partición-correcta)  
3. [Cargar el kernel Linux desde GRUB con parámetros específicos](#3-cargar-el-kernel-linux-desde-grub-con-parámetros-específicos)  
4. [Cargar la imagen initrd y arrancar el sistema](#4-cargar-la-imagen-initrd-y-arrancar-el-sistema)  
5. [Ver usuarios con directorio en home y cambiar la contraseña](#5-ver-usuarios-con-directorio-en-home-y-cambiar-la-contraseña)  
6. [Cambiar la contraseña de un usuario desde el shell de recuperación](#6-cambiar-la-contraseña-de-un-usuario-desde-el-shell-de-recuperación)  
7. [Reiniciar el sistema desde el shell de recuperación](#7-reiniciar-el-sistema-desde-el-shell-de-recuperación)  
8. [Iniciar sesión con la nueva contraseña](#8-iniciar-sesión-con-la-nueva-contraseña)  
9. [Generar hash PBKDF2 para GRUB](#9-generar-hash-pbkdf2-para-grub)  
10. [Editar el archivo 40_custom](#10-editar-el-archivo-40_custom)  
11. [Establecer contraseña para el usuario root](#11-establecer-contraseña-para-el-usuario-root)  
12. [Verificar acceso al usuario root con su](#12-verificar-acceso-al-usuario-root-con-su)  
13. [Actualizar GRUB para aplicar los cambios](#13-actualizar-grub-para-aplicar-los-cambios)  
14. [Verificar protección de GRUB tras reinicio](#14-verificar-protección-de-grub-tras-reinicio)  
15. [Autenticarse en GRUB](#15-autenticarse-en-grub)  
16. [Modificar 10_linux para añadir o quitar --unrestricted](#16-modificar-10_linux-para-añadir-o-quitar---unrestricted)  
17. [Verificar autenticación solo en accesos intencionados](#17-verificar-autenticación-solo-en-accesos-intencionados)  
18. [Notas finales](#18-notas-finales)

---

## 1. Creación de la máquina virtual

Configuraremos una máquina virtual con los recursos necesarios y un disco existente con una imagen ISO previamente preparada, para realizar prácticas de recuperación de contraseñas y protección del GRUB.

<img src="img/confi1.png" alt="Ordenador HP" width="400" height="auto">  
<img src="img/confi2.png" alt="Ordenador HP" width="400" height="auto">

**Pasos detallados:**
- Crea una nueva máquina virtual con:
  - 8 GB de memoria RAM  
  - 2 procesadores  
- En el apartado **Hard Disk**, selecciona:  
  *Use an existing virtual hard disk file*  
- Elige el disco que contiene la ISO previamente creada (en este caso estará en la comuna).  
- Guarda la configuración y arranca la máquina.

---

## 2. Acceder al menú GRUB y establecer la raíz en la partición correcta

En este paso se accederá al menú GRUB presionando la tecla **Esc** durante el arranque y se configurará la partición raíz en GRUB.

**Pasos detallados:**
- Inicia o reinicia la máquina virtual.  
- Presiona repetidamente la tecla **Esc** durante el arranque para acceder al menú GRUB.  
- En el prompt de GRUB (`grub_es>`), ejecuta:
  
```
set root=(hd0,gpt3)

```

<img src="img/1.png" alt="Ordenador HP" width="400" height="auto"> 

Este comando indica a GRUB que la raíz está en el primer disco (hd0), tercera partición GPT (gpt3).

⚠️ **Nota:** La nomenclatura `(hd0,gpt3)` puede variar. Asegúrate de usar la partición correcta.

---

## 3. Cargar el kernel Linux desde GRUB con parámetros específicos

Ejecuta:

```
linux /boot/vmlinuz-6.8.0-52-generic root=/dev/sda3 rw init=/bin/bash

```

<img src="img/2.png" alt="Ordenador HP" width="500" height="auto"> 

**Explicación:**
- `linux`: indica a GRUB que cargue el kernel.  
- `/boot/vmlinuz-6.8.0-52-generic`: ruta al kernel.  
- `root=/dev/sda3`: define la partición raíz.  
- `rw`: monta el sistema con permisos de escritura.  
- `init=/bin/bash`: abre un shell Bash como proceso principal.

⚠️ **Nota:** Usa la versión correcta del kernel instalada en el sistema.

---

## 4. Cargar la imagen initrd y arrancar el sistema

Ejecuta:

```
initrd /boot/initrd.img-6.8.0-52-generic

```

<img src="img/3.png" alt="Ordenador HP" width="500" height="auto"> 

Luego:

```
boot

```

⚠️ **Nota:** La versión de la imagen initrd debe coincidir con la del kernel cargado.

---

## 5. Ver usuarios con directorio en /home y cambiar la contraseña

Ejecuta:

```
cat /etc/passwd | grep /home

```

<img src="img/4.png" alt="Ordenador HP" width="600" height="auto"> 

Luego:

```
passwd miquel

```

⚠️ **Nota:** Si el sistema está en solo lectura, remonta la raíz con permisos de escritura antes de ejecutar `passwd`.

---

## 6. Cambiar la contraseña de un usuario desde el shell de recuperación

Ejecuta:

```
passwd miquel

```

<img src="img/5.png" alt="Ordenador HP" width="400" height="auto"> 

Mensaje esperado:

```
passwd: password updated successfully

```

⚠️ **Nota:** Asegúrate de que el sistema de archivos raíz esté montado con permisos de escritura.

---

## 7. Reiniciar el sistema desde el shell de recuperación

Ejecuta:

```
exit

```

<img src="img/6.png" alt="Ordenador HP" width="500" height="auto"> 

⚠️ **Nota:** Si el sistema no se reinicia automáticamente, hazlo desde VirtualBox manualmente.

---

## 8. Iniciar sesión con la nueva contraseña

Después de reiniciar, inicia sesión con la nueva contraseña.

<img src="img/inicio.png" alt="Ordenador HP" width="400" height="auto"> 

**Pasos:**
- Espera la pantalla de inicio de sesión.  
- Selecciona el usuario (por ejemplo, *Miquel Valls*).  
- Introduce la nueva contraseña.  

⚠️ **Nota:** Verifica que *Bloq Mayús* esté desactivado.

---

## 9. Generar hash PBKDF2 para GRUB

Ejecuta:

```
grub-mkpasswd-pbkdf2

```

<img src="img/9.png" alt="Ordenador HP" width="400" height="auto"> 

Copia el hash generado.

⚠️ **Nota:** Guarda este hash; será necesario más adelante.

---

## 10. Editar el archivo 40_custom

Abre:
```
sudo nano /etc/grub.d/40_custom

```

<img src="img/10.png" alt="Ordenador HP" width="400" height="auto"> 

Agrega:
```
set superusers="miquel,root"`
password_pbkdf2 miquel grub.pbkdf2.sha512.10000.01B0F9BFED3D69C8C29750B17590BAB7... (hash contraseña miquel)
password_pbkdf2 root grub.pbkdf2.sha512.10000.83F0FFABC8F9F01098FB80DF5EB093B0A... (hash contraseña root)

```

<img src="img/11.png" alt="Ordenador HP" width="400" height="auto"> 

Guarda con **Ctrl + O**, sal con **Ctrl + X**.

⚠️ **Nota:** Asegúrate de que no haya errores de sintaxis.

---

## 11. Establecer contraseña para el usuario root

Verifica:

```
sudo passwd -S root

```
Desbloquea:

```
sudo passwd -u root

```
Asigna:

```
sudo passwd root

```

<img src="img/12.png" alt="Ordenador HP" width="400" height="auto"> 

⚠️ **Nota:** Usa esta contraseña solo para administración avanzada.

---

## 12. Verificar acceso al usuario root con su

Ejecuta:

```
su

```

<img src="img/13.png" alt="Ordenador HP" width="400" height="auto"> 

Si el prompt cambia a `root@equipo:~#`, el acceso fue exitoso.

---

## 13. Actualizar GRUB para aplicar los cambios

Ejecuta:

```
sudo update-grub

```

<img src="img/16.png" alt="Ordenador HP" width="400" height="auto"> 

Salida esperada:

```
Generating grub configuration file ...
done

```

⚠️ **Nota:** Este paso es obligatorio tras cualquier cambio en GRUB.

---

## 14. Verificar protección de GRUB tras reinicio

Reinicia:
```

sudo reboot

```

GRUB pedirá usuario y contraseña.  
Introduce `miquel` o `root`.

⚠️ **Nota:** Si no aparece el menú, presiona **Esc** durante el arranque.

---

## 15. Autenticarse en GRUB

En la autenticación:

`Enter username: miquel`

Introduce la contraseña configurada.  

<img src="img/18.png" alt="Ordenador HP" width="400" height="auto"> 

⚠️ **Nota:** Si fallas, no podrás continuar con el arranque.

---

## 16. Modificar 10_linux para añadir o quitar --unrestricted

Abre:

`sudo nano /etc/grub.d/10_linux`

Cambia:
```
echo "menuentry '$(echo "$title" | grub_quote)' ${CLASS} >

```
Por:
```

echo "menuentry '$(echo "$title" | grub_quote)' ${CLASS} --unrestricted >

```

<img src="img/21.png" alt="Ordenador HP" width="400" height="auto"> 

Guarda y ejecuta:
```

sudo update-grub

```

⚠️ **Nota:** `--unrestricted` permite arrancar sin autenticación esas entradas.

---

## 17. Verificar autenticación solo en accesos intencionados

Reinicia:
```

sudo reboot

```

<img src="img/22.png" alt="Ordenador HP" width="400" height="auto"> 

El sistema arrancará directamente sin pedir contraseña.  

<img src="img/23.png" alt="Ordenador HP" width="400" height="auto"> 

Para acceder al menú protegido, presiona **Shift** o **Esc**.  

<img src="img/24.png" alt="Ordenador HP" width="600" height="auto"> 

⚠️ **Nota:** El sistema arrancará normalmente, pero el menú avanzado seguirá protegido.

---

## 18. Notas finales

✅ El sistema arrancará sin pedir contraseña, pero si intentas acceder al modo de recuperación o edición del GRUB, se solicitará autenticación.  

⚠️ **Advertencia:**
- Manipular GRUB o el acceso root debe hacerse con precaución.  
- Realiza copias de seguridad antes de modificar archivos críticos.  
- Estas configuraciones están destinadas a personal técnico o administradores.

📝 **Fuentes:**
- [YouTube: uVGcgudLTl0](https://youtu.be/uVGcgudLTl0?si=xhJET3GmH53PvVsd)  
- [SoloConLinux: securizando-grub](https://soloconlinux.org.es/securizando-grub/)
```

