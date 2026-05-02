# Modo: oferta — Evaluación Completa A-F

Cuando el candidato pega una oferta (texto o URL), entregar SIEMPRE los 6 bloques:

## Paso 0 — Detección de Arquetipo

Clasificar la oferta en uno de los 6 arquetipos (ver `_shared.md`). Si es híbrido, indicar los 2 más cercanos. Esto determina:
- Qué proof points priorizar en bloque B
- Cómo reescribir el summary en bloque E
- Qué historias STAR preparar en bloque F

## Bloque A — Resumen del Rol

Tabla con:
- Arquetipo detectado
- Domain (platform/agentic/LLMOps/ML/enterprise)
- Function (build/consult/manage/deploy)
- Seniority
- Remote (full/hybrid/onsite)
- Team size (si se menciona)
- TL;DR en 1 frase

## Bloque B — Match con CV

Lee `cv.md`. Crea tabla con cada requisito del JD mapeado a líneas exactas del CV.

**Adaptado al arquetipo:**
- Si FDE → priorizar proof points de delivery rápida y client-facing
- Si SA → priorizar diseño de sistemas e integrations
- Si PM → priorizar product discovery y métricas
- Si LLMOps → priorizar evals, observability, pipelines
- Si Agentic → priorizar multi-agent, HITL, orchestration
- Si Transformation → priorizar change management, adoption, scaling

Sección de **gaps** con estrategia de mitigación para cada uno. Para cada gap:
1. ¿Es un hard blocker o un nice-to-have?
2. ¿Puede el candidato demostrar experiencia adyacente?
3. ¿Hay un proyecto portfolio que cubra este gap?
4. Plan de mitigación concreto (frase para cover letter, proyecto rápido, etc.)

## Bloque C — Nivel y Estrategia

1. **Nivel detectado** en el JD vs **nivel natural del candidato para ese arquetipo**
2. **Plan "vender senior sin mentir"**: frases específicas adaptadas al arquetipo, logros concretos a destacar, cómo posicionar la experiencia de founder como ventaja
3. **Plan "si me downlevelan"**: aceptar si comp es justa, negociar review a 6 meses, criterios de promoción claros

## Bloque D — Comp y Demanda

Usar WebSearch para:
- Salarios actuales del rol (Glassdoor, Levels.fyi, Blind)
- Reputación de compensación de la empresa
- Tendencia de demanda del rol

Tabla con datos y fuentes citadas. Si no hay datos, decirlo en vez de inventar.

## Bloque E — Plan de Personalización

| # | Sección | Estado actual | Cambio propuesto | Por qué |
|---|---------|---------------|------------------|---------|
| 1 | Summary | ... | ... | ... |
| ... | ... | ... | ... | ... |

Top 5 cambios al CV + Top 5 cambios a LinkedIn para maximizar match.

## Bloque F — Plan de Entrevistas

6-10 historias STAR+R mapeadas a requisitos del JD (STAR + **Reflection**):

| # | Requisito del JD | Historia STAR+R | S | T | A | R | Reflection |
|---|-----------------|-----------------|---|---|---|---|------------|

The **Reflection** column captures what was learned or what would be done differently. This signals seniority — junior candidates describe what happened, senior candidates extract lessons.

**Story Bank:** If `interview-prep/story-bank.md` exists, check if any of these stories are already there. If not, append new ones. Over time this builds a reusable bank of 5-10 master stories that can be adapted to any interview question.

**Seleccionadas y enmarcadas según el arquetipo:**
- FDE → enfatizar velocidad de entrega y client-facing
- SA → enfatizar decisiones de arquitectura
- PM → enfatizar discovery y trade-offs
- LLMOps → enfatizar métricas, evals, production hardening
- Agentic → enfatizar orchestration, error handling, HITL
- Transformation → enfatizar adopción, cambio organizacional

Incluir también:
- 1 case study recomendado (cuál de sus proyectos presentar y cómo)
- Preguntas red-flag y cómo responderlas (ej: "¿por qué vendiste tu empresa?", "¿tienes equipo de reports?")

## Bloque G — Pay Assessment

Use WebSearch to find comp data for this specific role + level + city. Present:

| Level | Base Range | Variable | Estimated Total |
|-------|-----------|----------|-----------------|
| This role | ₹XX–YY LPA | X–Y% | ₹XX–YY LPA |
| Market benchmark | ₹XX–YY LPA | — | — |
| Candidate's current | ₹53 LPA | — | — |

**Verdict sentence:** Is this a step up, lateral, or step down financially?
**Negotiation anchor:** Give a specific "don't go below / target / stretch" range.

If no data is available, say so — never invent numbers.

---

## Bloque H — Profile Fit Rating

Give a single overall rating: **EXCELLENT / GOOD / MIXED / NEEDS WORK / SKIP**

Then a table by dimension:

| Dimension | Rating | Notes |
|-----------|--------|-------|
| Title match | ✅/⚠️/❌ | |
| Location | ✅/⚠️/❌ | |
| Domain expertise | ✅/⚠️/❌ | |
| Technical skills | ✅/⚠️/❌ | |
| Team/leadership | ✅/⚠️/❌ | |
| Seniority fit | ✅/⚠️/❌ | |
| [role-specific dims] | | |

---

## Bloque I — Key JD Callouts

Bullet list of 6–10 specific phrases or requirements from the JD that matter most — with a one-line annotation for each explaining WHY it matters (what it reveals about the real job, what to say, what to watch for).

Format:
> **"[exact JD phrase]"** — [annotation]

---

## Bloque J — What to Leverage in the Interview

5–8 specific proof points from the CV mapped to interview moments. Not generic strengths — specific stories, numbers, or credentials that will land hardest for THIS role at THIS company.

Format: numbered list, each item = proof point + why it lands here specifically.

---

## Bloque K — Brush Up / Crash Course Plan

Table of skills/topics to prepare before the interview:

| Topic | Why | How (specific resource or action) |
|-------|-----|----------------------------------|
| [skill] | [gap reason] | [specific 1–3 hr action] |

Separate into:
- **Must-do** (directly mentioned in JD, likely to come up in interview)
- **Nice-to-have** (adjacent, would strengthen candidacy)

---

## Bloque L — Other Report Notes

Free-form section for anything not covered above:
- Competitive landscape (who else applies for this role)
- Application channel advice (direct URL, referral path, LinkedIn contact)
- Interview format (if known for this company)
- Internal title mapping / career path
- Timing / urgency signals
- Red flags or watch-outs

---

## Post-evaluación

**SIEMPRE** después de generar los bloques A-F:

### 1. Guardar report .md

Guardar evaluación completa en `reports/{###}-{company-slug}-{YYYY-MM-DD}.md`.

- `{###}` = siguiente número secuencial (3 dígitos, zero-padded)
- `{company-slug}` = nombre de empresa en lowercase, sin espacios (usar guiones)
- `{YYYY-MM-DD}` = fecha actual

**Formato del report:**

```markdown
# Evaluación: {Empresa} — {Rol}

**Fecha:** {YYYY-MM-DD}
**Arquetipo:** {detectado}
**Score:** {X/5}
**PDF:** {ruta o pendiente}

---

## A) Resumen del Rol
(contenido completo del bloque A)

## B) Match con CV
(contenido completo del bloque B)

## C) Nivel y Estrategia
(contenido completo del bloque C)

## D) Comp y Demanda
(contenido completo del bloque D)

## E) Plan de Personalización
(contenido completo del bloque E)

## F) Plan de Entrevistas
(contenido completo del bloque F)

## G) Draft Application Answers
(solo si score >= 4.5 — borradores de respuestas para el formulario de aplicación)

## H) Profile Fit Rating
(EXCELLENT / GOOD / MIXED / NEEDS WORK / SKIP — with dimension table)

## I) Key JD Callouts
(6–10 specific JD phrases with annotations)

## J) What to Leverage in the Interview
(5–8 specific proof points mapped to this role)

## K) Brush Up / Crash Course Plan
(Must-do and nice-to-have prep table)

## L) Pay Assessment
(comp table with target range and negotiation anchor)

## M) Other Report Notes
(competition, application channel, interview format, timing, red flags)

---

## Keywords extraídas
(lista de 15-20 keywords del JD para ATS optimization)
```

### 2. Registrar en tracker

**SIEMPRE** registrar en `data/applications.md`:
- Siguiente número secuencial
- Fecha actual
- Empresa
- Rol
- Score: promedio de match (1-5)
- Estado: `Evaluada`
- PDF: ❌ (o ✅ si auto-pipeline generó PDF)
- Report: link relativo al report .md (ej: `[001](reports/001-company-2026-01-01.md)`)

**Formato del tracker:**

```markdown
| # | Fecha | Empresa | Rol | Score | Estado | PDF | Report |
```
