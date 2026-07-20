# Sequence Diagram

```text
User
 |
 | Search Company
 |
 v
Streamlit UI
 |
 v
FastAPI
 |
 v
Workflow Orchestrator
 |------------------------------|
 |                              |
 |----> Market Data Agent ------|
 |----> Financial Agent --------|
 |----> Technical Agent --------|
 |----> News Agent -------------|
 |----> RAG Agent --------------|
 |                              |
 |<----- Results ---------------|
 |
 v
Investment Research Agent
 |
 v
Report Generation Agent
 |
 v
FastAPI
 |
 v
Streamlit UI
 |
 v
Investment Research Report
```
