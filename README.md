# HireIQ - AutoApply AI Dashboard

HireIQ is a production-ready Streamlit app for AI-assisted job search workflows:
- Resume parsing and optimization with Gemini
- ATS scoring and improvement suggestions
- Job match discovery and ranking
- Application tracker with Excel import/export
- Optional Notion logging for admin analytics

## 1) Local Setup

### Prerequisites
- Python 3.10+
- `pip`

### Install
```bash
pip install -r requirements.txt
```

### Run
```bash
streamlit run app.py
```

---

## 2) Environment / Secrets Configuration

The app reads keys from Streamlit secrets (`st.secrets`) for secure deployment.

### A) Local development (`.streamlit/secrets.toml`)
Create:
```toml
GEMINI_API_KEY = "your_gemini_api_key"
NOTION_TOKEN = "your_notion_integration_token"
NOTION_DATABASE_ID = "your_notion_database_id"
```

### B) Optional `.env` for local convenience
If you prefer `.env`, create:
```env
GEMINI_API_KEY=your_gemini_api_key
NOTION_TOKEN=your_notion_integration_token
NOTION_DATABASE_ID=your_notion_database_id
```

Then map these to Streamlit secrets or load them before app start.

> Note: This project uses session state for all app data (no database).

---

## 3) Streamlit Cloud Deployment

1. Push the project to GitHub.
2. Open [Streamlit Community Cloud](https://share.streamlit.io/).
3. Click **New app** and select your repo/branch.
4. Set main file path to:
   - `app.py`
5. Add secrets in **App settings -> Secrets**:
```toml
GEMINI_API_KEY = "your_gemini_api_key"
NOTION_TOKEN = "your_notion_integration_token"
NOTION_DATABASE_ID = "your_notion_database_id"
```
6. Deploy and verify:
   - Dashboard loads
   - Resume upload works
   - Gemini analysis runs
   - Notion logs are written (if secrets configured)

---

## 4) Theme Config

Theme is defined in `.streamlit/config.toml`:
- dark base
- background `#080b12`
- primary blue `#3b82f6`
- sans-serif font
