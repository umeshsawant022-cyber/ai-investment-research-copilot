# API Specification

## Purpose

This document defines the REST APIs for AI Investment Research Copilot. These APIs enable communication between the frontend, backend, AI workflow, and external financial data providers.

---

# API Overview

| API | Method | Description |
|------|--------|-------------|
| /companies/search | GET | Search companies |
| /companies/{symbol} | GET | Retrieve company details |
| /market-data/{symbol} | GET | Retrieve market data |
| /financials/{symbol} | GET | Retrieve financial statements |
| /news/{symbol} | GET | Retrieve company news |
| /research/generate | POST | Generate investment research report |
| /reports | GET | Retrieve saved reports |
| /reports/{id} | GET | Retrieve a specific report |
| /reports/{id}/export | GET | Export report |

---

# Search Companies

## Endpoint

```http
GET /companies/search?q={company}
```

### Description

Search publicly listed companies.

### Example Response

```json
[
  {
    "symbol": "MSFT",
    "companyName": "Microsoft Corporation",
    "exchange": "NASDAQ"
  }
]
```

---

# Company Details

## Endpoint

```http
GET /companies/{symbol}
```

### Response

```json
{
  "symbol": "MSFT",
  "companyName": "Microsoft Corporation",
  "sector": "Technology",
  "industry": "Software"
}
```

---

# Market Data

## Endpoint

```http
GET /market-data/{symbol}
```

### Response

```json
{
  "currentPrice": 428.52,
  "marketCap": "3.2T",
  "volume": 25600000,
  "high": 432.10,
  "low": 424.80
}
```

---

# Financial Statements

## Endpoint

```http
GET /financials/{symbol}
```

### Response

```json
{
  "revenue": "245B",
  "netIncome": "88B",
  "eps": 11.80,
  "operatingMargin": "44%",
  "debtToEquity": 0.32
}
```

---

# Company News

## Endpoint

```http
GET /news/{symbol}
```

### Response

```json
[
  {
    "headline": "Microsoft Reports Strong Quarterly Earnings",
    "publishedDate": "2026-07-15",
    "sentiment": "Positive"
  }
]
```

---

# Generate Investment Research

## Endpoint

```http
POST /research/generate
```

### Request

```json
{
  "symbol": "MSFT",
  "investmentHorizon": "Long Term"
}
```

### Response

```json
{
  "company": "Microsoft",
  "overallOutlook": "Positive",
  "confidenceScore": 87,
  "summary": "Strong financial performance supported by healthy cash flow and sustained cloud growth.",
  "keyRisks": [
    "Valuation",
    "Regulatory scrutiny"
  ]
}
```

---

# Retrieve Saved Reports

## Endpoint

```http
GET /reports
```

### Description

Returns previously generated investment research reports.

---

# Retrieve Report

## Endpoint

```http
GET /reports/{reportId}
```

### Description

Returns a specific investment research report.

---

# Export Report

## Endpoint

```http
GET /reports/{reportId}/export
```

### Supported Formats

- PDF
- HTML

---

# Response Codes

| Status Code | Description |
|-------------|-------------|
| 200 | Success |
| 201 | Report Created |
| 400 | Invalid Request |
| 401 | Unauthorized |
| 404 | Resource Not Found |
| 429 | Rate Limit Exceeded |
| 500 | Internal Server Error |

---

# Authentication

Future versions of the platform may support:

- OAuth 2.0
- JWT Authentication
- API Keys
- Enterprise Single Sign-On (SSO)

---

# External Integrations

The platform may integrate with:

- Yahoo Finance
- Alpha Vantage
- NewsAPI
- SEC EDGAR (or stock exchange filings)
- OpenAI API

---

# API Design Principles

The APIs are designed to:

- Follow RESTful conventions
- Return consistent JSON responses
- Support modular AI workflows
- Be scalable and versionable
- Enable secure integrations with external services
