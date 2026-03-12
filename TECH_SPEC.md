# FiskalApp
### Gestión fiscal inteligente para personas físicas en México
> **Tech Spec & Vision Document — v1.0 | Marzo 2026**

| Campo | Detalle |
|---|---|
| Tipo de documento | Especificación Técnica y Propuesta de Valor |
| Audiencia | Inversionistas y Stakeholders |
| Estado | Borrador — Versión inicial |
| Mercado objetivo | México — Personas Físicas con actividad empresarial |
| Plataforma | iOS & Android (aplicación móvil) |

---

## Tabla de Contenidos

1. [Resumen Ejecutivo](#1-resumen-ejecutivo)
2. [Descripción del Problema](#2-descripción-del-problema)
3. [Usuarios Objetivo](#3-usuarios-objetivo)
4. [Funcionalidades Principales](#4-funcionalidades-principales)
5. [Flujos de Usuario](#5-flujos-de-usuario-principales)
6. [Arquitectura Técnica](#6-arquitectura-técnica)
7. [Modelo de Negocio](#7-modelo-de-negocio)
8. [Roadmap de Desarrollo](#8-roadmap-de-desarrollo)
9. [Próximos Pasos](#9-próximos-pasos)
10. [SRS — Módulo de Onboarding](SRS_ONBOARDING.md)

---

## 1. Resumen Ejecutivo

FiskalApp es una aplicación móvil diseñada para empoderar a personas físicas —comerciantes, contratistas, profesionistas independientes y freelancers— en México para gestionar su contabilidad fiscal de forma autónoma, sin depender de un contador externo.

La aplicación traduce la complejidad del sistema tributario mexicano (SAT) a un lenguaje claro y accesible, automatiza los procesos más repetitivos y reduce drásticamente la posibilidad de errores en la declaración de impuestos.

> **El 65% de los contribuyentes personas físicas en México admite no entender completamente sus obligaciones fiscales.** FiskalApp resuelve este problema directamente con tecnología accesible, guías interactivas y automatización inteligente.

---

## 2. Descripción del Problema

Las personas físicas con actividad económica formal en México enfrentan una carga cognitiva alta al intentar cumplir con sus obligaciones fiscales. Este problema tiene tres dimensiones:

### Complejidad del sistema tributario
- Jerga técnica especializada difícil de interpretar sin formación contable.
- Múltiples regímenes fiscales (RESICO, RIF, Actividad Empresarial) con reglas distintas.
- Cambios frecuentes en las disposiciones del SAT que generan incertidumbre.
- Procesos de facturación con pasos técnicos que inducen errores fácilmente.

### Dependencia costosa de intermediarios
- Un contador externo puede costar entre $500 y $3,000 MXN mensuales para una persona física.
- La relación con un contador genera una dependencia que limita la autonomía del contribuyente.
- No todos los contribuyentes tienen acceso geográfico o económico a servicios contables de calidad.

### Consecuencias del incumplimiento
- Multas y recargos del SAT por declaraciones tardías o incorrectas.
- Cancelación de sellos digitales que imposibilita facturar.
- Acumulación de adeudos fiscales por desconocimiento de deducciones aplicables.

---

## 3. Usuarios Objetivo

FiskalApp está diseñada para tres perfiles principales de usuarios, todos bajo el esquema de personas físicas con actividad económica registrada ante el SAT.

### 👩‍💻 Ximena, 32 años
**Diseñadora freelance — Régimen de Actividades Empresariales**

| Necesidades | Puntos de dolor |
|---|---|
| Emitir facturas fácilmente a sus clientes | No entiende la diferencia entre IVA trasladado e IVA acreditable |
| Saber cuánto apartar de ingresos para el SAT | Ha pagado multas por cancelar facturas incorrectamente |
| Recordatorios de sus fechas de declaración | Su contador cobra $1,500/mes y apenas la orienta |
| Historial claro de sus gastos deducibles | — |

### 🛒 Don Roberto, 55 años
**Comerciante de abarrotes — RESICO**

| Necesidades | Puntos de dolor |
|---|---|
| Entender qué tiene que pagar bimestralmente | Tecnología con curva de aprendizaje alta |
| No cometer errores al momento de declarar | Confunde el CFDI de ingresos con el de egresos |
| Acceso rápido al portal del SAT desde su celular | Tiene miedo de hacer algo mal y recibir una auditoría |

### 💻 Sofía, 28 años
**Desarrolladora de software independiente — Honorarios**

| Necesidades | Puntos de dolor |
|---|---|
| Automatizar el cálculo de su ISR mensual | El portal del SAT es lento y confuso en móvil |
| Integración directa con el portal del SAT | No sabe qué gastos puede deducir legalmente |
| App que le ahorre tiempo sin sacrificar control | Ha tenido inconsistencias entre sus facturas y las de su cliente |

---

## 4. Funcionalidades Principales

### 4.1 Balance Fiscal
Vista centralizada del estado financiero del usuario en el período actual, con desglose bimestral según el régimen fiscal aplicable.

- Resumen de ingresos, gastos y balance neto del período.
- Listado de facturas que componen el balance (emitidas y recibidas).
- Filtros por tipo: ingresos, egresos, nómina, complementos.
- Indicador visual del impuesto estimado a pagar en la próxima declaración.

### 4.2 Gestión de Facturas (CFDI)
Herramientas completas para emitir, descargar, cancelar y organizar facturas digitales.

- Emisión de facturas mediante integración con Facturama (PAC certificado).
- Descarga automática de CFDIs desde el portal del SAT.
- Wizard paso a paso para cancelación de facturas con selección de motivo.
- Almacenamiento seguro en la nube con búsqueda y filtros avanzados.

### 4.3 Acceso Simplificado al SAT
Navegador interno integrado que captura sesiones del portal del SAT para reducir fricción.

- Accesos directos a: declaración mensual, buzón tributario, catálogo de conceptos.
- Notificaciones sobre mensajes nuevos en el buzón tributario.
- Precarga automática de datos para agilizar formularios del SAT.

### 4.4 Recordatorios y Obligaciones
Sistema de alertas personalizado según el régimen fiscal del usuario.

- Recordatorios de fechas límite de declaración (mensual, bimestral, anual).
- Notificaciones para obligaciones extraordinarias (declaración anual, DIOT).
- Historial de cumplimiento de obligaciones anteriores.

### 4.5 Lenguaje Accesible e Inteligencia Fiscal
Motor de traducción de términos fiscales a lenguaje cotidiano.

- Glosario fiscal interactivo con definiciones en lenguaje simple.
- Asistente que explica cada concepto al momento de realizar una acción.
- Sugerencias de gastos deducibles según el giro del usuario.

---

## 5. Flujos de Usuario Principales

### 5.1 Onboarding — Primera vez en la app
El proceso de incorporación está diseñado para completarse en menos de 5 minutos:

1. Registro con número de teléfono o email.
2. Ingreso de RFC y vinculación con el SAT (FIEL o contraseña).
3. Selección o detección automática del régimen fiscal.
4. Importación inicial de facturas históricas del SAT.
5. Presentación del dashboard personalizado con el balance actual.

### 5.2 Emisión de Factura
1. Usuario selecciona "Nueva Factura" desde el dashboard.
2. Wizard de 4 pasos: cliente → concepto → importe + IVA → revisión.
3. Validación automática de RFC del receptor y régimen fiscal.
4. Emisión vía Facturama y confirmación con descarga del PDF y XML.
5. La factura aparece automáticamente en el balance del período.

### 5.3 Preparación de Declaración Bimestral
1. La app consolida ingresos y gastos del bimestre de forma automática.
2. Muestra un resumen del ISR e IVA estimado en lenguaje simple.
3. Ofrece botón directo al módulo de declaración del SAT con datos prellenados.
4. Registro del cumplimiento en el historial de obligaciones del usuario.

### 5.4 Consulta de Balance
1. Vista principal del dashboard con totales del período actual.
2. Gráfica de ingresos vs. gastos por mes.
3. Detalle de cada factura con opción de descargar PDF o XML.
4. Filtros por rango de fecha, tipo de comprobante y estatus (vigente/cancelado).

---

## 6. Arquitectura Técnica

### 6.1 Stack de Tecnologías

| Componente | Tecnología / Decisión |
|---|---|
| Frontend móvil | React Native (iOS y Android desde un solo código base) |
| Backend / API | Java 21 + Spring Boot 3 — API RESTful robusta y tipada estáticamente |
| Seguridad | Spring Security — autenticación, autorización y manejo seguro de credenciales SAT |
| Procesamiento batch | Spring Batch — descarga masiva y procesamiento de CFDIs del SAT |
| Base de datos | PostgreSQL (datos transaccionales) + Redis (caché de sesiones y tokens) |
| Almacenamiento | AWS S3 — XMLs y PDFs de CFDI cifrados en reposo |
| Autenticación | OAuth 2.0 + JWT con Spring Security — sesión segura con el SAT |
| Facturación CFDI | Facturama API (PAC certificado ante el SAT) |
| Notificaciones | Firebase Cloud Messaging (FCM) |
| Infraestructura | AWS (ECS + RDS) con contenedores Docker |

### 6.2 Por qué Java / Spring Boot

La elección de Java 21 con Spring Boot 3 responde a las exigencias específicas del dominio fiscal:

- **Tipado estático:** reduce errores en runtime al procesar transacciones financieras y XMLs de CFDI donde la consistencia de datos es crítica.
- **Spring Security:** uno de los frameworks de seguridad más maduros del ecosistema, esencial para el manejo cifrado de credenciales del SAT.
- **Spring Batch:** diseñado para procesamiento de grandes volúmenes de datos, ideal para la descarga y conciliación masiva de facturas desde el portal del SAT.
- **Ecosistema maduro de XML:** librerías robustas para parsear, validar y generar CFDI 4.0 con namespaces del SAT.
- **Escalabilidad probada:** la arquitectura soporta el crecimiento proyectado a 150,000 usuarios sin cambios estructurales.

### 6.3 Integraciones Externas
- **SAT (portal.sat.gob.mx):** Descarga de CFDIs, validación de RFC, declaraciones.
- **Facturama:** Emisión y cancelación de facturas CFDI 4.0.
- **Firebase:** Notificaciones push en tiempo real.
- **AWS S3:** Almacenamiento encriptado de archivos fiscales del usuario.

### 6.4 Seguridad y Cumplimiento
- Cifrado en tránsito: TLS 1.3 en todas las comunicaciones.
- Cifrado en reposo: AES-256 para credenciales del SAT almacenadas.
- Las credenciales del SAT nunca se almacenan en texto plano.
- Cumplimiento con la Ley Federal de Protección de Datos Personales (LFPDPPP).
- Autenticación biométrica opcional (Face ID / huella digital).

---

## 7. Modelo de Negocio

### 7.1 Estrategia de Monetización

Modelo freemium con suscripción mensual/anual:

| Plan | Descripción |
|---|---|
| **Gratuito** | Hasta 5 facturas/mes, balance básico, recordatorios. Sin costo. |
| **Pro — $149 MXN/mes** | Facturas ilimitadas, balance detallado, navegador SAT integrado, soporte prioritario. |
| **Pro Anual — $1,299 MXN/año** | Todos los beneficios Pro con 27% de descuento vs. pago mensual. |
| **Empresas (B2B)** | Licencia por asiento para despachos contables que gestionen múltiples clientes. |

### 7.2 Proyección de Mercado

México cuenta con más de 12.5 millones de personas físicas registradas ante el SAT con actividad económica. El segmento objetivo inicial representa aproximadamente 4.2 millones de personas.

- Penetración objetivo año 1: 0.5% del mercado = ~21,000 usuarios activos.
- Conversión estimada a plan Pro: 20% = ~4,200 suscriptores de pago.
- ARR estimado año 1: ~$7.5 millones MXN (~$375K USD).
- Año 3 — objetivo: 150,000 usuarios activos, 30,000 suscriptores Pro.

### 7.3 Ventajas Competitivas
- Enfoque exclusivo en personas físicas, no en grandes empresas.
- UX simplificada con lenguaje no técnico — diferenciador clave vs. competidores.
- Integración directa con el SAT y con un PAC certificado (Facturama).
- Modelo de precios accesible frente al costo de un contador externo.

---

## 8. Roadmap de Desarrollo

| Fase | Alcance y entregables |
|---|---|
| **Fase 1 — MVP (Q2 2026)** | Onboarding, balance fiscal básico, descarga de CFDIs del SAT, recordatorios de obligaciones, visualización de ingresos y gastos. |
| **Fase 2 — Emisión (Q3 2026)** | Integración con Facturama para emitir y cancelar facturas, wizard de facturación, navegador SAT integrado. |
| **Fase 3 — Inteligencia (Q4 2026)** | Asistente de lenguaje accesible, sugerencias de deducibles, preparación automática de declaración bimestral, plan Pro. |
| **Fase 4 — Escala (Q1 2027)** | Módulo B2B para despachos, declaración anual asistida, expansión de integraciones bancarias. |

---

## 9. Próximos Pasos

- **Prototipo en Figma:** Diseño de los flujos principales del MVP (onboarding, balance, recordatorios) y validación interna de usabilidad con el equipo antes de escribir una sola línea de código.
- **Definición del equipo técnico:** Contratación o asignación de 1 desarrollador backend, 1 frontend/mobile y 1 diseñador UX.
- **Acuerdo con Facturama:** Gestión del convenio con el PAC para integración de facturación CFDI 4.0.
- **Constitución legal:** Apertura de persona moral y trámites ante el SAT para operar como proveedor de servicios digitales.

---

## 10. SRS — Módulo de Onboarding

La especificación detallada de requerimientos del módulo de onboarding se encuentra en un documento dedicado para facilitar su lectura y extensión futura:

**[SRS_ONBOARDING.md](SRS_ONBOARDING.md)**

Incluye: casos de uso, requerimientos funcionales y no funcionales, endpoints REST, reglas de negocio, manejo de errores y diagramas de flujo del cliente y servidor.

---

*Documento confidencial — Uso exclusivo para inversionistas y stakeholders. FiskalApp © 2026*