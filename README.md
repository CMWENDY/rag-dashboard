# GitLab Benefits Q&A — Dashboard

A Streamlit dashboard for a Retrieval-Augmented Generation (RAG) system with hybrid search
(dense + BM25), citation verification, and confidence scoring.

This repo is **just the dashboard** (deployed on Streamlit Community Cloud). It calls a separate
FastAPI backend hosted on Google Cloud Run.

- **Live demo:** [DEMO](https://rag-dashboard-wcm.streamlit.app/)
- **API backend + full source (FastAPI, Docker, retrieval pipeline):** main repo url

## Configuration
Set one secret in Streamlit Cloud (**Advanced settings → Secrets**):

```toml
API_URL = "https://rag-api-751441988751.us-central1.run.app"
```

The app reads it via `st.secrets["API_URL"]`, falling back to `http://127.0.0.1:8000` for local runs.

## Run locally
```bash
pip install -r requirements.txt
API_URL="https://rag-api-751441988751.us-central1.run.app" streamlit run dashboard.py
```
