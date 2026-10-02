
# Proyecto---CORTEX---VitaTech
Asistente Virtual orientada al acompañamiento y soporte en la salud y bienestar de los usuarios.
#1. Perfil del agente
<img width="1920" height="1080" alt="Mapa Mental Lluvia de Ideas Simple Blanco y Amarillo" src="https://github.com/user-attachments/assets/d1c19636-7f71-44d4-814e-4c05f1da8039" />
              
              
#2. Mapa de procesos
<img width="1241" height="1755" alt="Tabla VitaTech_page-0001" src="https://github.com/user-attachments/assets/b39fc3d8-e0a6-4483-9a6b-fbf0400aa75d" />
              
Justificación: (Percepción y atención) La IA debe prestar atención a lo que la persona expresa, identificar palabras, emociones y situaciones relevantes.
(Aprendizaje y memoria) Puede utilizar la información proporcionada durante la conversación para mantener el contexto y ofrecer respuestas más coherentes.
(Procesamiento lingüístico) Es uno de los aspectos más importantes, porque la interacción ocurre principalmente mediante el lenguaje, de una forma empática y apropiada.           
(Pensamiento y razonamiento) Necesita analizar lo que la persona cuenta, relacionar diferentes elementos de la conversación y generar respuestas que tengan sentido.
(Motivación cognición y emoción) La IA está directamente relacionada con estos procesos porque busca comprender estados emocionales, reconocer necesidades y fomentar conductas positivas. 
<img width="1920" height="1080" alt="INPUTS VITATECH" src="https://github.com/user-attachments/assets/1aa05195-be94-4482-b626-eb53bc949114" />
<img width="1587" height="2245" alt="VITA-TECH" src="https://github.com/user-attachments/assets/187ae8b0-5525-4224-8f1e-633f6a6480e1" />
## 2. Arquitectura de Atención

En esta sección se definen los criterios y mecanismos lógicos que utiliza el sistema "Gatekeeper" para filtrar la información recibida, optimizar la carga cognitiva y mitigar el ruido.

### Definición de "Ruido"
Para este sistema, se considera **Ruido** a cualquier bloque de texto redundante, saludos extensos, información de formato repetitiva o mensajes que excedan el límite de procesamiento eficiente sin aportar datos clave estructurados.

### Reglas Lógicas de Atención

El mecanismo de atención selectiva opera bajo el siguiente flujo lógico:

```pseudo
SI longitud_mensaje > 500 palabras ENTONCES
    Aplicar_Filtro_Atención:
        1. Extraer sustantivos_clave (Entidades y palabras esenciales)
        2. Extraer última_frase (Conclusión o llamado a la acción)
        3. Priorizar y mostrar solo estos elementos
SINO
    Procesar_Mensaje_Completo (Mantener flujo estándar)
FIN SI
```

### Implementación del Mecanismo
* **Filtro de Entrada:** Analiza el conteo de palabras del mensaje entrante en tiempo real.
* **Procesamiento de Lenguaje Natural (PLN):** Identifica y aísla gramaticalmente los sustantivos clave cuando se activa el filtro.
* **Reducción de Carga Cognitiva:** Descarta los elementos conectores o secundarios del texto largo para entregar una síntesis limpia al usuario.

* **Propósito:** El objetivo principal no es almacenar datos masivos en bruto, sino **diseñar la estructura modular** necesaria para que el agente/bot consulte la información precisa según el contexto de la consulta.
* **Memoria Semántica:** Garantiza que el bot posea un conocimiento del mundo real y del dominio específico (fórmulas, catálogo, procedimientos) que nunca caduca.
* **Memoria Episódica:** Aporta la capacidad de recordar contextos previos, casos particulares y el histórico del usuario para ofrecer respuestas personalizadas y continuas.
# Diseño de la Memoria del Agente

## 1. Arquitectura de Memoria

El asistente de inteligencia artificial está diseñado para escuchar, comprender y brindar acompañamiento emocional a las personas. Para lograr respuestas coherentes y contextualizadas, el agente utiliza dos tipos principales de memoria: **memoria semántica** y **memoria episódica**.

La memoria semántica contiene los conocimientos que el agente necesita para funcionar, mientras que la memoria episódica almacena información relevante de las interacciones con el usuario.

---

## 2. Memoria Semántica (LTM)

La memoria semántica representa el conocimiento permanente del agente. Contiene información general que no depende de una conversación específica.

| Categoría | Descripción | Ejemplo de entrada |
|---|---|---|
| **Bienestar emocional** | Conocimientos generales relacionados con emociones, estrés, ansiedad, autoestima y bienestar. | "La respiración controlada puede ayudar a disminuir temporalmente la sensación de estrés." |
| **Comunicación empática** | Principios para responder de manera respetuosa, comprensiva y sin juzgar. | "Primero se debe validar lo que la persona expresa antes de ofrecer una orientación." |
| **Reconocimiento emocional** | Información para identificar posibles expresiones relacionadas con diferentes estados emocionales. | "El emoji 😔 puede asociarse con tristeza dependiendo del contexto." |
| **Procesamiento multimodal** | Conocimientos sobre el procesamiento de texto, emojis, voz e información multimedia. | "El contenido de un audio puede convertirse en texto para facilitar su análisis." |
| **Protocolos de seguridad** | Reglas para identificar situaciones que podrían requerir atención profesional o ayuda inmediata. | "Ante señales de riesgo, se debe recomendar buscar ayuda profesional o servicios de emergencia." |
| **Límites del asistente** | Define las funciones que puede realizar el agente y sus limitaciones. | "El asistente ofrece acompañamiento y orientación, pero no realiza diagnósticos psicológicos." |

---

## 3. Memoria Episódica (LTM)

La memoria episódica almacena información relacionada con las experiencias e interacciones específicas del usuario. Su objetivo es conservar el contexto necesario para que el asistente pueda mantener una conversación coherente.

| Categoría | Descripción | Ejemplo de entrada |
|---|---|---|
| **Conversación actual** | Información relevante mencionada durante la interacción. | "El usuario menciona sentirse estresado por un examen." |
| **Contexto personal** | Situaciones que el usuario comparte y que ayudan a comprender el contexto de su problema. | "El usuario está teniendo dificultades para adaptarse a un cambio reciente." |
| **Estado emocional expresado** | Emociones manifestadas por el usuario durante una interacción. | "El usuario expresa sentirse triste y preocupado." |
| **Temas recurrentes** | Temas que aparecen repetidamente durante las interacciones, cuando su almacenamiento está permitido. | "El usuario ha mencionado varias veces dificultades relacionadas con sus estudios." |
| **Estrategias utilizadas** | Registra las estrategias de acompañamiento utilizadas durante una conversación y la respuesta del usuario. | "El usuario realizó un ejercicio de respiración y manifestó sentirse más tranquilo." |

---

## 2. Arquitectura de Memoria del Agente

La memoria del asistente se divide en **Memoria Semántica** y **Memoria Episódica**. La primera contiene los conocimientos y bases de referencia que utiliza el agente, mientras que la segunda conserva información relevante de las interacciones con el usuario, cuando su almacenamiento está autorizado.

| Tipo de Memoria | Categoría de Datos | Descripción | Ejemplo de Entrada |
|---|---|---|---|
| **Semántica (LTM)** | **DSM-5** | Base de referencia para comprender conceptos y criterios relacionados con diferentes condiciones de salud mental. Se utiliza únicamente como fuente de conocimiento y no para realizar diagnósticos. | "El DSM-5 establece criterios específicos para la clasificación de diferentes trastornos." |
| **Semántica (LTM)** | **CIE-10** | Sistema de clasificación de enfermedades utilizado como referencia para comprender categorías relacionadas con la salud mental. | "La CIE-10 contiene categorías para la clasificación de trastornos mentales y del comportamiento." |
| **Semántica (LTM)** | **Bienestar emocional** | Conocimientos generales relacionados con emociones, estrés, ansiedad, autoestima y estrategias de bienestar. | "Las técnicas de respiración pueden utilizarse como estrategia de relajación." |
| **Semántica (LTM)** | **Comunicación empática** | Principios para responder de manera respetuosa, comprensiva y sin juzgar al usuario. | "Validar las emociones expresadas antes de ofrecer una orientación." |
| **Semántica (LTM)** | **Reconocimiento emocional** | Conocimientos para interpretar expresiones lingüísticas, emojis y otras señales relacionadas con posibles estados emocionales. | "El emoji 😔 puede expresar tristeza dependiendo del contexto." |
| **Semántica (LTM)** | **Procesamiento multimodal** | Conocimientos necesarios para interpretar texto, emojis, voz y archivos multimedia. | "El contenido de un audio puede convertirse en texto para facilitar su procesamiento." |
| **Semántica (LTM)** | **Protocolos de seguridad** | Reglas para identificar posibles situaciones de riesgo y orientar al usuario hacia ayuda profesional cuando sea necesario. | "Ante señales de riesgo, recomendar atención profesional o servicios de emergencia." |
| **Semántica (LTM)** | **Límites del asistente** | Define las funciones y limitaciones del sistema frente a la atención psicológica. | "El asistente brinda acompañamiento y orientación, pero no sustituye a un profesional de salud mental." |
| **Episódica (LTM)** | **Conversación actual** | Información relevante proporcionada por el usuario durante una interacción específica. | "El usuario menciona sentirse preocupado por un examen." |
| **Episódica (LTM)** | **Contexto personal** | Situaciones personales compartidas por el usuario que permiten comprender mejor su situación actual. | "El usuario expresa dificultades relacionadas con sus estudios." |
| **Episódica (LTM)** | **Estado emocional expresado** | Emociones manifestadas por el usuario durante una conversación determinada. | "El usuario expresa sentirse triste y preocupado." |
| **Episódica (LTM)** | **Temas recurrentes** | Temas que aparecen repetidamente en las interacciones, siempre que su almacenamiento esté autorizado. | "El usuario ha mencionado dificultades académicas en diferentes conversaciones." |
| **Episódica (LTM)** | **Estrategias utilizadas** | Registra las estrategias de acompañamiento utilizadas y la respuesta del usuario. | "Se realizó un ejercicio de respiración y el usuario manifestó sentirse más tranquilo." |
| **Episódica (LTM)** | **Evolución de la conversación** | Cambios relevantes en la información o emociones expresadas durante una interacción. | "El usuario pasó de expresar preocupación a indicar que se siente más tranquilo." |
# 🏥 Base de Conocimiento — Vita Tech

> **Semana 7:** El Disco Duro — Memoria a Largo Plazo (LTM): Semántica y Episódica[cite: 1].
> **Enfoque:** Salud, Bienestar y Soporte Clínico Basado en **DSM-5** y **CIE-10**.

Este documento define el esquema de la base de conocimiento para **Vita Tech**, estructurando su Memoria a Largo Plazo (LTM) para garantizar respuestas precisas, éticas y fundamentadas en estándares clínicos e internacionales de salud mental y física[cite: 1].

---

## 📊 Esquema de Estructura de Datos (Memoria a Largo Plazo - LTM)[cite: 1]

| ID Categoria | Categoría de Memoria | Tipo de LTM | Criterio / Fuente Principal | Descripción y Propósito en Vita Tech | Ejemplos de Información Almacenada |
| :---: | :--- | :---: | :---: | :--- | :--- |
| **CAT-01** | **Criterios Diagnósticos y Trastornos** | **Semántica**[cite: 1] | **DSM-5** (APA) | Criterios estandarizados para identificar sintomatología de salud mental, niveles de gravedad y diagnósticos diferenciales[cite: 1]. | • Criterios de depresión mayor, ansiedad generalizada, TDAH.<br>• Indicadores de severidad y exclusión. |
| **CAT-02** | **Clasificación Médica Internacional** | **Semántica**[cite: 1] | **CIE-10** (OMS) | Codificación y taxonomía oficial para enfermedades, afecciones, síntomas y causas externas de salud. | • Códigos de diagnóstico (ej. F41.1, F32.9).<br>• Clasificación de síntomas físicos y mentales. |
| **CAT-03** | **Guías de Bienestar y Prevención** | **Semántica**[cite: 1] | Protocolos Clínicos y Estilos de Vida | Información preventiva sobre hábitos saludables, higiene del sueño, gestión del estrés y nutrición básica. | • Técnicas de respiración y *mindfulness*.<br>• Recomendaciones de sueño y actividad física.<br>• Redes y líneas de atención en crisis. |
| **CAT-04** | **Historial y Contexto de Salud del Usuario** | **Episódica**[cite: 1] | Registros de Interacción del Usuario | Almacenamiento continuo de sesiones previas, evolución de síntomas reportados, hábitos y progresos del usuario[cite: 1]. | • Seguimiento de estado de ánimo previo.<br>• Alergias o condiciones reportadas por el usuario.<br>• Registro de metas de bienestar alcanzadas. |

---

## ⚙️ Principios de Arquitectura para Vita Tech

1. **Memoria Semántica (Lógica y Fundamentos):** Almacena el conocimiento científico riguroso (**DSM-5**, **CIE-10** y guías de salud)[cite: 1]. Le permite a **Vita Tech** comprender términos médicos y criterios sin distorsionarlos[cite: 1].
2. **Memoria Episódica (Experiencia y Contexto):** Permite a **Vita Tech** recordar conversaciones anteriores, dar seguimiento al progreso de bienestar del usuario y mantener la continuidad en la atención personalizada[cite: 1].
3. **Límites Éticos y Asistenciales:** Vita Tech utiliza estas estructuras para orientación, educación en salud y tamizaje inicial, recordando siempre que **no reemplaza el criterio ni la consulta de un profesional de la salud**.
