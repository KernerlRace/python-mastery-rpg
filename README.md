# Python Mastery RPG

A gamified platform for learning Python, built in **48 hours** at a University of Winchester hackathon.

Instead of reading tutorials, you write real Python in the browser to defeat "syntax monsters".
Every solved quest gives XP and gold, unlocks ranks and items, and moves you up the leaderboard.
When you get stuck, an LLM-powered mentor gives a hint instead of the answer.

## Features

- **Code Arena** — an in-browser editor (Ace) where each quest is checked by running your code against a test.
- **11 quests** covering variables, lists, loops, conditionals, exceptions, functions, files, testing, OOP, GUI and SQL.
- **Infinite Tower** — an endless mode with generated tasks after the main quest line.
- **Progression** — XP, ranks, gold, a shop with themes and avatars, daily quests and hidden achievements.
- **Analytics** — a radar chart of skills by category and a gold history chart (Plotly).
- **Hall of Fame** — a global top-10 leaderboard.
- **Copilot Duck** — a mentor chatbot: built-in hints for every quest, with a fallback to an LLM through the OpenRouter API.
- **Accounts** — registration and login with salted SHA-256 password hashes, progress stored in SQLite.
- **Shareable hero card** — a PNG generated with Pillow.
- **Themes** — Dracula, Monokai, One Dark, SynthWave '84 and the unlockable Matrix Hacker.

## Tech stack

Python · Streamlit · SQLite · pandas · Plotly · Pillow · streamlit-ace · OpenAI SDK (OpenRouter)

## Run locally

```bash
pip install -r requirements.txt
streamlit run rpg_app.py
```

The mentor's LLM fallback needs an OpenRouter key. Either set an environment variable:

```bash
export OPENROUTER_API_KEY="sk-or-..."
```

or copy `.streamlit/secrets.toml.example` to `.streamlit/secrets.toml` and put the key there.
The game itself works without a key; only free-form questions to the mentor need it.

## Project structure

| File | Purpose |
|---|---|
| `rpg_app.py` | The whole Streamlit app: auth, quests, shop, analytics, leaderboard, mentor |
| `index.html` | Landing page |
| `bonk.mp3`, `door.mp3` | Sound effects for failed and passed quests |

## Team

Built by a student team at the University of Winchester hackathon, 2026.
