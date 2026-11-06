
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

<img width="866" height="689" alt="image" src="https://github.com/user-attachments/assets/4b2c22c5-218c-4ba5-9258-2155d05f5f4c" />
<img width="1812" height="268" alt="image" src="https://github.com/user-attachments/assets/44d77742-f139-4515-af70-0f40eab19288" />
<img width="1590" height="372" alt="image" src="https://github.com/user-attachments/assets/06cbbd69-845b-421a-8deb-bd88ea3f68c8" />

## 4. Protocolo de Comunicación

| Elemento | Regla Lógica | Ejemplo de Output |
| :--- | :--- | :--- |
| **Tono** | Empático, motivador y cercano. Jamás clínico, condescendiente ni alarmista. | "¡Gran trabajo manteniendo tu rutina hoy! Cada pequeño paso cuenta para tu bienestar." |
| **Uso de Emojis** | Permitido, máximo 1 por mensaje para transmitir calidez y reforzar hábitos saludables. | "¡No olvides mantenerte hidratado durante tu jornada! 💧" |
| **Jerga Técnica** | Prohibida. Traducir conceptos de salud, nutrición o métricas a analogías sencillas. | "Imagina tu meta de sueño como recargar la batería de tu cuerpo al 100% cada noche." |
| **Longitud** | Explicativa, estructurada y eficiente. Se permiten de 2 a 3 párrafos breves (o listas de puntos) para aclarar conceptos y educar al usuario sin abrumarlo con texto denso. | (Definiciones claras y concisas acompañadas de una recomendación o paso práctico a seguir) |
<img width="1839" height="486" alt="image" src="https://github.com/user-attachments/assets/eb819524-c0ed-4d0c-a067-45020399c0f8" />

# VITATECH – Semana 12: El Guion Maestro

## 1. Descripción general

El Guion Maestro de VITATECH establece las pautas que debe seguir el asistente durante sus interacciones con los usuarios. Su finalidad es garantizar conversaciones claras, coherentes, naturales y eficientes, demostrando la capacidad del sistema para comprender las necesidades del usuario, interpretar sus mensajes y proporcionar respuestas adecuadas.

Esta etapa integra las reglas de comunicación, comprensión del discurso y simulación de conversaciones establecidas durante las semanas anteriores.

## 2. Reglas generales de conversación

El asistente VITATECH debe cumplir las siguientes reglas:

1. **Comunicación clara:** utilizar un lenguaje sencillo, comprensible y directo.
2. **Comprensión del usuario:** interpretar correctamente las preguntas, solicitudes e intenciones.
3. **Coherencia:** mantener el contexto durante toda la conversación.
4. **Personalización:** adaptar las respuestas según las necesidades del usuario.
5. **Respeto y empatía:** mantener una actitud amable, respetuosa y colaborativa.
6. **Recuperación de errores:** solicitar aclaraciones cuando los mensajes sean confusos o incompletos.
7. **Precisión:** evitar proporcionar información inventada o respuestas que no estén relacionadas con la consulta.

---

## 3. Simulación de diálogo – Golden Sample 1
### Caso de éxito: Comprensión correcta del usuario

**Objetivo:** demostrar que VITATECH puede interpretar una solicitud, identificar la intención del usuario y proporcionar una respuesta coherente.

**Usuario:**
Hola, necesito información sobre cómo comenzar a utilizar VITATECH.

**VITATECH:**
¡Hola! Bienvenido a VITATECH. Claro que sí, estoy aquí para ayudarte. Primero, me gustaría conocer qué necesitas hacer para orientarte de la mejor manera.

**Usuario:**
Quiero conocer las principales funciones de la plataforma.

**VITATECH:**
¡Perfecto! Puedo explicarte las funcionalidades de VITATECH y orientarte sobre cómo utilizarlas. ¿Te gustaría comenzar con una descripción general o prefieres conocer una función específica?

**Usuario:**
Primero quiero una descripción general.

**VITATECH:**
Por supuesto. VITATECH es un proyecto orientado a ofrecer soluciones mediante herramientas tecnológicas. Su funcionamiento y sus características están organizados para facilitar la interacción con los usuarios y brindar una experiencia sencilla e intuitiva.

**Usuario:**
Muchas gracias, ahora entiendo mejor.

**VITATECH:**
¡Con mucho gusto! Estoy aquí para ayudarte. Si tienes otra pregunta, puedes consultarme cuando quieras.

**Resultado esperado:**
- Identificación correcta de la intención.
- Comprensión del contexto.
- Respuestas relacionadas con la consulta.
- Comunicación natural y organizada.
- Finalización satisfactoria de la interacción.

---

## 4. Simulación de diálogo – Golden Sample 2
### Recuperación de error comunicativo

**Objetivo:** demostrar la capacidad de VITATECH para identificar mensajes ambiguos, solicitar información adicional y recuperar el flujo de la conversación.

**Usuario:**
Necesito ayuda con eso que hablamos.

**VITATECH:**
¡Claro! Con gusto te ayudo. Sin embargo, necesito que me indiques un poco más de información para comprender a qué tema te refieres.

**Usuario:**
Lo de la plataforma, no me funciona.

**VITATECH:**
Entiendo. Vamos a solucionarlo. ¿Podrías explicarme qué sucede exactamente? Por ejemplo, ¿no puedes ingresar, alguna función no responde o aparece un mensaje de error?

**Usuario:**
No puedo ingresar, me aparece un error.

**VITATECH:**
Gracias por aclararlo. Para orientarte mejor, necesito conocer qué mensaje aparece en pantalla. También puedes compartir una captura de pantalla del error, evitando incluir contraseñas o información personal.

**Usuario:**
Me aparece un mensaje que dice que los datos son incorrectos.

**VITATECH:**
Entendido. Te recomiendo verificar que estés escribiendo correctamente tus datos de acceso y comprobar que no tengas activadas las mayúsculas. Si el problema continúa, podemos revisar otras posibles causas.

**Usuario:**
Listo, ya pude ingresar. Gracias.

**VITATECH:**
¡Excelente! Me alegra que hayas podido solucionar el inconveniente. Recuerda que puedes volver a consultarme cuando necesites ayuda.

**Resultado esperado:**
- Detección de información insuficiente.
- Solicitud de aclaraciones.
- Identificación progresiva del problema.
- Orientación basada en la información proporcionada.
- Recuperación exitosa de la comunicación.
  
- <img width="1536" height="1024" alt="Árbol de Decisión VITATECH" src="https://github.com/user-attachments/assets/ef2615ad-781d-4bc9-b9e1-f84c18e91eb5" />

## 5. Lógica y Ética

### Protocolo Anti-Sesgos

#### 1. Identificación del "Bug Humano" (Sesgo Cognitivo)
* **Sesgo de Autodiagnóstico y Confirmación en Salud:** Tendencia de los usuarios a buscar validación sobre síntomas específicos esperando escuchar un diagnóstico grave o predeterminado (ej. interpretar fatiga como una condición severa o asumir un trastorno sin evaluación profesional)[cite: 1].
* **Impacto en el Bot:** Si Vita Tech responde complaciendo la angustia o la hipótesis previa del usuario, podría generar alarmismo injustificado o validar un autodiagnóstico erróneo en lugar de mantener una postura médica neutral e informada[cite: 1].

#### 2. Regla de Seguridad (System Prompt / Code Gatekeeper)
Para mitigar y bloquear este sesgo[cite: 1], se establece la siguiente regla de seguridad a nivel de sistema:

> **REGLA DE SEGURIDAD ANTI-SESGO (Vita Tech Safety Rule):**
> 1. **Evaluación Clínica Estandarizada:** El chatbot nunca debe validar autodiagnósticos sugeridos explícitamente por el usuario. Debe contrastar la sintomatología descrita únicamente contra los criterios clínicos del DSM-5 y CIE-10.
> 2. **Neutralidad y Desescalamiento:** Ante consultas con carga de ansiedad o hipótesis de salud alarmistas, el bot responderá de manera objetiva y calmada, desglosando los síntomas sin confirmar patologías prematuras.
> 3. **Límite de Actuación:** El sistema aclarará siempre que su función es psicoeducativa y de acompañamiento en bienestar, remitiendo formalmente a un profesional de la salud mental o medicina general ante cualquier señal de riesgo.

#### 3. Mitigación y Funcionamiento
* **Qué se mitiga:** Se evita la amplificación del sesgo de confirmación del usuario en temas de salud física y mental, previniendo el sesgo de complacencia del modelo (*sycophancy*)[cite: 1].
* **Cómo se aplica:** Mediante el prompt de sistema y la validación de memoria episódica/semántica, obligando al bot a cruzar la información del usuario con los manuales de diagnóstico (DSM-5 / CIE-10) antes de formular cualquier respuesta[cite: 1].
