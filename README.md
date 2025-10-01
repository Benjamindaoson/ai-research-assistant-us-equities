📊 AI Research Assistant for US Equities

An AI-powered research copilot designed for equity research and investment insights.
This system integrates market data, signals (news & announcements), and filing analysis into a unified workflow, producing structured, auditable, and decision-ready outputs.

🔑 Key Features

Intent Router
Automatically routes user queries into four agents:

📈 Price Agent → Fetches market data (Yahoo Finance), charts, and KPIs.

📰 Signals Agent → Aggregates company news & announcements (Finnhub, DuckDuckGo fallback), LLM-based summarization & sentiment classification.

📑 Filings Agent (RAG) → Ingests SEC 10-K/10-Q filings from PDF or URL, builds FAISS vector indexes with page-aware metadata, and enables retrieval-augmented QA.

🤖 Analysis Agent → Synthesizes insights across price, signals, and filings into structured research notes.

📊 KPI Agent → Logs latency, cache usage, query counts, ensuring performance and compliance auditability.

Market Data Module

Yahoo Finance integration (price, volume, performance).

Plotly charts with performance metrics.

Local caching + PNG export.

Signals Module (News + Announcements)

Primary source: Finnhub API.

Fallback: DuckDuckGo Search.

LLM enrichment: summarization + sentiment analysis.

Local cache with timestamp.

Filings Module (RAG-based)

SEC 10-K/10-Q ingestion (PDF or SEC.gov URL).

Recursive text splitting + FAISS vector store.

Page-aware metadata for auditable sources.

LLM-powered Q&A over filings.

Analysis Module

LLM synthesis of price, news, and filings.

Strict JSON output (summary, opportunities, risks).

Downloadable research memo (Markdown).

KPI & Audit

CSV logging (latency, intent, sources count, cache usage).

KPI monitor tab for average latency, cache hit ratio, total queries.

Structured JSON outputs for downstream integration.

Notebook View

Transparent "how it works" demo with step-by-step pipeline explanation.

Useful for evaluations, pitches, or training.

🏗️ Architecture
User Query → Intent Router
    ├─ Price Agent (Market Data)
    ├─ Signals Agent (News + Announcements)
    ├─ Filings Agent (SEC RAG)
    └─ Analysis Agent (LLM Synthesis)
        └─ KPI Agent (Monitoring & Audit)

⚙️ Tech Stack

Frontend: Streamlit + Plotly

Data Sources: Yahoo Finance, Finnhub API, DuckDuckGo, SEC.gov

LLMs & Embeddings: OpenAI GPT-4o-mini, Tongyi Qwen-Max, DashScope / OpenAI embeddings

Vector Store: FAISS

Evaluation: RAGAS metrics (faithfulness, recall, precision, relevancy)

Logging: CSV-based KPI monitoring

🚀 Usage
pip install -r requirements.txt
streamlit run streamlit_app_full.py


Environment variables:

OPENAI_API_KEY or DASHSCOPE_API_KEY (LLM provider)

FINNHUB_API_KEY (optional, for primary news source)

📌 Roadmap

 Multi-ticker batch research reports

 Sentiment scoring over multi-source signals

 Extended KPI dashboard (response time, model costs)

 Export to PDF & Excel for institutional workflows
