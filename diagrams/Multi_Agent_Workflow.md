# Multi-Agent Workflow

```text
User Request
      |
      v
Workflow Orchestrator
      |
      +------------------------------+
      |                              |
      | Parallel Execution           |
      |                              |
      +------------------------------+
      |              |               |
      v              v               v
Market Data   Financial Analysis   Technical Analysis
Agent          Agent               Agent
      |              |               |
      +--------------+---------------+
                     |
                     v
          News & Sentiment Agent
                     |
                     v
        Document Retrieval Agent (RAG)
                     |
                     v
          Investment Research Agent
                     |
                     v
          Report Generation Agent
                     |
                     v
          Final Investment Report
```
