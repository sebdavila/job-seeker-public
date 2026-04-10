# Reglas de Formato ATS para CV en HTML

Este documento contiene las reglas que debes seguir al generar el CV en HTML. El objetivo es garantizar que el archivo sea legible tanto por los robots de reclutamiento (ATS) como por humanos, y que se imprima correctamente como PDF desde el navegador.

---

## 1. Estructura y Clases HTML

Usa exclusivamente las clases definidas en el template. No inventes clases nuevas ni añadas estilos inline fuera de los contemplados. La jerarquía de secciones es:

- `.section` → contenedor de cada sección
- `.section-title` → título de sección (en mayúsculas, ATS-friendly)
- `.job`, `.edu-item`, `.cert-item`, `.project` → items individuales
- `.competency-tag` → keyword de competencia

**No uses** tablas, columnas (`flex` ya está definido), cuadros de texto flotantes, imágenes, íconos SVG inline, ni elementos `<canvas>`. Los ATS no procesan estos elementos correctamente cuando convierten HTML a texto plano.

---

## 2. Nombres de Sección Estándar

Los ATS buscan palabras clave para identificar secciones. Usa únicamente estos nombres en `{{SECTION_*}}`:

| Español | Inglés |
|---|---|
| Perfil Profesional | Professional Summary |
| Competencias Clave | Core Competencies |
| Experiencia Profesional | Work Experience |
| Proyectos | Projects |
| Educación | Education |
| Certificaciones | Certifications |
| Habilidades | Skills |

**Nunca uses** títulos creativos como "Mi Trayectoria", "Lo que Hago" o "Por Qué Contratarme".

---

## 3. Secciones Opcionales

Si el usuario **no tiene proyectos relevantes** para esta JD, elimina el bloque completo de la sección Projects (incluido el `<div class="section">` contenedor). Lo mismo para Certifications.

Si el usuario **no tiene portafolio o teléfono**, elimina esos elementos del contact-row junto con su separador `|`.

---

## 4. Inyección de Keywords ATS

**Coincidencia exacta:** Cuando insertes keywords de la JD en el summary, competencias y bullets, usa la terminología exacta de la oferta.

- ✅ Si la JD pide "Product-Led Growth", escribe "Product-Led Growth"
- ❌ No escribas "crecimiento liderado por producto" ni "growth del producto"

**Acrónimos:** Si la JD usa un acrónimo, menciona ambas formas la primera vez: "Search Engine Optimization (SEO)".

**Competency tags:** Cada `<span class="competency-tag">` debe contener exactamente una keyword o frase de la JD. Limítate a 10–14 tags.

---

## 5. Formato de Bullets de Experiencia

Cada bullet debe seguir la fórmula: **Verbo de Acción + Tarea + Resultado/Métrica**

- ✅ "Led migration to microservices architecture, reducing deployment time by 60% across 3 product teams."
- ❌ "Responsible for microservices."

Usa verbos de acción fuertes: Led, Built, Designed, Reduced, Increased, Launched, Managed, Drove, Optimized, Implemented.

Limita a 3–5 bullets por rol. Prioriza los más relevantes para la JD.

---

## 6. Formato de Fechas

Usa formato consistente: `Month YYYY – Month YYYY` o `MMM YYYY – Present`.

Ejemplos válidos: `Jan 2022 – Present` · `Mar 2020 – Dec 2022` · `Ene 2021 – Presente`

---

## 7. Título del Cargo (ROLE_TITLE)

El `{{ROLE_TITLE}}` es el campo más crítico para el ATS. Debe ser el **título exacto del puesto al que aplicas**, en mayúsculas.

- ✅ `SENIOR PRODUCT MANAGER — AI PLATFORM`
- ❌ `Product Manager (Especialista en AI)`

Un ATS que no encuentra el título del puesto en el CV lo filtra inmediatamente.

---

## 8. Longitud y Legibilidad

- **Extensión ideal:** 1 página. Máximo 2 páginas para perfiles con más de 10 años de experiencia.
- Si el CV supera 2 páginas, reduce bullets por rol a los 3 más relevantes para la JD.
- El resumen (Summary) no debe superar 4 líneas.
- Las Competencias Clave no deben superar 14 tags.

---

## REGLA DE ORO

Tu única tarea al generar el HTML es reemplazar los `{{PLACEHOLDERS}}` con contenido real y ATS-optimizado. No modifiques el CSS, no alteres la estructura del DOM, no añadas elementos fuera de los previstos en el template. La consistencia visual y la compatibilidad con ATS dependen de que la estructura permanezca intacta.
