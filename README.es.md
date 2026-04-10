# job-seeker

> **[Read in English →](README.md)**

Un skill para Claude que actúa como coach de carrera experto. Dale una oferta de trabajo (URL o texto) y tu CV — evalúa el match en 5 dimensiones, genera un CV adaptado y optimizado para ATS en HTML, redacta mensajes de referido, y te prepara para la entrevista con historias STAR.

**Sin Node.js, sin Playwright, sin infraestructura.** Instala el archivo `.skill` y empieza desde Claude Desktop.

---

## Novedades en v2.0

| Característica | v1 | v2 |
|---|---|---|
| Formato del CV | Plantilla DOCX (edición XML) | Plantilla HTML (imprimir como PDF desde Chrome) |
| Evaluación de oferta | Puntuación básica | Scoring ponderado en 5 dimensiones con veredicto 🟢/🟡/🔴 |
| Onboarding | No tenía | Guarda `cv.md` + `profile.md` — no repites datos |
| Investigación de empresa | ❌ | Paso de research profundo opcional (WebSearch) |
| Mensajes de referido | Redactados como el aplicante | Redactados en 1ª persona **como el contacto interno** |
| Preparación de entrevista | ❌ | Historias STAR+R opcionales, guardadas por empresa |
| Detección de idioma | ✅ | ✅ (detección automática ES/EN) |

---

## Qué hace

1. **Carga tu perfil** — la primera vez configura `cv.md` y `profile.md`; en sesiones posteriores los carga en silencio
2. **Obtiene la JD** — pega una URL (LinkedIn, Greenhouse, Workday, etc.) o el texto completo de la oferta
3. **Research de empresa** — análisis profundo de cultura, finanzas y red flags (tú decides si lo quieres)
4. **Evalúa el match** en 5 dimensiones con puntuación ponderada y veredicto claro
5. **Reality check** — confirma que quieres continuar antes de generar cualquier contenido
6. **Genera el CV** — completa la plantilla HTML optimizada para ATS; ábrela en Chrome → Imprimir → Guardar como PDF
7. **Redacta mensajes de referido** — versión corta (LinkedIn/Slack, ≤300 caracteres) + email formal, escritos en 1ª persona como tu contacto interno para enviar a RRHH
8. **Carta de presentación** — opcional, estructurada, en el idioma correcto
9. **Preparación de entrevista** — historias STAR+R opcionales guardadas en `interview-prep/[empresa]-[cargo].md`

---

## Instalación

Descarga el archivo `.skill` desde [Releases](../../releases/latest) e instálalo en Claude:

- **Claude Desktop:** Configuración → Skills → Instalar desde archivo
- **Claude.ai:** Configuración → Skills → Subir archivo `.skill`

---

## Uso

Inicia una conversación y pega una oferta de trabajo:

> *"Quiero aplicar a este trabajo: https://linkedin.com/jobs/..."*

o

> *"I want to apply to this role: [pega el texto completo de la JD]"*

El skill te guía por todo el proceso paso a paso. Si es tu primera vez, te pedirá tu CV y unas preguntas rápidas de perfil — esto solo ocurre una vez.

---

## Cómo funciona el CV

El skill completa `assets/cv-template.html` reemplazando `{{PLACEHOLDERS}}` con tu información y las keywords de la oferta. Abres el HTML resultante en Chrome y lo imprimes como PDF (Cmd+P → Guardar como PDF → Márgenes: Mínimos). La plantilla usa Google Fonts y funciona completamente offline una vez que las fuentes están en caché.

No se guarda ningún dato personal entre sesiones, más allá de los archivos `cv.md` y `profile.md` que tú controlas.

---

## Dimensiones de evaluación

| Dimensión | Peso |
|---|---|
| Match de Perfil y Habilidades | 30% |
| Nivel y Seniority | 20% |
| Alineación de Compensación | 20% |
| Cultura y Motivación | 15% |
| Brechas y riesgos | 15% |

Puntuaciones por debajo de 3.0/5.0 generan una recomendación fuerte de no aplicar.

---

## Requisitos

- Claude Desktop o Claude.ai con soporte de skills
- Tu CV actual (cualquier formato — .pdf, .docx, o pega el texto)
- Chrome o Chromium para imprimir el CV HTML como PDF

---

## Código fuente

```
skills/
├── job-seeker/          # fuente v1
│   ├── SKILL.md
│   ├── assets/
│   │   └── base-cv-ats.docx
│   └── references/
│       └── reglas-ats.md
└── job-seeker-v2/       # fuente v2
    ├── SKILL.md
    ├── assets/
    │   └── cv-template.html
    └── references/
        └── reglas-ats.md
```
