# ecosistema-ia-leads-financieros
Ecosistema autónomo con IA para la cualificación y gestión de leads de inversores. Desarrollado con Make, Airtable y OpenAI. Optimiza costos con enrutamiento inteligente, filtra spam y aplica validación humana (HITL) para emitir propuestas comerciales seguras y personalizadas.

# 🚀 AI Investor Onboarding Pipeline

Un ecosistema de automatización inteligente diseñado para la captación, cualificación y perfilado de leads financieros. El sistema procesa consultas entrantes en lenguaje natural, estructura los datos, evalúa el perfil de riesgo del inversor y orquesta un flujo de decisiones autónomo, culminando en propuestas comerciales asistidas por IA.

## 🛠️ Stack Tecnológico

* **Make (Integromat):** Orquestador central del flujo lógico y manejo de errores.
* **OpenAI API (GPT-4o-mini / GPT-4o):** Motor de procesamiento de lenguaje natural (NLP) para extracción de datos estructurados (JSON) y redacción persuasiva.
* **Airtable:** Base de datos relacional (Cerebro) para trazabilidad de estados, catálogo de fondos y registro de errores.
* **Gmail / Slack:** Triggers de entrada, notificaciones de monitoreo y puntos de validación (Borradores).

## 🧠 Arquitectura Lógica (Orquestador)

El flujo se divide en 4 módulos de ingesta y un enrutador (Router) con 4 caminos de decisión dinámicos:

1. **Ruta A (Faltan Datos):** El lead no especificó capital o riesgo. La IA redacta y envía automáticamente una solicitud de clarificación.
2. **Ruta B (Spam / Descarte):** Filtro binario inteligente. Si el correo es irrelevante, el orquestador lo clasifica como Error silenciosamente, ahorrando costos de procesamiento.
3. **Ruta C (Lead Completo - VIP):** El "Camino Feliz". Se activa el modelo superior (GPT-4o) para redactar una propuesta comercial personalizada y se ejecuta el protocolo HITL.
4. **Ruta D (Soporte al Cliente):** Identifica a los clientes actuales de la cartera que realizan consultas operativas, desviándolos hacia Slack para evitar envíos de plantillas de ventas.

## 🛡️ Características Destacadas

* **Optimización de Costos (Tiering):** Uso de `gpt-4o-mini` (rápido y económico) para el triage masivo de todos los correos entrantes, reservando el procesamiento pesado de `gpt-4o` exclusivamente para el 15% de los leads calificados.
* **Resiliencia y Tolerancia a Fallos:** Implementación de directivas `Break` (reintentos ante caídas de la API) e `Ignore` (para fallos de parseo JSON), garantizando que el escenario no colapse. Todo fallo se registra en la tabla `Log_Errores`.
* **Human-in-the-Loop (HITL):** El sistema nunca envía ofertas financieras automáticamente. Genera un Borrador en Gmail y emite una alerta por Slack, exigiendo la revisión final de un asesor comercial.
* **Data Minimization:** Sanitización de datos entrantes mediante extracción JSON estricta, descartando ruido y aislando la información personal.

## 📄 Documentación Adjunta

En este repositorio se incluye la carpeta con todo los manuales operativos que detallan la ingeniería detrás del proyecto, Imagen del esquema en Make y Video explicando el funcionamiento del mismo como asi tambien el link al escenario creado en Make y las Bases de datos creadas en Airtable:
* [https://drive.google.com/drive/folders/1X4RRCUo2ktAM7z8VAGKj8pmnVW0NTa87?usp=drive_link](https://drive.google.com/drive/folders/1X4RRCUo2ktAM7z8VAGKj8pmnVW0NTa87?usp=sharing)
* https://us2.make.com/public/shared-scenario/tEWiGokMxBH/entrega-final
* https://airtable.com/invite/l?inviteId=inv0CmOQqIJZvcowH&inviteToken=9a5842ee439f037f73f1c51266fc6df92a8248878b8ea93bc8a4e94abefa8103&utm_medium=email&utm_source=product_team&utm_content=transactional-alerts

Dashboard de Control
* https://airtable.com/appdbl5mR6F8B8Wno/pagMcKBD7Lb0T2ybH



---
**Autor:** Gonzalo Nicolas Severini
**Rol:** Data Analyst
