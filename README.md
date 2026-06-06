# AI Calendar Scheduler
> Built for GDG Doha — Build with AI Show & Tell

A single-file web app that converts natural language into Google Calendar events using the Gemini API. No more manually filling in date, time, and location fields — just describe your event the way you'd say it out loud.

---

## Demo

> *"DSAI lab exam on Tuesday 9th, SQL and Python, 11am to 1pm"*
> *"عندي اجتماع مع المشرف غداً الساعة 3 العصر في مبنى A"*
> *"SRP poster due Wednesday 10th at 10:30am, start today"*

Gemini parses the text → preview card appears → one click saves it to Google Calendar.

---

## Features

- **Natural language parsing** — messy, casual input works fine
- **Voice input** — tap the mic, speak, done
- **Arabic + English support** — handles mixed language input natively
- **Smart date resolution** — understands "tomorrow", "next Tuesday", multi-day spans
- **Live Google Calendar integration** — creates the event directly, no copy-pasting
- **Preview before saving** — always see what you're adding before it goes in

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript (single file, zero frameworks) |
| AI / NLP | Gemini API (`gemini-2.5-flash`) with JSON mode |
| Calendar | Google Calendar API v3 |
| Auth | Google Identity Services (OAuth 2.0) |
| Voice | Web Speech API (native browser) |

---

## Setup

### 1. Get your API keys

| Key | Where to get it |
|---|---|
| `GEMINI_API_KEY` | [Google AI Studio](https://aistudio.google.com) → Get API Key |
| `GOOGLE_CLIENT_ID` | [Google Cloud Console](https://console.cloud.google.com) → Credentials → OAuth Client ID |
| `GOOGLE_API_KEY` | Google Cloud Console → Credentials → API Key (restrict to Calendar API) |

### 2. Configure OAuth

In Google Cloud Console → OAuth Client ID → Authorized JavaScript origins, add:
```
http://localhost
http://127.0.0.1
http://127.0.0.1:5500
```

In OAuth consent screen → Test users, add your Gmail address.

### 3. Run locally

1. Clone the repo
2. Open `index.html` in VS Code
3. Paste your API keys into the three config variables at the top of the script
4. Right-click → **Open with Live Server**
5. Connect your Google Calendar and start scheduling

---

## Why I Built This

Managing an academic schedule means constantly switching between apps, reformatting your own thoughts into rigid calendar fields, and repeating the same manual steps. This app removes that friction — describe your event the way you'd text a friend and let Gemini handle the rest.

---

## Project Structure

```
ai-calendar/
├── index.html    # Entire app — UI, Gemini logic, Calendar API
└── README.md
```

---

Built by [Maymona Mustafa](https://github.com/Maymona-M) · BSc Data Science & AI, UDST