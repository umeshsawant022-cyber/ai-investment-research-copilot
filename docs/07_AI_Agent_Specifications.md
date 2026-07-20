# AI Agent Specifications

## Purpose

This document defines the AI agents that power AI Investment Research Copilot. Each agent is responsible for a specific task within the investment research workflow and is coordinated by a central Workflow Orchestrator.

---

# Multi-Agent Architecture

```text
User Request

↓

Workflow Orchestrator

├── Market Data Agent
├── Financial Analysis Agent
├── Technical Analysis Agent
├── News & Sentiment Agent
├── Document Retrieval Agent (RAG)
├── Investment Research Agent
└── Report Generation Agent

↓

Human Review
```

---

# 1. Market Data Agent

## Purpose

Retrieve market data required for investment analysis.

### Responsibilities

- Retrieve current stock price
- Retrieve historical price data
- Retrieve trading volume
- Retrieve market capitalization
- Retrieve sector and industry information

### Inputs

- Company name
- Stock ticker

### Outputs

- Structured market data

### Data Sources

- Yahoo Finance
- Alpha Vantage
- Polygon.io (future)

---

# 2. Financial Analysis Agent

## Purpose

Analyze company financial performance.

### Responsibilities

- Analyze Income Statement
- Analyze Balance Sheet
- Analyze Cash Flow Statement
- Calculate financial ratios
- Identify revenue and profit trends

### Inputs

- Financial statements

### Outputs

- Financial analysis summary
- Key financial metrics

---

# 3. Technical Analysis Agent

## Purpose

Evaluate historical price trends and technical indicators.

### Responsibilities

Calculate and interpret:

- RSI
- MACD
- Moving Averages
- Bollinger Bands
- Support & Resistance
- Volume Trends

### Inputs

- Historical market data

### Outputs

- Technical analysis summary
- Trend interpretation

---

# 4. News & Sentiment Agent

## Purpose

Summarize recent company and market developments.

### Responsibilities

- Retrieve recent news
- Summarize major events
- Classify sentiment
- Highlight opportunities and risks

### Inputs

- News articles
- Financial news feeds

### Outputs

- News summary
- Sentiment assessment

---

# 5. Document Retrieval Agent (RAG)

## Purpose

Retrieve relevant company documents to provide factual context for the LLM.

### Responsibilities

Retrieve and rank relevant sections from:

- Annual Reports
- Quarterly Reports
- Earnings Call Transcripts
- Investor Presentations

### Inputs

- Company name
- User query

### Outputs

- Relevant document excerpts

### Technology

- OpenAI Embeddings
- ChromaDB
- Retrieval-Augmented Generation (RAG)

---

# 6. Investment Research Agent

## Purpose

Generate an explainable investment research report by combining outputs from all previous agents.

### Responsibilities

- Assess financial health
- Interpret technical signals
- Summarize news
- Identify opportunities
- Identify risks
- Generate confidence score
- Produce investment outlook

### Inputs

- Market data
- Financial analysis
- Technical analysis
- News summary
- Retrieved documents

### Outputs

- Comprehensive investment research report

---

# 7. Report Generation Agent

## Purpose

Format AI-generated insights into a structured, user-friendly report.

### Responsibilities

Generate:

- Executive Summary
- Company Overview
- Financial Analysis
- Technical Analysis
- News Summary
- Risk Assessment
- Opportunities
- Investment Outlook
- Confidence Score

### Outputs

- Investment Research Report (PDF/HTML in future)

---

# Workflow Orchestrator

The Workflow Orchestrator coordinates all agents by:

- Receiving user requests
- Invoking the appropriate agents
- Managing execution order
- Aggregating outputs
- Sending consolidated results to the Investment Research Agent

Agents do not communicate directly with one another; all coordination occurs through the Workflow Orchestrator.

---

# Design Principles

The AI architecture follows these principles:

- Modular agent design
- Clear separation of responsibilities
- Explainable AI outputs
- Retrieval-Augmented Generation (RAG)
- Human-in-the-loop review
- Scalable workflow orchestration

---

# Future AI Agents

Potential future agents include:

- Portfolio Monitoring Agent
- ESG Analysis Agent
- Macro-Economic Analysis Agent
- Earnings Forecast Agent
- Peer Comparison Agent
- Portfolio Optimization Agent
- Alert & Notification Agent
