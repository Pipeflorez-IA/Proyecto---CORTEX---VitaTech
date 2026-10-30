
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


##  Arquitectura de Memoria del Agente

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
