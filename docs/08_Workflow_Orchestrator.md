# Workflow Orchestrator

## Purpose

The Workflow Orchestrator is the central coordinator of AI Investment Research Copilot. It manages the execution of AI agents, controls the workflow, aggregates results, and generates a unified investment research report.

The orchestrator ensures that each agent performs a specific responsibility while maintaining a structured, scalable, and explainable workflow.

---

# Architecture Overview

```text
                    User Request
                         │
                         ▼
              Workflow Orchestrator
                         │
      ┌──────────────────┼──────────────────┐
      ▼                  ▼                  ▼
Market Data      Financial Analysis   News & Sentiment
      │                  │                  │
      └──────────────┬───┴──────────────────┘
                     ▼
          Technical Analysis
                     │
                     ▼
        Document Retrieval (RAG)
                     │
                     ▼
      Investment Research Agent
                     │
                     ▼
        Report Generation Agent
                     │
                     ▼
              Human Review
```

---

# Responsibilities

The Workflow Orchestrator is responsible for:

- Receiving user requests
- Managing workflow execution
- Coordinating AI agents
- Collecting intermediate results
- Handling errors and retries
- Passing consolidated information to the Investment Research Agent
- Returning the final research report

---

# Workflow Execution

## Step 1: Receive Request

Input:

- Company name
- Stock ticker (optional)

Example:

```
Analyze Microsoft Corporation
```

---

## Step 2: Parallel Data Collection

The orchestrator invokes these agents in parallel:

- Market Data Agent
- Financial Analysis Agent
- News & Sentiment Agent
- Document Retrieval Agent (RAG)

Running these tasks simultaneously reduces overall response time.

---

## Step 3: Technical Analysis

Once historical market data is available, the Technical Analysis Agent calculates indicators such as RSI, MACD, and Moving Averages.

---

## Step 4: Aggregate Results

The orchestrator combines outputs from all agents into a unified research context.

Example:

- Market data
- Financial metrics
- Technical indicators
- News summary
- Retrieved document excerpts

---

## Step 5: Investment Research

The Investment Research Agent generates:

- Financial assessment
- Technical interpretation
- Risk analysis
- Investment outlook
- Confidence score

---

## Step 6: Report Generation

The Report Generation Agent formats the analysis into a structured investment research report.

---

## Step 7: Human Review

The completed report is presented to the user for review before any investment decision.

The platform supports decision-making but does not execute trades or provide personalized financial advice.

---

# Error Handling

The Workflow Orchestrator handles common failures, including:

- Market data API unavailable
- Financial document unavailable
- News retrieval failure
- LLM timeout
- Retrieval failures

If one data source is unavailable, the platform continues where possible and clearly indicates missing information in the final report.

---

# Execution Strategy

| Activity | Execution Mode |
|----------|----------------|
| Market Data Retrieval | Parallel |
| Financial Analysis | Parallel |
| News Retrieval | Parallel |
| Document Retrieval (RAG) | Parallel |
| Technical Analysis | Sequential (after market data retrieval) |
| Investment Research | Sequential |
| Report Generation | Sequential |

---

# Benefits of Workflow Orchestration

- Modular AI architecture
- Faster execution through parallel processing
- Easier maintenance
- Scalable design
- Improved fault tolerance
- Consistent report generation
- Explainable AI workflow

---

# Design Principles

The orchestrator follows these principles:

- Single point of coordination
- Independent agent execution
- Structured data exchange
- Human-in-the-loop decision support
- Explainable AI outputs
- Graceful handling of partial failures

---

# Future Enhancements

Future versions of the Workflow Orchestrator may include:

- Dynamic workflow selection
- Agent prioritization based on user intent
- Multi-company comparative analysis
- Asynchronous long-running research jobs
- Event-driven processing
- Agent performance monitoring
- Workflow analytics dashboard
