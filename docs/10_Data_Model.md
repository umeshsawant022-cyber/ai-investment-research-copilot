# Data Model

## Purpose

This document defines the core business entities, their attributes, and relationships within AI Investment Research Copilot. The data model provides a conceptual view of how information flows through the platform and supports AI-driven investment research.

---

# Entity Relationship Overview

```text
User
 │
 ├── Research Report
 │        │
 │        ├── Company
 │        ├── Market Data
 │        ├── Financial Statement
 │        ├── Technical Analysis
 │        ├── News Summary
 │        └── Risk Assessment
 │
 └── Saved Reports
```

---

# Entity: User

## Description

Represents a registered user of the platform.

### Attributes

| Attribute | Description |
|-----------|-------------|
| User ID | Unique identifier |
| Name | User's full name |
| Email | Login email |
| Role | Investor, Analyst, Advisor |
| Created Date | Account creation date |

---

# Entity: Company

## Description

Represents a publicly listed company.

### Attributes

| Attribute | Description |
|-----------|-------------|
| Company ID | Unique identifier |
| Company Name | Registered company name |
| Stock Symbol | Trading symbol |
| Exchange | Stock exchange |
| Sector | Industry sector |
| Industry | Business category |
| Market Capitalization | Company market value |

---

# Entity: Market Data

## Description

Stores market information retrieved from external providers.

### Attributes

| Attribute | Description |
|-----------|-------------|
| Stock Price | Current market price |
| Open Price | Opening price |
| Close Price | Closing price |
| High | Daily high |
| Low | Daily low |
| Volume | Trading volume |
| Date | Market date |

---

# Entity: Financial Statement

## Description

Represents company financial information.

### Attributes

| Attribute | Description |
|-----------|-------------|
| Revenue | Total revenue |
| Net Income | Profit after tax |
| EPS | Earnings per Share |
| Debt | Total debt |
| Cash Flow | Operating cash flow |
| Total Assets | Company assets |
| Total Liabilities | Company liabilities |
| Reporting Period | Quarterly or Annual |

---

# Entity: Technical Analysis

## Description

Stores calculated technical indicators.

### Attributes

| Attribute | Description |
|-----------|-------------|
| RSI | Relative Strength Index |
| MACD | Moving Average Convergence Divergence |
| Moving Average | Average price |
| Bollinger Bands | Volatility indicator |
| Support Level | Price support |
| Resistance Level | Price resistance |
| Trend | Bullish / Bearish / Neutral |

---

# Entity: News Summary

## Description

Represents summarized company and market news.

### Attributes

| Attribute | Description |
|-----------|-------------|
| News ID | Unique identifier |
| Source | News provider |
| Published Date | Publication date |
| Headline | News title |
| Summary | AI-generated summary |
| Sentiment | Positive / Neutral / Negative |

---

# Entity: Risk Assessment

## Description

Represents AI-generated investment risks.

### Attributes

| Attribute | Description |
|-----------|-------------|
| Financial Risk | Low / Medium / High |
| Market Risk | Low / Medium / High |
| Industry Risk | Low / Medium / High |
| Regulatory Risk | Low / Medium / High |
| Overall Risk Score | Numerical score |

---

# Entity: Investment Research Report

## Description

Represents the final AI-generated research output.

### Attributes

| Attribute | Description |
|-----------|-------------|
| Report ID | Unique identifier |
| Company | Company analyzed |
| Executive Summary | High-level overview |
| Financial Analysis | Financial insights |
| Technical Analysis | Technical insights |
| News Summary | News highlights |
| Opportunities | Growth opportunities |
| Risks | Investment risks |
| Confidence Score | AI confidence level |
| Generated Date | Report creation date |

---

# Relationships

| Entity | Relationship |
|---------|--------------|
| User → Research Report | One-to-Many |
| Company → Market Data | One-to-Many |
| Company → Financial Statement | One-to-Many |
| Company → Technical Analysis | One-to-Many |
| Company → News Summary | One-to-Many |
| Company → Research Report | One-to-Many |
| Research Report → Risk Assessment | One-to-One |

---

# Design Principles

The data model is designed to:

- Support modular AI workflows
- Separate structured and AI-generated data
- Enable future scalability
- Maintain traceability between data sources and AI outputs
- Support explainable investment research

---

# Future Enhancements

Future versions of the data model may include:

- Portfolio entity
- Watchlist entity
- Alert entity
- User preferences
- Report version history
- Collaboration and comments
- Audit logs
