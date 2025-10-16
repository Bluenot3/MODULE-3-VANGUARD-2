# Define the content of the .md file
content = """# Agents Module — ZEN AI Pioneer / Vanguard Track
## Module 3: AI Interaction & Autonomy (Build + Deploy + Embed)

This file instructs Codex to generate a complete, hands-on AI literacy course that teaches learners to deploy, embed, and integrate their own AI creations.

By the end of this module, every learner will have:

- A live Hugging Face Space they personally launched.
- A custom Google Site integrated with that Space.
- Custom-coded HTML/JS widgets and generated images.
- Two advanced exercises tested in the course itself.

---

## 🔒 Code Emission Rules (Important)

These rules apply to Codex output. The instructions remain Markdown, but the generated artifacts must NOT be Markdown-fenced.

1. Do not wrap any generated source code in Markdown fences (no ``` blocks).
2. Emit files as plain text using file delimiters exactly like this:

<<<START_FILE:path/from/repo/root.ext>>>
<file contents here, any language>
<<<END_FILE>>>

3. Use correct file extensions and directories (e.g., .py, .ts, .tsx, .js, .css, .html, .md, .yaml).
4. You may generate any language or framework required by the spec (Python, JS/TS, HTML/CSS, Gradio, Next.js, etc.).
5. Include a root /project_manifest.json with sha256 checksums for all emitted files.
6. After emitting all files, also emit: /README.md, /qa_report.md, /telemetry.json.
7. If something conflicts or is missing, ship the closest working scaffold, list blockers in /qa_report.md, and do one minimal-diff repair pass.

---

## 🧭 Course Overview

**Goal:** Transform learners from AI users into deployers—people who can design, launch, and host AI agents and applications on public platforms.

**Length:** 2–3 weeks  
**Difficulty:** Beginner → Intermediate  
**Stack:** Hugging Face Spaces (Gradio), Google Sites, Python, HTML/CSS/JS, OpenAI API (GPT-5 or GPT-4o).

---

## 🧱 Learning Outcomes

Learners will:

1. Build and launch a public-facing Hugging Face Space (Gradio UI).
2. Integrate their Space into a Google Site as an interactive app (embed + link-out).
3. Use AI models to generate custom visuals (logos, banners) and optimize for web.
4. Code and embed custom HTML/JS widgets that call APIs safely.
5. Complete two self-contained projects demonstrating multimodal/autonomous apps.
6. Publish a portfolio Google Site showcasing their deployed work.

---

## 📂 Repository Layout (to be emitted as files, not Markdown)

Codex must emit the following tree (add files as needed):

/course
/modules/03_agents/
syllabus.md
instructor_guide.md
learner_guide.md
assets/
logos/
banners/
sample_data/
exercises/
01_launch_hf_space/
02_embed_google_site/
03_custom_widget/
04_autonomy_projects/
solutions/
grading_rubrics/
checklists/
/scaffolds
/hf_space_basic/
/hf_space_multimodal/
/widget_html_js/
/next_embed_demo/
project_manifest.json
README.md
qa_report.md
telemetry.json

yaml
Always show details

Copy code

All of the above must be emitted via <<<START_FILE … >>> … <<<END_FILE>>> blocks with real file contents.

---


## 🧪 Acceptance Tests (auto-generate into /qa_report.md)

Codex must run and summarize:

- **HF Space boot test:** `python app.py` runs locally; Space deploys with no missing deps.
- **Embed check:** Google Sites embed instructions verified (iframe snippet + publish instructions).
- **Widget check:** HTML/JS widget loads, handles API errors safely, and logs telemetry.
- **Two projects run:** Both advanced exercises install and run locally with documented commands.
- **Security lint:** No secrets in repo; environment variables documented in `.env.example`.

---


## 🔧 Build Tasks (what Codex must generate)

### 1) Hugging Face Space — Basic (Gradio)

A minimal Gradio app (`/scaffolds/hf_space_basic`) with:

- Text input, selectable model provider, and streaming output.
- `.env.example` for API keys; never hardcode secrets.
- `requirements.txt` pinned; `README.md` with “Deploy to HF” steps.
- Include a basic test script to hit the space locally.

### 2) Hugging Face Space — Multimodal

A richer Gradio app (`/scaffolds/hf_space_multimodal`) that:

- Accepts image upload + prompt; returns caption or edited image.
- Provides a safe queue and rate limiting sample.
- Adds a small dataset cache folder for demo inputs.
- Includes a license note and content-safety disclaimer.

### 3) Google Sites Integration

A clear instructions doc (`/course/modules/03_agents/learner_guide.md`) describing:

- Publishing the HF Space and retrieving the public URL.
- Embedding in Google Sites (iframe or link-out).
- Uploading generated assets (logo/banner) and linking to the Space.
- Accessibility tips (contrast, alt text, focus order).

### 4) Custom HTML/JS Widget (Vanilla)

A standalone widget (`/scaffolds/widget_html_js`) that:

- Renders a small UI (input, button, output panel).
- Calls a serverless proxy endpoint; no keys in client.
- Implements robust error handling and telemetry.
- Ships with a minimal Node/Express proxy (`/api/proxy.js`) and instructions.

### 5) Optional Next.js Embed Demo

A tiny Next.js embed demo (`/scaffolds/next_embed_demo`) that:

- Shows multiple embed patterns (iframe, link-out, modal overlay).
- Contains an a11y-first layout and keyboard handlers.

---


## 🧪 Two Advanced Exercises (must run inside the course)

### 1) Autonomous Researcher Lite

- Inputs: company name or topic.
- Behavior: fetches 3–5 reputable sources, summarizes, produces a draft brief.
- Output: `/outputs/research_{slug}.md` + optional chart.
- Safety: domain allowlist + request budget; no scraping blocked sites.

### 2) Multimodal Storycard Generator

- Inputs: theme, tone, and up to 3 images.
- Behavior: composes a storycard (title + sections) + optional generated image.
- Output: static HTML card + downloadable PNG render.
- Safety: gated image gen; include “no real people” default.

Each exercise gets:

- A scaffold in `/course/modules/03_agents/exercises/...`
- A matching solution in `/course/modules/03_agents/solutions/...`
- A short rubric and checklist.

---


## 🖼️ Asset Generation (images/logos)

- Provide a small image-gen helper (API stub or local pipeline) to create banners/logos.
- Export web-optimized assets (WebP/PNG) and include alt text guidance.
- Place assets in `/course/modules/03_agents/assets/...`

---


## 🔐 Security & Privacy

- No secrets in repo.
- Use `.env.example` and document variable names.
- Use server proxy for API calls; never expose keys in client.
- Add a short privacy note in `README.md` covering telemetry and logs.

---


## 📊 Telemetry & QA

- `telemetry.json`: record template ids, timings, environment.
- `qa_report.md`: list tests, results, and patches applied.
- `project_manifest.json`: exact file tree + sha256 checksums.

---


## ▶️ Run & Deploy (must be documented in /README.md)

- Local run commands for each scaffold (HF Spaces, widget, Next demo).
- “Deploy to Hugging Face” steps.
- Google Sites publish + embed instructions.
- Troubleshooting for CORS, 403, mixed content, iframe blocking.

---


**That’s it**  
- The instructions stay in Markdown (this file).  
- All generated artifacts are real files, emitted with the START/END file delimiters — no Markdown code fences.  
- Use any language or framework needed to satisfy the build tasks.
"""

# Write the content to a .md file
output_path = Path("/mnt/data/agents.md")
output_path.write_text(content)

output_path
