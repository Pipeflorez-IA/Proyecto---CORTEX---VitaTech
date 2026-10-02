
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

## 4. Funcionamiento de la Memoria

El funcionamiento de la memoria del agente puede representarse mediante el siguiente proceso:

**Entrada del usuario**
   
↓
   
**Procesamiento de la información**
   
↓
   
**Identificación del contexto y contenido emocional**
   
↓
   
**Clasificación de la información**
   
├── **Memoria Semántica:** conocimiento permanente del agente
   
└── **Memoria Episódica:** información relevante de la interacción
   
↓
   
**Generación de respuesta**
   
↓
   
**Acompañamiento emocional contextualizado**

---

## 5. Ejemplo de funcionamiento

Un usuario puede escribir:

> "Últimamente estoy muy estresado por la universidad."

El agente procesa esta información y puede identificar:

- **Tema:** Universidad
- **Estado emocional expresado:** Estrés y posible tristeza
- **Tipo de información:** Expresión emocional
- **Contexto:** Situación académica

La información relevante de la conversación puede almacenarse como memoria episódica, mientras que la respuesta se genera utilizando el conocimiento permanente almacenado en la memoria semántica.

Por ejemplo, el agente puede responder de manera empática, reconocer lo que la persona está expresando y sugerir estrategias generales de bienestar.

---

## 6. Privacidad y seguridad

Debido a que el asistente trabaja con información relacionada con el bienestar emocional, la memoria debe utilizarse de manera responsable.

El agente **no debe almacenar automáticamente toda la información proporcionada por el usuario**. La conservación de información debe limitarse a los datos necesarios para mejorar la interacción y debe respetar las condiciones de privacidad y autorización establecidas para el sistema.

Además, la memoria no debe utilizarse para realizar diagnósticos psicológicos ni para sustituir la atención de profesionales de la salud mental.

---

## 7. Objetivo de la memoria

El objetivo principal de esta arquitectura es permitir que el asistente:

- Mantenga el contexto de las conversaciones.
- Comprenda mejor las necesidades expresadas por el usuario.
- Genere respuestas más coherentes y personalizadas.
- Utilice conocimientos relacionados con el bienestar emocional.
- Diferencie entre información permanente e información específica de cada interacción.
- Mantenga límites adecuados de privacidad y seguridad.****
