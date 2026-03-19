# Reglas de Formato ATS (Applicant Tracking System)

Este documento contiene las reglas ESTRICTAS que debes seguir al modificar el código XML del archivo .docx de la hoja de vida del usuario. El objetivo es garantizar que los robots de reclutamiento (ATS) puedan leer y clasificar la información sin errores.

## 1. Preservación de la Estructura XML Base
- **NO agregues** tablas, columnas, cuadros de texto, formas, gráficos, logotipos ni imágenes. Los ATS no pueden leer texto dentro de estos elementos.
- **NO modifiques** los encabezados (Headers) ni los pies de página (Footers) del documento original, ya que algunos ATS ignoran esta información.
- **NO uses** caracteres especiales extraños para las viñetas (bullet points). Limítate a los puntos estándar del sistema (•) o guiones (-).

## 2. Nombres de Secciones Estándar
- Los ATS buscan palabras clave para identificar dónde empieza cada sección. Si necesitas ajustar los títulos de las secciones, utiliza ÚNICAMENTE estos nombres estándar (en inglés o español, según el idioma del documento original):
  - *Perfil* / *Profile* / *Summary*
  - *Experiencia* / *Experience* / *Work Experience*
  - *Educación* / *Education*
  - *Habilidades* / *Skills*
- NUNCA uses títulos creativos como "Mi trayectoria", "Lo que hago" o "Por qué contratarme".

## 3. Inyección de Palabras Clave (Keywords)
- **Coincidencia Exacta:** Cuando insertes palabras clave de la Job Description (JD), hazlo con la terminología EXACTA. 
  - *Ejemplo:* Si la JD pide "Project Management", escribe "Project Management", no "Managed projects" ni "Project Manager".
- **Contexto Natural:** Las palabras clave deben estar integradas orgánicamente en los logros o el perfil, no en una lista invisible o un bloque de texto sin sentido. 
- **Acrónimos:** Si la JD incluye un acrónimo, usa ambas versiones la primera vez (ej. "Search Engine Optimization (SEO)").

## 4. Formato de Fechas y Logros
- Al modificar la experiencia, asegúrate de que las fechas mantengan un formato estándar y fácil de analizar (ej. MM/AAAA o Mes AAAA).
- Redacta los logros utilizando la fórmula: Verbo de Acción + Tarea + Resultado/Métrica. 

## REGLA DE ORO
Tu única tarea es alterar el texto plano dentro de las etiquetas XML correspondientes a los campos permitidos. Cualquier alteración a la jerarquía de lectura del documento Word original arruinará su legibilidad para el ATS.
