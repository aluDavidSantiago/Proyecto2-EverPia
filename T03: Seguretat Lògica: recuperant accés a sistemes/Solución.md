# Paso 1: Acceder al menú GRUB

## Introducción  
En este paso interrumpiremos el proceso de arranque de la máquina virtual para mostrar el menú de GRUB. Esto permite editar las opciones de arranque y preparar la recuperación o modificación del sistema.

## Pasos detallados

1. Arranca o reinicia la máquina virtual que contiene el disco clonado.
2. Durante el arranque, cuando aparezca la primera información en pantalla (como el logo del firmware o una pantalla negra previa al inicio del sistema), pulsa repetidamente la tecla `Esc` para interrumpir el arranque automático.
3. Si el menú de GRUB no aparece, reinicia la máquina virtual y vuelve a intentarlo pulsando `Esc` varias veces.
4. En caso de que `Esc` no funcione, prueba con las teclas `Shift` o `F12`, que en algunas configuraciones activan el menú GRUB.
5. Verifica que la ventana de la máquina virtual tenga el foco para que las pulsaciones de teclado se registren correctamente.
6. Una vez visible el menú de GRUB, selecciona la entrada de arranque correspondiente para continuar con la edición (paso siguiente).

## Notas importantes

- **OJO:** Asegúrate de contar con autorización expresa para realizar estas acciones, ya que afectan la configuración del sistema.
- Algunos sistemas con arranque en modo UEFI y "fast boot" pueden omitir el menú GRUB; en ese caso, será necesario desactivar estas opciones desde el firmware de la máquina virtual.
- Mantén el disco clonado en modo solo lectura para evitar modificaciones accidentales del original.
- La tecla para acceder al menú GRUB puede variar según la distribución y configuración del sistema.
