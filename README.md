# Ask a model about a country and the United States

Hackathon UI for a country's relationship to the United States. You pick a country. The FastAPI backend sends three prompts (sentiment, key figures, and a threat writeup) to a Llama 3.1 70B chat endpoint and expects JSON back. It does not query a threat database, a news API, or a live feed. The numbers and sources on the page are whatever the model returns.

The page was started with Josh, Sahil, and Sam at the SCSP x AGI House hackathon on 11/15/24. No license is added, because this is not sole-author work.

## Run the page locally

From `backend`, with the packages in `backend/requirements.txt` (FastAPI, Uvicorn, requests, python-dotenv, Pydantic):

```bash
pip install -r requirements.txt
uvicorn app.main:app --reload
```

From `frontend` (Next.js 15):

```bash
npm install
npm run dev
```

The API allows `http://localhost:3000`. `POST /analyze` takes `{"country": "France"}` and returns `sentiment`, `figures_events`, and `threats`.
