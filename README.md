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

## What we'll cover

| Part | Topic | What you'll build |
|---|---|---|
| 1 | Your first LLM call | A working API call in three lines |
| 2 | Prompting | System instructions, temperature, JSON output |
| 3 | Multi-turn chat | A conversation that remembers |
| 4 | RAG from scratch | Retrieval over your own documents, in numpy |
| 5 | Agents | A model that calls your Python functions |

No prior experience with AI or Python is required. Everything either runs as-is or
has a clearly marked `TODO` for you to fill in.

---

## What's in here

| File | What it is |
|---|---|
| `workshop.ipynb` | The notebook you'll work in, with `TODO` gaps |
| `solutions.ipynb` | Identical, with every TODO completed |
| `requirements.txt` | The Python packages we use |
| `.devcontainer/` | Configures Codespaces automatically — you can ignore this |

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

## Troubleshooting

| Problem | Fix |
|---|---|
| `429 RESOURCE_EXHAUSTED` | You've hit the free-tier limit. Wait 60 seconds and re-run, or switch to Groq using the appendix cell at the end of the notebook. |
| `API key not valid` | Re-paste the key between the existing quotes only — no extra quotes or spaces. |
| Codespace won't build | Try creating a fresh one. If it still fails, ask the instructor to share theirs. |
| `ModuleNotFoundError` | Re-run the first cell (the `%pip install` one) and wait for it to finish. |
| Model name errors | This repo uses `gemini-2.5-flash`. Older tutorials online reference retired models. |
| `import google.generativeai` errors | That's the deprecated SDK. This repo uses `from google import genai`. |

---

## Where to go next

- [Hugging Face Agents Course](https://huggingface.co/learn/agents-course) — free, hands-on, Apache-2.0
- [Gemini API docs](https://ai.google.dev/gemini-api/docs)
- LangChain, LlamaIndex, smolagents and PydanticAI are the frameworks worth
  learning once you understand what we build here by hand.

**One safety note:** free-tier prompts may be used to improve the provider's models.
Never paste customer data, credentials or anything confidential into a free-tier API.
