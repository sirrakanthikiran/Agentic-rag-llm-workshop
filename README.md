# Agentic AI, RAG & LLMs — 2-Hour Hands-On Workshop

Build a working LLM app, a RAG system and an agent from scratch, in two hours,
in your browser. No Colab, no local installs, no paid API keys.

---

## Before the workshop (10 minutes, please do this in advance)

1. **Create a GitHub account** — [github.com/signup](https://github.com/signup). Free. This is how you'll run the code.
2. **Get a free Gemini API key** — go to [aistudio.google.com](https://aistudio.google.com), sign in with a Google account, click **Get API key**. No credit card needed. Copy the key somewhere you can paste from.
3. **Get a free Groq key as backup** — [console.groq.com](https://console.groq.com). Takes about 30 seconds, no card. We may not need it, but having it saves the day if Gemini rate-limits.
4. **Open this repo once** — click the green **Code** button → **Codespaces** → **Create codespace on main**. Wait for it to finish building, confirm you see VS Code in your browser, then close the tab. Doing this in advance means it's cached on the day.
5. **Bring a laptop**, not a tablet or phone. Chrome or Edge works best.

Nothing to install. If step 4 fails, tell the instructor before the session.

---

## On the day

1. Open this repo → **Code** → **Codespaces** → open your existing codespace.
2. Open `workshop.ipynb`.
3. Run the first cell. When you see `Setup OK`, you're ready.

`solutions.ipynb` has every answer filled in. Try the TODOs first — but if you get
stuck, open it rather than falling behind.

---

## What's in here

| File | What it is |
|---|---|
| `workshop.ipynb` | The participant notebook, with `TODO` gaps to fill in |
| `solutions.ipynb` | Identical, with every TODO completed |
| `requirements.txt` | Pinned dependencies |
| `.devcontainer/` | Auto-configures Codespaces, pre-downloads the embedding model |

---

## Run it locally instead (optional)

```bash
git clone <this-repo>
cd <this-repo>
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

---

## Instructor notes

### Run of show (120 min)

| Time | Segment | Notes |
|---|---|---|
| 0:00–0:10 | Setup check | **Gate.** Nobody moves on until every screen shows `Setup OK`. Pair people up now. |
| 0:10–0:20 | First API call | Talk light. Get them running code fast. |
| 0:20–0:40 | Prompting | System instruction, temperature, JSON output. First TODOs. |
| 0:40–0:45 | Break / buffer | |
| 0:45–1:00 | Multi-turn chat | The "no memory" demo lands well — run it live. |
| 1:00–1:35 | RAG from scratch | The core. Don't rush the embeddings intuition. |
| 1:35–1:40 | Break / buffer | |
| 1:40–2:05 | Agent with tools | The `4738 * 2913` failure → tool fix is the money moment. |
| 2:05–2:15 | Wrap-up + Q&A | |

### Setup and delivery

- **Pair programming.** Assign pairs at 0:05. A broken laptop then costs you one
  person's screen, not one person's participation.
- **Every participant uses their own API key.** Free-tier limits count per account,
  so a shared key will rate-limit the entire room at once.
- **Stagger the heavy cells.** If 30 people hit the API in the same 5 seconds you'll
  see 429s. Ask half the room to start, then the other half.
- **Keep a spare Codespace open** on your own account that a stuck participant can
  be invited into.

### Known failure modes

| Problem | Fix |
|---|---|
| `429 RESOURCE_EXHAUSTED` | Wait 60s, or switch to Groq (appendix cell in the notebook) |
| Someone pasted the key with quotes/spaces | Re-paste between the existing quotes only |
| Codespace won't build | Fall back to local install, or share your Codespace |
| Venue wifi dies | Pre-download `ollama pull llama3.2:3b` (~2 GB) on your machine and demo from the front |
| Model name errors | We use `gemini-2.5-flash`. Older tutorials reference retired models. |
| `import google.generativeai` | That's the deprecated SDK. This repo uses `from google import genai`. |

### Verify before the day

Model IDs and free-tier limits change often. The week before, run
`solutions.ipynb` end to end on a **fresh** account to confirm `gemini-2.5-flash`
is still current and the free tier still covers the session.
