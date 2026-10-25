<div align="center">

# HERscope

**Women's health, on your terms.**

A browser-based women's health companion for period tracking, symptom journaling, personal health insights, a visual symptom guide, and optional private AI-assisted conversations.

![Status](https://img.shields.io/badge/status-hackathon%20prototype-7650d8)
![Stack](https://img.shields.io/badge/stack-HTML%20%7C%20CSS%20%7C%20Vanilla%20JS-a58af4)
![Dependencies](https://img.shields.io/badge/dependencies-none-36a58a)
![AI](https://img.shields.io/badge/AI-optional%20local%20Ollama-36a58a)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

Built for **recHERsion 2026**, the women-only online hackathon by ACM-W, NITK Surathkal (Engineer NITK 2K26).
Problem Statement: **PS1, Women's Healthcare**

</div>

---

## Quick links

| Deliverable | Link |
|---|---|
| GitHub repository | [https://github.com/Naisha-0607/HERscope](https://github.com/Naisha-0607/HERscope) |
| Demo video (Google Drive) | [Watch the demo](https://drive.google.com/file/d/1e45Pkc3KQrP_6sFe-564zY6wVWzwv1Gb/view?usp=sharing) |

---

## Table of contents

1. [Problem statement](#problem-statement)
2. [Our solution](#our-solution)
3. [Features](#features)
4. [Screenshots](#screenshots)
5. [Tech stack and dependencies](#tech-stack-and-dependencies)
6. [Setup and run](#setup-and-run)
7. [How to use (demo walkthrough)](#how-to-use-demo-walkthrough)
8. [Project structure](#project-structure)
9. [Data and privacy](#data-and-privacy)
10. [Limitations](#limitations)
11. [Future scope](#future-scope)
12. [License and acknowledgements](#license-and-acknowledgements)

---

## Problem statement

Symptoms and cycle changes are hard to remember accurately over weeks or months. In a short appointment, many women struggle to describe what happened, when it started, and how severe it was. Existing tools tend to be either simple period calendars or generic health content, and few help a user turn their own records into something they can discuss with a clinician.

## Our solution

HERscope brings cycle tracking, daily symptom logs, trend insights, visual references, and a clinician-ready summary into one private, easy-to-use web app. It runs entirely in the browser, needs no account or server, and keeps data on the user's own device. An optional AI assistant runs on a **local** Ollama model, so health conversations do not have to leave the user's machine.

HERscope is designed to help users **understand and prepare**. It does not diagnose.

---

## Features

| Feature | What it does |
|---|---|
| **Home dashboard** | Daily check-in, health-at-a-glance summary, and quick actions. |
| **Period tracker** | Calendar-based period logging, cycle history, configurable typical cycle and period lengths, and estimated period, fertile-window, and ovulation dates. |
| **Daily symptom journal** | Log date, mood, symptoms, severity, and optional notes. Past dates can be backfilled. Recent entries are listed for review. |
| **Health insights** | Symptom trends over selectable time ranges and summaries built from the user's saved entries. Includes age-specific insight content. |
| **Visual symptom guide** | Browse and compare visual references for symptom-related information (educational only). |
| **HERscope AI** | Optional chat with a locally running Ollama model. Endpoint and model are configurable, with a built-in connection test. Saved app data can optionally be used as context. |
| **Health report** | A symptom-based concern and urgency summary that the user can preview and download, to discuss with a clinician. |
| **Find a gynaecologist** | A section to help users explore care options. |
| **Notifications** | Reminder and notification preferences. |
| **Profile and privacy controls** | Local demo profile, preferences, and account and data controls. |
| **Responsive design** | Sidebar navigation on desktop and a mobile-friendly layout. |

> All estimates and AI responses depend on user-entered data and are **not** medical diagnoses.

---

## Screenshots

| Home dashboard | Period tracker | Symptom journal |
|---|---|---|
| ![Home dashboard](assets/home.png) | ![Period tracker](assets/period-tracker.png) | ![Symptom journal](assets/symptom-journal.png) |

| Health insights | Visual symptom guide | HERscope AI |
|---|---|---|
| ![Health insights](assets/insights.png) | ![Visual symptom guide](assets/visual-guide.png) | ![HERscope AI](assets/ai-chat.png) |

| Health report |
|---|
| ![Health report](assets/health-report.png) |

*Screenshots use sample demo data.*

---

## Tech stack and dependencies

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (custom properties, grid, responsive layouts) |
| Logic | Vanilla JavaScript (no framework) |
| Storage | Browser `localStorage` |
| Optional AI | [Ollama](https://ollama.com/) local API (`/api/tags`, `/api/chat`) |

**Dependencies**

- **Required:** only a modern web browser (Chrome, Edge, Firefox, or Safari). There is **nothing to install**: no `npm install`, no build step, and no external CDN or API calls.
- **Optional (for the AI assistant only):** Ollama and one downloaded model, for example `qwen2.5:3b`.
- **Optional (for a local server):** Python 3, used only to serve the folder over `localhost`.

---

## Setup and run

### 1. Get the code

```bash
git clone https://github.com/Naisha-0607/HERscope.git
cd HERscope
```

Or use **Code → Download ZIP** on GitHub and extract it.

### 2. Run the app

**Option A: open the file directly**

Double-click `index.html`, or open it from your browser with **File → Open**.

**Option B: serve it on localhost (recommended, and required for AI chat)**

```bash
python -m http.server 8000
```

Then visit <http://localhost:8000>.

(Use `python3` instead of `python` if needed on macOS or Linux.)

### 3. (Optional) Enable the AI assistant

The app is fully usable without this step.

```bash
# 1. Install Ollama from https://ollama.com/
# 2. Download a small model
ollama pull qwen2.5:3b

# 3. Start the service (skip if Ollama is already running in the background)
ollama serve
```

Then in HERscope, open **HERscope AI** and enter:

- **Endpoint:** `http://localhost:11434`
- **Model:** `qwen2.5:3b` (or any model you have pulled)

Click the connection test to verify.

**Troubleshooting the connection**

- Pages opened as `file://` can be blocked by browser security or Ollama's CORS rules. Serve the app with Option B.
- If the browser still blocks the request, allow the page's origin using Ollama's `OLLAMA_ORIGINS` environment variable, for example:
  ```bash
  OLLAMA_ORIGINS="http://localhost:8000" ollama serve
  ```
- Do not expose a local model endpoint publicly without understanding the security implications.

---

## How to use (demo walkthrough)

1. **Create a local profile** on the sign-in screen (stored only in your browser).
2. **Set cycle settings** (typical cycle length and period length) on the period tracker.
3. **Log a period** on the calendar and see the estimated next period, fertile window, and ovulation dates update.
4. **Add a symptom check-in** in the journal: pick a date, mood, symptoms, severity, and a note. Add a few entries across different dates.
5. **Open Health insights** and switch time ranges to see symptom trends from your logs.
6. **Browse the Visual symptom guide** to compare symptom references.
7. **Generate a Health report** to preview and download a summary you can take to a clinician.
8. **(Optional) Ask HERscope AI** a question about your logs once Ollama is connected.

---

## Project structure

```text
.
├── index.html        # Complete single-page application (HTML, CSS, JavaScript)
├── assets/           # Screenshots used in this README
├── LICENSE           # MIT License
└── README.md         # This file
```

---

## Data and privacy

- Profile, journal entries, and settings are stored in the current browser's `localStorage`.
- Nothing is uploaded to a server. HERscope has no backend and no analytics.
- Data is not synced between devices or browsers, and clearing site data removes saved records.
- The AI assistant talks only to the Ollama endpoint you configure (by default on your own computer). It can optionally use saved app data as context, so review that setting before sending sensitive information to any model.
- The prototype does **not** send records to any doctor automatically.

---

## Limitations

- Cycle, fertile-window, and ovulation dates are **estimates** from user-entered dates and settings. They cannot confirm ovulation or an individual's chance of pregnancy.
- AI-generated content may be incomplete or wrong. Always verify health information with a qualified healthcare professional.
- `localStorage` is suitable for a demo, not as a secure medical-record system.
- Clinician listings and other externally dependent features may need extra configuration or verification.
- The AI assistant requires a separately installed local Ollama setup.

---

## Future scope

- Encrypted cloud backup and cross-device sync with user-controlled consent
- Verified clinician directory with appointment booking
- Exportable PDF reports and secure sharing with a doctor
- Multilingual support for wider accessibility in India
- Screen-reader and accessibility audits
- Clinician-reviewed symptom and urgency content

---

## Responsible use

HERscope is a prototype for tracking and health education. It does not diagnose conditions, confirm pregnancy, or replace advice from a qualified clinician. Seek professional care for new, severe, persistent, or concerning symptoms. Urgent symptoms need timely medical attention, so contact local emergency services.

---

## License and acknowledgements

Released under the [MIT License](LICENSE).

Built for **recHERsion 2026**, organised by **ACM-W, NITK Surathkal**, as part of **Engineer NITK 2K26**. The optional AI feature uses [Ollama](https://ollama.com/) and open models such as Qwen.

---

<div align="center">
  <strong>HERscope</strong><br>
  Understand your body. On your terms.
</div>
