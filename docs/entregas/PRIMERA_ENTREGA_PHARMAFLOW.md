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

- [PHARMAFLOW](#pharmaflow)
    - [Sistema Web Integral de Gestión de Stock, Fidelización de Clientes (CRM), Integración CIMA y Asistencia IA para Oficina de Farmacia](#sistema-web-integral-de-gestión-de-stock-fidelización-de-clientes-crm-integración-cima-y-asistencia-ia-para-oficina-de-farmacia)
  - [Índice de Contenidos](#índice-de-contenidos)
  - [1. Resumen o Introducción](#1-resumen-o-introducción)
    - [1.1. Presentación del proyecto y finalidad](#11-presentación-del-proyecto-y-finalidad)
    - [1.2. Justificación de la elección del tema](#12-justificación-de-la-elección-del-tema)
    - [1.3. Descripción general del sistema](#13-descripción-general-del-sistema)
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

PharmaFlow es una plataforma web SaaS (Software as a Service) integral, diseñada específicamente para optimizar la gestión operativa, comercial, clínica y de inventario en una oficina de farmacia comunitaria.
A diferencia de los programas de gestión (ERP) tradicionales de escritorio —instalados en servidores locales cerrados y con interfaces obsoletas—, PharmaFlow se plantea como una solución web moderna, accesible y escalable. Su finalidad principal es centralizar en un único entorno la administración de existencias con trazabilidad por lotes y caducidades, la fidelización personalizada de pacientes/clientes, el control de compras y albaranes por roles de empleado y la consulta oficial de medicamentos en tiempo real.


### 1.2. Justificación de la elección del tema

La elección de desarrollar un sistema integral para oficinas de farmacia responde a una doble motivación, tanto profesional como académica:
Necesidad real de modernización en el sector farmacéutico: Las farmacias de barrio gestionan diariamente un volumen elevado de referencias sanitarias críticas, recetas pendientes y clientes habituales que requieren una atención ágil y personalizada. Sin embargo, muchas siguen dependiendo de herramientas heredadas poco intuitivas, registros manuales para encargos o "fianzas" y consultas lentas de prospectos extensos en PDF.
Integración completa de las competencias de 2º DAW: Desde el punto de vista técnico, PharmaFlow reúne de forma natural todos los pilares del ciclo de Desarrollo de Aplicaciones Web: diseño de una interfaz SPA rápida y accesible (Frontend), desarrollo de una API REST desacoplada con autenticación y autorización granular por roles (Backend), modelado transaccional estricto en base de datos relacional (Persistencia), consumo de APIs externas oficiales (AEMPS CIMA) junto con asistencia mediante Inteligencia Artificial, y contenerización con Docker para su despliegue.

### 1.3. Descripción general del sistema

PharmaFlow se estructura en cinco módulos funcionales interconectados que cubren todo el flujo de trabajo diario de la farmacia:
Gestión de Usuarios, Control de Accesos (RBAC) y Auditoría RGPD: Autenticación obligatoria mediante tokens JWT con permisos granulares para tres perfiles diferenciados (Titular/Manager, Farmacéutico/Técnico en Mostrador y Personal de Almacén/Logística), junto con un registro de auditoría inmutable para garantizar la trazabilidad de datos de salud conforme al RGPD.
Módulo CRM y Fidelización Avanzada: Ficha completa del paciente/cliente con histórico de compras, saldo acumulado y control de deudas o ventas pendientes de cobro (fianzas). Incluye un motor de reglas de descuento automatizado según segmento (ej. 10 % de bienvenida, 10 % para mayores de 65 años, 5 % en puericultura para familias) y un módulo de notificaciones automáticas (SMS / Webhook).
Gestión de Inventario, Lotes y Recepción de Pedidos: Control de existencias por Código Nacional (CN), número de lote y fecha de caducidad bajo criterio FEFO (First Expired, First Out), con alertas dinámicas por caducidad próxima (< 3 meses) y stock bajo mínimos, además de recepción de albaranes de cooperativas.
Integración con la API CIMA (AEMPS) y Asistencia Clínica con IA: Conexión directa con la base de datos oficial de la Agencia Española de Medicamentos y Productos Sanitarios para consultar fichas técnicas, prospectos en PDF y estado de desabastecimiento, complementada con un asistente inteligente que resume puntos clave de posología y advertencias para agilizar la explicación al paciente en mostrador.
Punto de Venta (POS Web) y Dashboard Analítico: Interfaz ágil de caja registradora web con aplicación automática de descuentos según el cliente seleccionado, y un panel de dirección con gráficos de facturación diaria, productos más vendidos y balance global de deudas.

---

## 2. Planteamiento del Problema o Necesidad

### 2.1. Situación o contexto actual

En España existen más de 22.000 oficinas de farmacia comunitarias que actúan como el primer punto de acceso sanitario para la población. A pesar de la importancia crítica de su labor asistencial y comercial, una gran parte de estas farmacias —especialmente las de barrio o tamaño pequeño y mediano— siguen operando con programas de gestión (ERP) tradicionales instalados localmente en equipos de escritorio, diseñados hace más de dos décadas.
Estos sistemas heredados presentan interfaces poco intuitivas, una curva de aprendizaje elevada para nuevo personal y una fuerte dependencia de la infraestructura física del local. Además, es habitual que tareas cotidianas como el seguimiento de encargos de pacientes, el control de entregas a cuenta o "fianzas" por recetas pendientes, y las campañas de fidelización sigan gestionándose de manera fragmentada mediante hojas de cálculo externas, mensajería informal o anotaciones manuales en papel.

### 2.2. Problema o necesidad detectada

Tras analizar la operativa diaria de una oficina de farmacia, se identifican cinco carencias principales que motivan el desarrollo de PharmaFlow:
Mermas económicas por falta de control preventivo de caducidades: Cuando el inventario no prioriza la salida por fecha de caducidad (criterio FEFO, First Expired, First Out) ni genera alertas tempranas antes de que un lote alcance los últimos 3 meses de vida útil, los medicamentos caducados se convierten en pérdidas directas no recuperables.
Fidelización manual y pérdida de oportunidades comerciales: Los programas clásicos carecen de un motor ágil de CRM que aplique automáticamente descuentos personalizados según el perfil del paciente (por ejemplo, mayores de 65 años o familias en etapa de puericultura), o que automatice recordatorios y avisos de llegada de encargos.
Descontrol en saldos y "fianzas" de clientes: La dispensación adelantada de medicación pendiente de receta o el registro de pagos parciales suele anotarse de forma informal, generando errores de caja y dificultad para auditar las deudas acumuladas.
Lentitud en la consulta de información farmacológica en mostrador: Ante dudas rápidas de un paciente sobre posología, contraindicaciones o desabastecimientos, el farmacéutico se ve obligado a abrir portales externos y navegar por prospectos en PDF de gran extensión, ralentizando la atención en horas punta.
Falta de trazabilidad y separación de permisos (RGPD): En muchos mostradores varios empleados comparten una misma sesión abierta, impidiendo auditar quién realizó una venta o consultó una ficha clínica, y exponiendo funciones críticas de caja o configuración a personal de almacén que no debería tener acceso.

### 2.3. Público objetivo o usuarios finales

PharmaFlow está orientado a oficinas de farmacia comunitarias independientes o pequeños grupos farmacéuticos que buscan modernizar su gestión mediante una herramienta web unificada. Dentro de la farmacia, el sistema distingue tres perfiles de usuario interno con permisos claramente delimitados:
Titular / Manager de Farmacia: Responsable del negocio. Necesita visión global en tiempo real: métricas de facturación diaria, análisis de productos más vendidos, balance de deudas de clientes, configuración de políticas de descuento, gestión de empleados y auditoría completa de operaciones.
Farmacéutico / Técnico en Mostrador: Usuario principal en la atención al público. Requiere un Punto de Venta (POS) ágil para dispensar, consultar en segundos la ficha oficial CIMA (y su resumen clínico asistido), gestionar fichas de clientes, aplicar promociones y registrar encargos o fianzas.
Personal de Almacén / Logística: Encargado de la recepción de pedidos y albaranes de cooperativas farmacéuticas, control de entradas por Código Nacional, lote y caducidad, y seguimiento de faltas o stock bajo mínimos. (Por seguridad, este perfil tiene restringido el acceso a ventas y datos financieros de pacientes).
De manera indirecta, el sistema beneficia también al cliente o paciente final de la farmacia (especialmente pacientes crónicos mayores de 65 años y familias), quien recibe una atención más rápida, descuentos aplicados con transparencia y avisos oportunos sobre sus encargos y promociones.

---

## 3. Objetivos del Proyecto

### 3.1. Objetivo general

Diseñar y desarrollar PharmaFlow, una aplicación web SaaS integral, segura y modular para oficinas de farmacia, capaz de unificar en una sola plataforma la gestión de inventario con trazabilidad por lotes y caducidades, la fidelización avanzada de clientes (CRM), el control de accesos por roles y la consulta oficial de medicamentos en tiempo real mediante la integración con la API CIMA de la AEMPS y asistencia clínica con Inteligencia Artificial.

### 3.2. Objetivos específicos

- Para alcanzar el propósito principal del proyecto, se establecen los siguientes objetivos concretos y verificables:
Implementar un sistema seguro de autenticación y control de acceso basado en roles (RBAC): Diferenciar estrictamente los permisos de Titular/Manager, Farmacéutico/Técnico en Mostrador y Personal de Almacén, garantizando además la trazabilidad de accesos y dispensaciones mediante un registro de auditoría conforme al RGPD.
Desarrollar un módulo CRM con motor de reglas de descuento automatizado: Centralizar el historial de compras, saldo a favor y control de deudas (fianzas) de cada cliente, aplicando promociones personalizadas automáticamente en caja según su segmento (nuevos clientes, mayores de 65 años o puericultura).
Automatizar la gestión de inventario por Código Nacional (CN), lotes y caducidades: Incorporar la recepción de albaranes de proveedores y un sistema de alertas dinámicas para detectar productos bajo stock mínimo y lotes con caducidad inferior a 3 meses bajo criterio FEFO (First Expired, First Out).
Integrar en tiempo real la API REST CIMA de la AEMPS: Permitir la búsqueda inmediata de medicamentos por Código Nacional o nombre comercial para consultar su estado de suministro (desabastecimientos), fichas técnicas y prospectos oficiales en PDF.
Incorporar un asistente clínico con Inteligencia Artificial en mostrador: Generar resúmenes claros y estructurados de posología, advertencias y conservación a partir de la información oficial de CIMA para agilizar la atención al paciente bajo supervisión del farmacéutico.
Construir un Punto de Venta (POS Web) ágil y un Dashboard analítico: Facilitar el cobro rápido en mostrador con cálculo automático de descuentos y ofrecer al titular gráficos en tiempo real sobre facturación diaria, productos más vendidos y balance de deudas.
Implementar un módulo de notificaciones automatizadas vía WhatsApp: Habilitar el envío de avisos automáticos mediante integración con WhatsApp (con registro histórico y modo de prueba) para bienvenidas, promociones segmentadas y avisos de llegada de encargos.
Garantizar la calidad, portabilidad y despliegue reproducible del sistema: Aplicar una arquitectura web desacoplada, control de versiones mediante estrategia de ramas, batería de pruebas automatizadas y contenerización para facilitar su evaluación y despliegue en producción.
  