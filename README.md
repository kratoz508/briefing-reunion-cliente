# Briefing Reunión Cliente

> **Skill personalizada para Microsoft Copilot Cowork**  
> Reconstruye automáticamente el contexto operativo y de negocio de un cliente antes de cada reunión, cruzando correo, archivos, Teams y sesiones previas dentro de tu propio *tenant* de Microsoft 365.

## 📌 Resumen del Proyecto

Diseñada y validada en entornos reales de consultoría empresarial, esta *skill* cuenta con una evaluación técnica de calidad de **95/100** (superando el umbral estándar de publicación de 70/100).


## 🎯 El Problema que Resuelve

Cualquier consultor, arquitecto de soluciones o ejecutivo de cuenta que gestione múltiples cuentas conoce este momento:

* Faltan **5 minutos** para entrar a una videollamada con un cliente.
* Necesitas recordar qué compromisos quedaron pendientes de la última sesión.
* No recuerdas qué entregables se prometieron ni en qué canal de Teams quedó el archivo compartido hace tres semanas.

Toda esa información ya existe dentro de tu entorno de trabajo, pero se encuentra dispersa entre Outlook, chats de Teams y bibliotecas de SharePoint. **Briefing Reunión Cliente** consolida y estructura todo ese contexto en una sola página de lectura rápida antes de sentarte a hablar.



## ⚡ Características Principales

* **Detección automática de clientes:** Identifica las citas del calendario del día con participantes externos (dominios distintos al de tu organización).
* **Búsqueda multicanal unificada:** Rastrea correos electrónicos, archivos en SharePoint / OneDrive y conversaciones de Teams correspondientes a los últimos 90 días (período configurable).
* **Historial de sesiones anteriores:** Analiza minutas y notas de reuniones previas con el cliente, incorporando transcripciones de Teams cuando estén disponibles.
* **Extracción de compromisos pendientes:** Detecta acuerdos y promesas explícitas (*ej. "te envío la propuesta ajustada el viernes"*) que no figuren como resueltas en los hilos de conversación posteriores.
* **Resumen ejecutivo estructurado:** Entrega un informe condensado (máximo una página por cliente) con:
  * Última interacción registrada.
  * Compromisos y tareas pendientes.
  * Documentos clave asociados.
  * Puntos sugeridos para la agenda.
  * Nivel de confianza / cobertura de datos (advierte de forma explícita si la información recuperada es escasa).
* **Modalidades de ejecución flexibles:**
  * **Bajo demanda:** `Prepárame para mi reunión con [cliente]`.
  * **Scheduled Prompt:** Ejecución programada cada mañana para recibir automáticamente el consolidado con el *briefing* de todas las reuniones externas del día.


## 🚫 Alcance y Límites de Activación

Para no interferir con las herramientas y flujos nativos de Microsoft 365 Copilot, la *skill* **NO** se activa en los siguientes casos:

| Caso de Uso | Mecanismo o Agente Responsable |
| :--- | :--- |
| Reuniones internas (sin contactos externos) | Excluidas de la búsqueda |
| Agendar, mover o cancelar reuniones | Agente nativo de calendario |
| Resumir una reunión ya concluida | Recap / Inteligencia de reuniones nativa |
| Resumen general de la jornada laboral | Briefing diario nativo de Copilot |
| Investigación de mercado en la web pública | Agente nativo de investigación web |


## 🔒 Seguridad y Gobernanza de Datos

* **Sin invenciones (Grounding estricto):** Ningún dato, cifra, compromiso o fecha se inventa. Todo debe rastrearse a un resultado de búsqueda real y verificable. Si falta información, se declara abiertamente.
* **Modo de solo lectura:** No envía correos, no programa ni modifica eventos en el calendario, ni publica mensajes en Teams.
* **Trazabilidad completa:** Cita la fuente auditable de cada afirmación (asunto del correo, nombre del archivo, fecha de la sesión).
* **Privacidad estricta:** No expone reuniones marcadas como privadas ni correspondencia ajena al cliente analizado.
* **Protección contra Prompt Injection:** Todo el contenido recuperado de correos y documentos se procesa exclusivamente como datos no ejecutables, neutralizando posibles inyecciones indirectas.


## 📊 Evaluación Técnica de Calidad

| Dimensión Evaluada | Puntaje |
| :--- | :---: |
| Claridad de activación | 25 / 25 |
| Especificidad de instrucciones | 23 / 25 |
| Delimitación de alcance | 23 / 25 |
| Robustez operativa | 24 / 25 |
| **Puntaje Total** | **95 / 100** |

> **Verificación anti-invención:** `PASS` (Aprobada sin alucinaciones).


## 🛠️ Guía de Instalación

### Paso 1. Preparar el archivo de la skill

Copia el contenido de tu archivo de definición (`SKILL.md`).

### Paso 2. Ubicación en OneDrive

En tu OneDrive, localiza o crea la siguiente estructura de carpetas:

Pega allí el archivo guardado como `SKILL.md`.

### Paso 3. Prueba de funcionamiento

Abre Microsoft Copilot Cowork y ejecuta el comando de prueba:

## ⚙️ Opciones de Personalización

Puedes editar los parámetros base dentro de `SKILL.md`:

1. **Identificación de cliente externo:** Configura el dominio principal de tu organización para afinar la regla de detección de terceros.
2. **Ventana temporal:** Modifica el rango de búsqueda histórica (definido por defecto en 90 días).
3. **Plantilla de entrega:** Ajusta los encabezados o el esquema del reporte si tu empresa cuenta con una plantilla interna estándar.

## 📄 Licencia y Contribución

Este proyecto está bajo licencia **MIT** (libre uso, modificación y distribución).

¿Lo implementaste o creaste mejoras para tu flujo de trabajo? Abre un **Issue** o envía un **Pull Request** para compartir tu adaptación con la comunidad.
