# System Architecture

## Purpose

This document describes the high-level architecture of AI Investment Research Copilot, including the major system components, data flow, external integrations, and AI services that enable explainable investment research.

---

# High-Level Architecture

```text
                            +----------------------+
                            |        User          |
                            +----------+-----------+
                                       |
                                       ▼
                            +----------------------+
                            |   Streamlit Frontend |
                            +----------+-----------+
                                       |
                                       ▼
                            +----------------------+
                            |    FastAPI Backend   |
                            +----------+-----------+
                                       |
                                       ▼
                        +-------------------------------+
                        |     Workflow Orchestrator     |
                        +---------------+---------------+
                                        |
        --------------------------------------------------------------------
        |               |                |               |                 |
        ▼               ▼                ▼               ▼                 ▼
+---------------+ +----------------+ +--------------+ +-------------+ +-------------------+
| Market Data   | | Financial      | | Technical    | | News &      | | Document Retrieval|
| Agent         | | Analysis Agent | | Analysis     | | Sentiment   | | Agent (RAG)       |
+-------+-------+ +--------+-------+ | Agent        | | Agent       | +---------+---------+
        |                  |         +------+-------+ +------+------+
        |                  |                |                |
        |                  |                |                |
        --------------------------------------------------------------------
                                        |
                                        ▼
                        +-------------------------------+
                        | Investment Research Agent     |
                        +---------------+---------------+
                                        |
                                        ▼
                        +-------------------------------+
                        | Report Generation Agent       |
                        +---------------+---------------+
                                        |
                                        ▼
                              Investment Research Report
```

---

# System Components

## 1. Frontend

**Technology**

- Streamlit

### Responsibilities

- Company search
- Display investment reports
- User interaction
- Report export
- Human review

---

## 2. Backend API

**Technology**

- FastAPI

### Responsibilities

- Receive requests
- Authenticate users
- Call Workflow Orchestrator
- Manage API integrations
- Return generated reports

---

## 3. Workflow Orchestrator

Acts as the central coordinator.

Responsibilities:

- Execute AI workflow
- Trigger AI agents
- Aggregate results
- Handle failures
- Generate final workflow response

---

## 4. AI Agents

### Market Data Agent

Retrieves:

- Stock prices
- Historical data
- Market capitalization
- Trading volume

---

### Financial Analysis Agent

Analyzes:

- Income Statement
- Balance Sheet
- Cash Flow Statement
- Financial ratios

---

### Technical Analysis Agent

Calculates:

- RSI
- MACD
- Moving Averages
- Bollinger Bands
- Support & Resistance

---

### News & Sentiment Agent

Processes:

- Company news
- Industry news
- Earnings announcements
- Market sentiment

---

### Document Retrieval Agent (RAG)

Retrieves relevant information from:

- Annual Reports
- Quarterly Reports
- Earnings Call Transcripts
- Investor Presentations

Technology:

- OpenAI Embeddings
- ChromaDB

---

### Investment Research Agent

Combines outputs from all agents to generate:

- Financial insights
- Technical insights
- Risk analysis
- Opportunities
- Investment outlook
- Confidence score

---

### Report Generation Agent

Formats the final report into a structured output suitable for presentation and export.

---

# External Integrations

## Financial Market Data

Examples:

- Yahoo Finance
- Alpha Vantage
- Polygon.io (future)

---

## News Providers

Examples:

- NewsAPI
- Financial news feeds
- Company press releases

---

## AI Services

### Large Language Model

- OpenAI GPT

### Embeddings

- OpenAI Embeddings

---

## Vector Database

- ChromaDB

Used for Retrieval-Augmented Generation (RAG) over company filings and related documents.

---

# Data Flow

1. User searches for a company.
2. FastAPI forwards the request to the Workflow Orchestrator.
3. The orchestrator invokes Market Data, Financial Analysis, News, and RAG agents in parallel.
4. Technical Analysis runs after market data is retrieved.
5. All outputs are consolidated.
6. Investment Research Agent generates explainable insights.
7. Report Generation Agent formats the final report.
8. Streamlit displays the completed investment research report.

---

# Non-Functional Characteristics

The architecture is designed to support:

- Scalability
- Modular AI services
- Fault tolerance
- Explainable AI
- Secure API integrations
- Maintainability
- Extensibility

---

# Future Architecture Enhancements

Potential additions include:

- Authentication & authorization
- Portfolio watchlists
- Scheduled research jobs
- Notification service
- Report history
- Enterprise user management
- Cloud deployment (AWS/Azure/GCP)
- Monitoring and observability
