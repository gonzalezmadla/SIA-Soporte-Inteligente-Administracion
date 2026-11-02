# SIA – Soporte Inteligente de Administración

## Checkpoint M1 – Agente Base y Motor de Razonamiento

### 1. Descripción del proyecto

SIA (Soporte Inteligente de Administración) es un asistente basado en inteligencia artificial diseñado para brindar soporte a procesos administrativos y contables.

Su objetivo es interpretar consultas, recuperar información de fuentes autorizadas, identificar faltantes e inconsistencias y derivar aquellos casos que requieren intervención humana.

### 2. Objetivo del M1

Desarrollar un agente de IA capaz de interpretar consultas administrativas, utilizar herramientas externas para recuperar información y generar respuestas fundamentadas, respetando límites de autonomía.

### 3. Arquitectura implementada

El workflow incluye:

- **Chat Trigger:** recibe las consultas del usuario.
- **AI Agent:** interpreta la solicitud y coordina el uso de herramientas.
- **Modelo de lenguaje:** motor de razonamiento del agente.
- **Simple Memory:** conserva el contexto de la conversación.
- **Google Sheets Tool:** consulta información de facturas recibidas.
- **IF:** identifica los casos que requieren supervisión.
- **Gmail:** registra y notifica los casos derivados a revisión humana.

### 4. Fuente de información

Se utiliza una base de datos demostrativa en Google Sheets denominada `SIA_Dataset_Empresa_Demo`, que contiene información ficticia de facturas, proveedores, vencimientos, estados de pago e importes pendientes.

### 5. Límites de autonomía

SIA funciona como asistente informativo y analítico. No está autorizado a aprobar facturas, ejecutar pagos, modificar registros contables ni tomar decisiones financieras.

### 6. Clasificación de respuestas

El agente utiliza cuatro estados:

- INFORMACION_ENCONTRADA
- FALTA_UN_DATO
- INCONSISTENCIA
- ESCALADO

### 7. Supervisión humana

Los casos que requieren intervención humana se derivan mediante una notificación por Gmail, conservando la consulta original y la respuesta generada por el agente.

### 8. Archivos y evidencias

- Workflow exportado de n8n: `SIA - Soporte Inteligente de Administración - M1(checkpoint1_MariadelosAngeles_Gonzalez)`.
- Capturas de configuración y pruebas: carpeta `evidencias/`.
