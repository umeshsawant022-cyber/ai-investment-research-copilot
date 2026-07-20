# Product Workflow

## Purpose

This document describes the end-to-end system workflow of AI Investment Research Copilot. It illustrates how user requests are processed through AI services, financial data providers, and workflow orchestration to generate explainable investment research.

---

# Workflow Overview

```text
User

↓

Search Company

↓

Workflow Orchestrator

↓

Retrieve Market Data

↓

Retrieve Financial Statements

↓

Retrieve Company News

↓

Calculate Technical Indicators

↓

Retrieve Company Filings (RAG)

↓

LLM Analysis

↓

Generate Investment Research Report

↓

Human Review

↓

Export / Save Report
```

---

# Workflow Steps

## Step 1: Company Search

### User Action

The user searches for a publicly listed company.

### System Actions

- Validate company name or ticker symbol.
- Retrieve company profile.
- Initialize the research workflow.

---

## Step 2: Market Data Retrieval

The platform retrieves current and historical market information, including:

- Stock price
- Volume
- Market capitalization
- Historical price data
- Sector information

---

## Step 3: Financial Statement Retrieval

The platform collects publicly available financial information, including:

- Income Statement
- Balance Sheet
- Cash Flow Statement
- Quarterly Results
- Annual Reports

---

## Step 4: Technical Indicator Calculation

Using historical market data, the platform calculates:

- RSI
- MACD
- Moving Averages
- Bollinger Bands
- Support & Resistance
- Trading Volume Trends

---

## Step 5: News & Market Intelligence

The platform retrieves:

- Recent company news
- Industry news
- Earnings announcements
- Major business events

The information is summarized for investment research.

---

## Step 6: Document Retrieval (RAG)

Relevant company documents are retrieved, including:

- Annual Reports
- Quarterly Reports
- Earnings Call Transcripts
- Investor Presentations

The retrieved content provides factual context for the LLM.

---

## Step 7: AI Analysis

The LLM combines structured financial data and retrieved documents to generate:

- Company overview
- Financial health assessment
- Technical trend interpretation
- News summary
- Opportunities
- Risks
- Investment outlook
- Confidence score

---

## Step 8: Report Generation

The platform generates a structured investment research report containing:

- Executive Summary
- Financial Analysis
- Technical Analysis
- News Summary
- Risk Assessment
- Opportunities
- Overall Outlook

---

## Step 9: Human Review

The user reviews the AI-generated report and supporting evidence before making any investment decision.

The platform provides decision support only and does not execute trades.

---

## Step 10: Export

Users may:

- Download the report
- Save the report
- Share the report
- Revisit previous analyses

---

# Workflow Principles

The workflow is designed to:

- Automate repetitive research tasks
- Use trusted financial data
- Ground AI responses with retrieved documents (RAG)
- Present explainable AI outputs
- Keep the user in control of investment decisions

---

# Expected Outcomes

The workflow enables users to:

- Reduce investment research time
- Consolidate information from multiple sources
- Improve consistency in financial analysis
- Generate structured investment research reports
- Support informed, explainable investment decisions
