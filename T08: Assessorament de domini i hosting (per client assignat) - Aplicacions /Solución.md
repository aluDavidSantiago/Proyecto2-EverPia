# Propuesta de Dominio y Hosting para Mercat Local Online

---

## 1. Presentación del Cliente  
**Nombre:** Mercat Local Online  
**Sector:** Marketplace local  
**Objetivo:** Plataforma de comercio electrónico comunitaria para múltiples tiendas locales, fomentando el consumo de proximidad.  

---

## 2. Análisis de Dominios  

### Criterios para el dominio:  
- Identidad local clara y fuerte.  
- SEO favorable para el mercado catalán.  
- Preferencia por TLDs: `.cat`, `.shop`, `.online`, `.com`.  

### Alternativas analizadas:  
- **mercatlocal.cat** (disponible)  
- mercatlocalonline.shop  
- mercatdeproximitat.online  
- comerçlocal.cat  

### Recomendación oficial:  
**mercatlocal.cat**  
- El dominio `.cat` está regulado por la Fundació puntCAT, destinado a proyectos relacionados con la lengua y cultura catalanas.  
- Refuerza la identidad local y mejora la confianza del usuario.  
- Adecuado para SEO local por su relevancia geográfica y cultural.  

---

## 3. Comparativa de Hosting  

| Proveedor        | Espacio          | Transferencia           | Precio/mes (IVA incl.) | Características clave                                  | Limitaciones                              |
|------------------|------------------|------------------------|-----------------------|------------------------------------------------------|-------------------------------------------|
| **Webempresa**   | 11 GB SSD        | ~50.000 visitas/mes    | 9,01 €                | Excelente soporte en español, seguridad avanzada, optimizado para WordPress y WooCommerce. | Espacio limitado para marketplace en crecimiento. Escalabilidad VPS costosa. |
| **Raiola Networks** | 15 GB SSD NVMe  | 3000 visitas/día        | 9,62 €                | Buen rendimiento, soporte en español, panel intuitivo. | Transferencia limitada, precio medio.    |
| **SiteGround**   | 20 GB SSD        | 10.000 visitas/día     | 33,86 €               | Alto rendimiento, herramientas avanzadas para WooCommerce, CDN incluido. | Renovación costosa, staging no incluido en plan básico. |
| **Dinahosting**  | 50 GB SSD        | Transferencia ilimitada | 6,59 €                | Precio competitivo, correo corporativo incluido, copias de seguridad diarias, soporte 24/7. | No especifica recursos CPU/RAM.          |

*Fuente: Información oficial de cada proveedor (consultado octubre 2025).*

---

## 4. Requisitos Técnicos Cumplidos  

- Certificado SSL incluido y renovado automáticamente.  
- Copias de seguridad diarias automáticas (Dinahosting).  
- Correo corporativo profesional y gestión DNS completa.  
- CDN integrado o posibilidad de configuración externa (Cloudflare).  
- Cumplimiento RGPD (GDPR) garantizado en todos los proveedores seleccionados.  
- Capacidad para WooCommerce y multitienda.  
- Escalabilidad futura prevista (Plan B).  

---

## 5. Recomendación Final  

**Dominio:** mercatlocal.cat  
- Ideal para reforzar la identidad local y cultural catalana.  
- Disponible y registrado mediante Fundació puntCAT.

**Hosting:** Dinahosting (plan “Hosting Profesional”)  
- Precio competitivo y transferencia ilimitada ideal para marketplace con mucho contenido.  
- Espacio suficiente (50 GB SSD) para crecimiento inicial y carga multimedia.  
- Backups y correo profesional incluidos.  
- Escalabilidad limitada, pero adecuada para comenzar.

---

## 6. Plan B Escalabilidad (para crecimiento futuro)  

**Proveedor:** Cloudways gestionado con DigitalOcean  
**Plan VPS recomendado:** 4 vCores, 8 GB RAM, 160 GB SSD (~42 €/mes)  

- Hosting WooCommerce gestionado con alta flexibilidad.  
- Escalabilidad vertical y horizontal con un clic.  
- Cumplimiento total RGPD, backups automáticos, CDN integrado.  
- Mejor soporte para alta concurrencia y rendimiento de multitienda.  

---

## 7. Coste Total Estimado  

| Concepto             | Precio anual (€)         |
|----------------------|-------------------------|
| Hosting Dinahosting   | 6,59 € × 12 = 79,08 €   |
| Dominio mercatlocal.cat | 6,05 €                |
| **Total anual estimado** | **~85,03€**           |

---

## 8. Entorno de Pruebas  

- Crear cuenta en Dinahosting.  
- Instalar WordPress y WooCommerce.  
- Configurar subdominio temporal: mercatlocal.dinahosting.com  
- Probar funcionalidades clave: gestión de múltiples tiendas, roles de usuario, campañas, redes sociales.  
- Realizar pruebas básicas de carga y rendimiento.  
- Documentar todo con capturas para repositorio GitHub.  

---

## 9. Evidencias para el Repositorio GitHub  

- Captura de disponibilidad del dominio.

<img src="com-hp-pro-sff-400-g9-product-image.png" alt="Disponibilidad de hosting y precio" width="300" height="auto">
- Panel de control del hosting elegido.  
- Instalación inicial WordPress + WooCommerce.  
- Plan de hosting y detalle de servicios incluidos.  
- URL del entorno de pruebas activo.  
- Cálculo y desglose de coste anual.  

---

## 10. Conclusiones  

- La opción Dinahosting con dominio .cat es óptima para comenzar un marketplace local, por su equilibrio entre coste, recursos y soporte.  
- El dominio `.cat` aporta identidad y mejora la confianza y SEO local.  
- Cloudways con DigitalOcean es una alternativa sólida para crecimiento y alta demanda.  
- Cumplimiento RGPD y servicios asociados (correo, backups, DNS) están garantizados.  
- Se recomienda monitorizar rendimiento y carga para plantear migración futura en caso de escalabilidad.  

---

