<div align="center">
  <h1>HERscope</h1>
  <p><strong>Women's health, on your terms.</strong></p>
  <p>A browser-based women's health companion for period tracking, symptom journaling, health insights, visual references, and optional AI-assisted conversations.</p>
  <p>
    <img alt="Status: Hackathon prototype" src="https://img.shields.io/badge/status-hackathon%20prototype-7650d8">
    <img alt="Interface: Responsive web app" src="https://img.shields.io/badge/interface-responsive%20web%20app-a58af4">
    <img alt="AI: Optional local Ollama" src="https://img.shields.io/badge/AI-optional%20local%20Ollama-36a58a">
  </p>
</div>

---

## Overview

HERscope is a women's health tracking and education prototype designed to help users record symptoms, view cycle estimates, identify patterns in their own logs, and organise information they may want to discuss with a qualified healthcare professional.

The project was built for **recHERsion 2026**, the women-only online hackathon organised by ACM-W, NITK Surathkal, as part of Engineer NITK 2K26.

![HERscope feature overview](assets/feature-overview.svg)

## The problem

Health symptoms and cycle changes can be difficult to remember and describe over time. HERscope brings personal logs and cycle information into one place so users can review their records and prepare for more informed healthcare conversations.

## Key features

- **Period tracker:** Calendar-based period logging, cycle history, configurable typical cycle and period lengths, and estimated period and ovulation windows.
- **Daily symptom journal:** Record a date, mood, symptoms, severity, and optional notes. Entries can be added for past dates.
- **Health insights:** Review logged symptom trends over selectable time ranges and summaries based on saved entries.
- **Visual symptom guide:** Browse visual reference content and compare symptom-related information. This is educational and not a diagnostic tool.
- **HERscope AI:** Optional chat integration with a locally running Ollama instance. The endpoint and model are configurable in the app.
- **Health reports:** Organise a symptom-based summary for personal review or discussion with a clinician.
- **Clinician discovery:** A section to help users explore care options.
- **Profile and preferences:** Browser-based demo profile and settings.
- **Responsive interface:** Desktop navigation and a mobile-friendly layout.

Features and estimates depend on the data entered by the user. Cycle predictions and AI responses are not medical diagnoses and should not be treated as a substitute for professional care.

## Screenshots and demo

The feature overview above is a project illustration. Add genuine screenshots of the running prototype here before final submission so reviewers can see the implemented interface.

| Home dashboard | Period tracker | Symptom journal |
|---|---|---|
| `assets/home.png` | `assets/period-tracker.png` | `assets/symptom-journal.png` |

**Demo video:** `ADD_DEMO_VIDEO_LINK`

**Project presentation:** `ADD_PRESENTATION_LINK`

Replace the placeholders with working, publicly accessible links before submitting. The recHERsion rulebook requires a GitHub repository, a project presentation, and a demo video.

## Technology

- HTML5
- CSS3, including responsive layouts
- Vanilla JavaScript
- Browser `localStorage` for demo records and settings
- Ollama API for optional local AI chat (`/api/tags` and `/api/chat`)

The supplied prototype is a single-page HTML application. It does not require a JavaScript package installation to open the interface.

## Run locally

### 1. Download or clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>
```

### 2. Open the application

Open `index.html` in a modern browser. If your file has a different name, open that HTML file instead.

For a local static server, you can also run:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000` and open the page served from the project directory.

### 3. Enable the optional AI assistant

The AI assistant is optional. To use it, install and run [Ollama](https://ollama.com/), pull a model, and start the local Ollama service. For example:

```bash
ollama pull qwen2.5:3b
ollama serve
```

In HERscope's AI settings, use the endpoint `http://localhost:11434` and model name `qwen2.5:3b`, or enter the endpoint and model you have configured. Use the app's connection test to check connectivity.

**Browser note:** Direct requests from a page opened as `file://` may be restricted by browser security or Ollama's CORS configuration. If the connection fails, serve the page over localhost and configure Ollama/browser access appropriately. Do not expose a local model endpoint publicly without understanding the security implications.

## Data and privacy

- Journal entries and settings are stored in the current browser using `localStorage` for this prototype.
- Browser-local data is not automatically synced across devices or browsers.
- Clearing browser site data may remove saved records.
- The AI assistant can optionally use saved app data as context when that setting is enabled. Review the setting before sending sensitive information to any model.
- This prototype does not automatically send records to a doctor.

Do not use the prototype as an emergency service or as a replacement for medical evaluation.

## Limitations

- Cycle, fertile-window, and ovulation dates are estimates based on user-entered dates and cycle settings. Calendar estimates cannot confirm ovulation or determine an individual's pregnancy probability.
- AI-generated content may be incomplete or incorrect. Verify health information with a qualified healthcare professional.
- Browser storage is intended for a demo, not as a secure medical-record system.
- Clinician information and other externally dependent features may require additional configuration or verification.

## Hackathon context

| Item | Details |
|---|---|
| Event | recHERsion 2026, women-only hackathon |
| Organiser | ACM-W, NITK Surathkal |
| Fest | Engineer NITK 2K26 |
| Event dates | 24–25 October 2026 |
| Mode | Online |
| Team size | 2–3 members |

The rulebook's evaluation criteria are problem relevance and understanding (15%), innovation and originality (15%), technical implementation (20%), working MVP and demonstration (25%), feasibility and potential impact (15%), and user experience and accessibility (10%). The working MVP category places particular emphasis on core functionality, end-to-end workflow, completeness/integration, and demonstration/validation.

## Responsible use

HERscope is a prototype for tracking and health education. It does not diagnose conditions, confirm pregnancy, or replace advice from a qualified clinician. Seek appropriate professional care for new, severe, persistent, or concerning symptoms. Urgent symptoms require timely medical attention.

## Acknowledgements

Built for recHERsion 2026, organised by ACM-W, NITK Surathkal, as part of Engineer NITK 2K26. Third-party libraries, models, APIs, and assets should be credited here as applicable to the final implementation.

---

<div align="center">
  <strong>HERscope</strong><br>
  Understand your body. On your terms.
</div>
