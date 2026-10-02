
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
# Esquema de la Base de Conocimiento (GitHub)

> **Semana 7:** El Disco Duro — Memoria a Largo Plazo (LTM): Semántica y Episódica.

Este documento contiene la estructura y el esquema conceptual para simular las "carpetas" de memoria a largo plazo que utilizará el bot para organizar, almacenar y consultar información fundamental de manera persistente.

---

## 🗂️ Estructura del Esquema de Datos (LTM)

| ID Categoria | Categoría de Memoria | Tipo de Memoria (LTM) | Descripción y Propósito | Tipos de Datos / Contenido Ejemplar |
| :---: | :--- | :---: | :--- | :--- |
| **CAT-01** | **Memoria Semántica (Conocimiento Base)** | Semántica | Conceptos, reglas, leyes, normas y fórmulas que el bot debe conocer permanentemente para operar de manera precisa. | • Leyes / Normativas<br>• Fórmulas y reglas de negocio<br>• Glosario de términos |
| **CAT-02** | **Catálogo de Productos y Servicios** | Semántica | Registro completo de la oferta disponible, especificaciones técnicas, precios y disponibilidades. | • Catálogo comercial<br>• Fichas técnicas<br>• Lista de precios y SKU |
| **CAT-03** | **Preguntas Frecuentes (FAQ)** | Semántica | Repositorio de consultas recurrentes y sus respuestas validadas para garantizar consistencia. | • Guías paso a paso<br>• Respuestas estandarizadas<br>• Resoluciones comunes |
| **CAT-04** | **Memoria Episódica (Histórico de Interacciones)** | Episódica | Registro cronológico y contextual de interacciones previas con usuarios, eventos relevantes y casos pasados. | • Logs de conversaciones<br>• Historial de incidencias<br>• Preferencias del usuario |

---

## 📌 Explicación del Diseño

* **Propósito:** El objetivo principal no es almacenar datos masivos en bruto, sino **diseñar la estructura modular** necesaria para que el agente/bot consulte la información precisa según el contexto de la consulta.
* **Memoria Semántica:** Garantiza que el bot posea un conocimiento del mundo real y del dominio específico (fórmulas, catálogo, procedimientos) que nunca caduca.
* **Memoria Episódica:** Aporta la capacidad de recordar contextos previos, casos particulares y el histórico del usuario para ofrecer respuestas personalizadas y continuas.
