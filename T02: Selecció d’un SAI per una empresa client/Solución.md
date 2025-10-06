# Propuesta de dominio y hosting para el cliente Mercat Local Online

## 1. Presentación del cliente

- **Nombre del cliente**: Mercat Local Online  
- **Sector**: Marketplace local  
- **Objetivo del sitio web**: Crear una plataforma de comercio electrónico comunitaria con múltiples tiendas locales, fomentando el consumo de proximidad.  
- **Funcionalidades clave**:
  - Catálogo multitienda con gestión individual por comercio
  - Acceso multiusuario con roles diferenciados
  - Integración optimizada con WooCommerce
  - Espacio para campañas comerciales locales
  - Integración con redes sociales (Facebook e Instagram)
- **Requisitos técnicos identificados**:
  - Escalabilidad mediante VPS o Cloud
  - Capacidad para 10.000 usuarios
  - Hosting con 4 vCores
  - Cumplimiento RGPD
  - Correo corporativo y gestión DNS

## 2. Análisis de dominios

- **Criterios para el nombre**:
  - Identidad clara y local
  - Buena indexación SEO
  - Preferencia por TLDs como .cat, .shop, .online o .com

- **Alternativas de dominios disponibles**:
  - mercatlocal.cat
  - mercatlocalonline.shop
  - mercatdeproximitat.online
  - comerçlocal.cat

- **Dominio recomendado**:  
  `mercatlocal.cat` por su claridad, identidad catalana e impacto local.  
  *Nota*: El dominio `.cat` está disponible para proyectos relacionados con la cultura catalana, como este.

## 3. Comparativa de hostings

| Proveedor        | Espacio en disco | Transferencia         | Precio mensual | Ventajas                                        | Desventajas                              |
|------------------|------------------|------------------------|----------------|------------------------------------------------|-------------------------------------------|
| Webempresa       | 11 GB SSD        | ~50.000 visitas        | 9,01 €         | Buen soporte, velocidad, seguridad             | Espacio limitado, escalabilidad costosa   |
| Raiola Networks  | 15 GB SSD NVMe   | 3000 visitas/día       | 9,62 €         | Flexibilidad, buen rendimiento, soporte técnico| Transferencia limitada, precio medio      |
| SiteGround       | 20 GB SSD        | 50 usuarios simultáneos| 33,86 €        | Alto rendimiento, herramientas avanzadas       | Renovación cara, sin staging en plan básico|
| Dinahosting      | 50 GB            | Ilimitada              | 6,59 €         | Precio bajo, mucho espacio, transferencia ilimitada | No especifica RAM ni CPU             |

## 4. Checklist de requisitos cumplidos

- [x] SSL incluido  
- [x] Copias de seguridad automáticas  
- [x] Correo corporativo  
- [x] CDN integrado  
- [x] Cumplimiento RGPD  
- [x] Gestión DNS  

## 5. Recomendación final

- **Hosting elegido**: Dinahosting  
- **Dominio recomendado**: mercatlocal.cat  

**Justificación de la decisión**:  
Dinahosting ofrece un buen equilibrio entre precio, espacio y transferencia ilimitada. El dominio `.cat` refuerza la identidad local y comunitaria del proyecto. El entorno es escalable y compatible con WooCommerce, ideal para un marketplace multitienda.

## 6. Plan B de escalabilidad

- **Proveedor alternativo**: Cloudways (con DigitalOcean)  
- **Plan VPS recomendado**: 4 vCores, 8 GB RAM, 160 GB SSD (~42 €/mes)  
- **Ventajas**:
  - Escalabilidad vertical con un clic
  - Hosting WooCommerce gestionado
  - Cumplimiento RGPD
  - Copias de seguridad, CDN, correo corporativo

## 7. Coste total estimado

- Hosting Dinahosting: 6,59 €/mes × 12 = **79,08 €/año**  
- Dominio `.cat`: ~12 €/año  
- **Total anual estimado**: **91,08 €**

## 8. Entorno de pruebas

- **Estado**: pendiente de creación  
- **Acciones recomendadas**:
  - Crear cuenta gratuita en Dinahosting
  - Instalar WordPress + WooCommerce
  - Activar subdominio temporal (ej: mercatlocal.dinahosting.com)
  - Documentar con capturas

## 9. Evidencias para el repositorio GitHub

Listado de capturas a incluir:

1. Comprobación de disponibilidad del dominio
2. Panel de control del hosting elegido
3. Configuración inicial de WordPress + WooCommerce
4. Plan de hosting con precio mensual
5. Checklist de servicios incluidos
6. Entorno de pruebas activo (URL temporal)
7. Cálculo de coste total anual

## 10. Conclusiones

- **Criterios decisivos**:
  - Compatibilidad con WooCommerce
  - Escalabilidad VPS
  - Transferencia ilimitada
  - Precio competitivo
  - Identidad local con dominio `.cat`

- **Valor añadido**:
  - Cumplimiento RGPD
  - Correo corporativo y gestión DNS
  - Posibilidad de migración a Cloudways si el proyecto crece

> Esta propuesta garantiza un buen rendimiento, una imagen profesional y capacidad de crecimiento para el cliente Mercat Local Online.
