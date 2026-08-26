# AIda

**A**sistente **I**nstitucional **D**e **A**lumnos

Trabajo Final – Tecnicatura Universitaria en Programación – UTN FRT

Sistema de gestión de consultas y conocimiento académico con panel web y asistente conversacional basado en IA.

## Integrantes

- Lazarte, Jorge Exequiel
- Díaz, Juan Gabriel

## 1. Problema que resuelve

La información académica de la Facultad (mesas de examen, inscripciones, correlativas, trámites, ingreso de nuevos estudiantes, calendario) está dispersa entre PDF, redes sociales, cartelería física y consultas presenciales. Como consecuencia, Bedelía y Alumnado responden decenas de veces por día las mismas preguntas, los estudiantes reciben respuestas tardías o contradictorias, y la institución no tiene registro de qué se pregunta ni con qué frecuencia.

## 2. Solución propuesta: dos componentes integrados

El sistema no es únicamente un chatbot. El núcleo es una plataforma de gestión de conocimiento institucional; el asistente conversacional es uno de los canales que la consume.

### A. Panel web de gestión (Bedelía, Alumnado, Secretaría)

- Carga y actualización de la información oficial con versionado y vigencia.
- Bandeja de consultas priorizadas: lo que el asistente no puede responder con certeza se deriva a una persona, ordenado por urgencia y frecuencia.
- La respuesta humana se incorpora automáticamente a la base de conocimiento.
- Métricas: preguntas más frecuentes, temas sin cobertura, tiempos de respuesta, consumo y costo.

### B. AIda, el asistente conversacional con IA (estudiantes e ingresantes)

- Responde consultas en lenguaje natural, 24 horas, citando siempre la fuente oficial y su fecha de actualización.
- Distingue dos tipos de consulta: los datos exactos (fechas de mesas, correlativas, aranceles) se resuelven por consulta directa a la base de datos; los procedimientos y reglamentos se responden recuperando el documento oficial correspondiente.
- Si no tiene evidencia suficiente, no inventa: deriva al panel (política de abstención).

## 3. Beneficios por actor

| Estudiantes e ingresantes | Bedelía / Alumnado | Institución |
|---|---|---|
| Respuesta inmediata y fuera de horario administrativo. | Reducción del volumen de consultas repetitivas. | Datos objetivos sobre las necesidades reales de los estudiantes. |
| Información única y trazable, con fuente citada. | Una sola herramienta para publicar información en todos los canales. | Comunicación institucional consistente y auditable. |
| Menos viajes y filas por consultas simples. | Bandeja priorizada en lugar de mensajes dispersos. | Base replicable a otras carreras o facultades regionales. |

## 4. Tecnologías y arquitectura

| Capa | Tecnología | Justificación |
|---|---|---|
| Base de datos | PostgreSQL + pgvector | Un único motor resuelve datos relacionales, búsqueda de texto completo y búsqueda vectorial. |
| Backend / API | Python con FastAPI | Orquestación de la recuperación, ruteo de consultas e integración con el modelo. |
| Panel web | React + Vite | Panel de gestión para el personal y widget de chat embebible en el sitio institucional. |
| Inteligencia artificial | API de Anthropic (Claude) | Haiku 4.5 para clasificar consultas (bajo costo) y Sonnet 5 para redactar la respuesta final. |
| Recuperación | Búsqueda híbrida (léxica + semántica) con reordenamiento | Combina coincidencia exacta de términos y similitud semántica. |
| Infraestructura y canales | Docker + VPS; widget web, WhatsApp, Telegram | Despliegue reproducible y de bajo costo, con un adaptador por canal. |

## 5. Canal de WhatsApp

Durante el desarrollo se utiliza **Twilio Sandbox for WhatsApp** (sin costo, sin requerir autorización institucional). En producción se contempla migrar a **WhatsApp Business Platform** sobre el canal Meta de la Facultad, previa autorización institucional. El sistema es funcional aun sin ese acceso, operando sobre el widget web.

## 6. Alcance del trabajo final

**Incluido:** panel web completo (carga versionada, bandeja de consultas, métricas), asistente sobre información pública institucional sin autenticación, canales widget web y WhatsApp vía Twilio Sandbox, pipeline de carga de documentos oficiales, marco de evaluación (exactitud, fundamentación, abstención, latencia, costo), prueba piloto.

**Excluido (trabajo futuro):** consultas personalizadas por estudiante (requieren integración con SIU-Guaraní y tratamiento de datos bajo la Ley 25.326), notificaciones proactivas, despliegue en producción sobre el canal Meta institucional, replicación multi-institucional.

---

El aporte técnico no reside en el uso de un modelo de lenguaje comercial, sino en la arquitectura construida alrededor: el modelado y versionado del conocimiento institucional, el ruteo entre consulta estructurada y recuperación documental, la política de abstención y citación de fuentes, el circuito de derivación a personal humano y el marco de evaluación de la calidad de las respuestas.
