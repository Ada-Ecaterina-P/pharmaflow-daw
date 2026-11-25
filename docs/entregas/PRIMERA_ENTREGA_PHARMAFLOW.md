<div style="text-align: center; margin-top: 80px;">

# PHARMAFLOW
### Sistema Web Integral de Gestión de Stock, Fidelización de Clientes (CRM), Integración CIMA y Asistencia IA para Oficina de Farmacia

<br><br>

**Proyecto Intermodular – Ciclo Formativo de Grado Superior en Desarrollo de Aplicaciones Web (DAW)**

<br><br><br>

| Datos del Proyecto | |
| :--- | :--- |
| **Centro Educativo** | CESUR – Formación Profesional |
| **Alumna** | Andrada Ecaterina Petrovici |
| **Tutor del Proyecto** | Gonzalo Pérez Crespo |
| **Entrega** | Primera Entrega — Análisis y Planteamiento del Proyecto |
| **Fecha** | Diciembre 2026 |

</div>

<div style="page-break-after: always;"></div>

## Índice de Contenidos

<!-- Con la extensión "Markdown All in One" en VS Code, pulsa Cmd+Shift+P y ejecuta: "Markdown All in One: Create Table of Contents" aquí debajo -->

- [PHARMAFLOW](#pharmaflow)
    - [Sistema Web Integral de Gestión de Stock, Fidelización de Clientes (CRM), Integración CIMA y Asistencia IA para Oficina de Farmacia](#sistema-web-integral-de-gestión-de-stock-fidelización-de-clientes-crm-integración-cima-y-asistencia-ia-para-oficina-de-farmacia)
  - [Índice de Contenidos](#índice-de-contenidos)
  - [1. Resumen o Introducción](#1-resumen-o-introducción)
    - [1.1. Presentación del proyecto y finalidad](#11-presentación-del-proyecto-y-finalidad)
    - [1.2. Justificación de la elección del tema](#12-justificación-de-la-elección-del-tema)
    - [1.3. Descripción general del sistema](#13-descripción-general-del-sistema)
  - [Punto de Venta (POS Web) y Dashboard Analítico: Interfaz ágil de caja registradora web con aplicación automática de descuentos según el cliente seleccionado, y un panel de dirección con gráficos de facturación diaria, productos más vendidos y balance global de deudas.](#punto-de-venta-pos-web-y-dashboard-analítico-interfaz-ágil-de-caja-registradora-web-con-aplicación-automática-de-descuentos-según-el-cliente-seleccionado-y-un-panel-de-dirección-con-gráficos-de-facturación-diaria-productos-más-vendidos-y-balance-global-de-deudas)
  - [2. Planteamiento del Problema o Necesidad](#2-planteamiento-del-problema-o-necesidad)
    - [2.1. Situación o contexto actual](#21-situación-o-contexto-actual)
    - [2.2. Problema o necesidad detectada](#22-problema-o-necesidad-detectada)
    - [2.3. Público objetivo o usuarios finales](#23-público-objetivo-o-usuarios-finales)
  - [3. Objetivos del Proyecto](#3-objetivos-del-proyecto)
    - [3.1. Objetivo general](#31-objetivo-general)
    - [3.2. Objetivos específicos](#32-objetivos-específicos)

<div style="page-break-after: always;"></div>

## 1. Resumen o Introducción

### 1.1. Presentación del proyecto y finalidad
<!-- TU TURNO: Presenta PharmaFlow en 1 o 2 párrafos claros. Explica qué es (una aplicación web SaaS) y cuál es su finalidad principal dentro de una oficina de farmacia. -->
PharmaFlow es una plataforma web SaaS (Software as a Service) integral, diseñada específicamente para optimizar la gestión operativa, comercial, clínica y de inventario en una oficina de farmacia comunitaria.
A diferencia de los programas de gestión (ERP) tradicionales de escritorio —instalados en servidores locales cerrados y con interfaces obsoletas—, PharmaFlow se plantea como una solución web moderna, accesible y escalable. Su finalidad principal es centralizar en un único entorno la administración de existencias con trazabilidad por lotes y caducidades, la fidelización personalizada de pacientes/clientes, el control de compras y albaranes por roles de empleado y la consulta oficial de medicamentos en tiempo real.


### 1.2. Justificación de la elección del tema
<!-- TU TURNO: Explica por qué has elegido este tema:
  - Interés personal/profesional y necesidad real de digitalización en farmacias de barrio.
  - Cómo conecta con todo lo aprendido en DAW (Frontend reactivo, Backend seguro con roles, Base de datos relacional y APIs externas). -->
La elección de desarrollar un sistema integral para oficinas de farmacia responde a una doble motivación, tanto profesional como académica:
Necesidad real de modernización en el sector farmacéutico: Las farmacias de barrio gestionan diariamente un volumen elevado de referencias sanitarias críticas, recetas pendientes y clientes habituales que requieren una atención ágil y personalizada. Sin embargo, muchas siguen dependiendo de herramientas heredadas poco intuitivas, registros manuales para encargos o "fianzas" y consultas lentas de prospectos extensos en PDF.
Integración completa de las competencias de 2º DAW: Desde el punto de vista técnico, PharmaFlow reúne de forma natural todos los pilares del ciclo de Desarrollo de Aplicaciones Web: diseño de una interfaz SPA rápida y accesible (Frontend), desarrollo de una API REST desacoplada con autenticación y autorización granular por roles (Backend), modelado transaccional estricto en base de datos relacional (Persistencia), consumo de APIs externas oficiales (AEMPS CIMA) junto con asistencia mediante Inteligencia Artificial, y contenerización con Docker para su despliegue.

### 1.3. Descripción general del sistema
<!-- TU TURNO: Resume los 5 módulos principales de PharmaFlow:
  1. Control de accesos por roles (RBAC) y trazabilidad RGPD.
  2. CRM y motor de fidelización/descuentos + control de saldos y deudas.
  3. Gestión de inventario por Código Nacional, lotes y caducidades.
  4. Integración oficial con CIMA (AEMPS) y asistencia clínica mediante IA.
  5. Punto de Venta (POS Web) y Dashboard de analítica. -->
PharmaFlow se estructura en cinco módulos funcionales interconectados que cubren todo el flujo de trabajo diario de la farmacia:
Gestión de Usuarios, Control de Accesos (RBAC) y Auditoría RGPD: Autenticación obligatoria mediante tokens JWT con permisos granulares para tres perfiles diferenciados (Titular/Manager, Farmacéutico/Técnico en Mostrador y Personal de Almacén/Logística), junto con un registro de auditoría inmutable para garantizar la trazabilidad de datos de salud conforme al RGPD.
Módulo CRM y Fidelización Avanzada: Ficha completa del paciente/cliente con histórico de compras, saldo acumulado y control de deudas o ventas pendientes de cobro (fianzas). Incluye un motor de reglas de descuento automatizado según segmento (ej. 10 % de bienvenida, 10 % para mayores de 65 años, 5 % en puericultura para familias) y un módulo de notificaciones automáticas (SMS / Webhook).
Gestión de Inventario, Lotes y Recepción de Pedidos: Control de existencias por Código Nacional (CN), número de lote y fecha de caducidad bajo criterio FEFO (First Expired, First Out), con alertas dinámicas por caducidad próxima (< 3 meses) y stock bajo mínimos, además de recepción de albaranes de cooperativas.
Integración con la API CIMA (AEMPS) y Asistencia Clínica con IA: Conexión directa con la base de datos oficial de la Agencia Española de Medicamentos y Productos Sanitarios para consultar fichas técnicas, prospectos en PDF y estado de desabastecimiento, complementada con un asistente inteligente que resume puntos clave de posología y advertencias para agilizar la explicación al paciente en mostrador.
Punto de Venta (POS Web) y Dashboard Analítico: Interfaz ágil de caja registradora web con aplicación automática de descuentos según el cliente seleccionado, y un panel de dirección con gráficos de facturación diaria, productos más vendidos y balance global de deudas.
---

## 2. Planteamiento del Problema o Necesidad

### 2.1. Situación o contexto actual
<!-- TU TURNO: Describe cómo trabajan muchas farmacias hoy en día (ERPs tradicionales de escritorio locales como Farmatic o Nixfarma, procesos manuales o apuntes en papel para encargos y deudas). -->


### 2.2. Problema o necesidad detectada
<!-- TU TURNO: Enumera los problemas concretos que resuelve PharmaFlow:
  - Mermas económicas por caducidades no detectadas a tiempo.
  - Desconexión entre la ficha del cliente y la aplicación automática de descuentos.
  - Falta de agilidad al consultar prospectos PDF extensos en mostrador.
  - Riesgos de seguridad/privacidad si no hay control estricto por usuario y rol. -->


### 2.3. Público objetivo o usuarios finales
<!-- TU TURNO: Define los 3 perfiles de usuario internos (Titular/Manager, Farmacéutico/Técnico en Mostrador, Personal de Almacén) y el cliente/paciente final beneficiado. -->


---

## 3. Objetivos del Proyecto

### 3.1. Objetivo general
<!-- TU TURNO: Un único párrafo claro que resuma la meta global del proyecto. -->


### 3.2. Objetivos específicos
<!-- TU TURNO: Lista de 6 a 8 objetivos concretos usando verbos en infinitivo (Implementar..., Integrar..., Automatizar..., Garantizar...). -->
- 
- 
- 
