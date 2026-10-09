# 🤖 Scientific Research Agent  
**Autonomous AI Agent with LangChain, LangGraph, LangFuse & Streamlit**

---

## 🚀 Live Demo

<a href="https://research-agent-langchain.streamlit.app/" target="_blank">▶️ Open Live App</a>

![App View](app_view.png)
---

## 📌 Project Overview

**Scientific Research Agent** is an AI-powered research assistant that autonomously answers scientific questions by selecting and calling the most appropriate external tool.

The project demonstrates a complete **LLM Agent pipeline**, covering tool selection, ReAct reasoning loop, conversation memory, observability, and interactive deployment as a web application, hardened for a public demo (safe calculator, HTML escaping, usage limits, per-session data).

It was designed as an **end-to-end portfolio project** showing LLM engineering with tool-using agents, observability and security basics for a public LLM app. Answer quality is only partly measured (tool choice, calculator, safety, sources on a small dev set); free-text factual quality is not.

---

## 🎯 Features

- 🔍 **4 research tools**: Wikipedia, ArXiv, PubMed, Calculator (AST-based, no `eval`)
- 🛡️ **Cost and safety limits** — question length, per-session and daily token budgets, recursion limit, escaped HTML
- 📚 **Sources** — links to the pages and papers the tools actually retrieved, shown under each answer
- 🧪 **Evaluation harness** — 32 hand-written cases with a dev/test split, scored on tool choice, calculator correctness, safety and source coverage (results published only after a real run)
- ✅ **Tests and CI** — pytest suite with a scripted fake model (no API key needed), ruff lint and dependency audit in GitHub Actions
- 🧠 **Autonomous tool selection** — agent decides which tool fits the question
- 💬 **Short-term memory** — the last 6 messages of the session are passed back to the model
- 🗄️ **SQLite logging** — queries saved with tokens used and tools called, visible only to the session that made them, kept 30 days
- 📊 **Tool usage statistics** — interactive bar chart in sidebar
- 📡 **LangFuse observability** (optional) — trace monitoring, latency and cost tracking when keys are configured
- ⬇️ **CSV export** — download your own session history (formula-injection safe)
- ⚙️ **GPT model selector** — switch between gpt-4o-mini and gpt-4o

---

## 🧠 Agent Architecture

- **Pattern**: ReAct (Reasoning + Acting)
- **Framework**: LangChain + LangGraph
- **LLM**: OpenAI GPT-4o-mini
- **Observability**: LangFuse (optional, when keys are configured)

### ReAct Loop
```
User Question
     ↓
LLM reasons which tool to use
     ↓
Tool is called (Wikipedia / ArXiv / PubMed / Calculator)
     ↓
LLM observes the result
     ↓
Final Answer
```

When LangFuse keys are configured, every step is traced there.

---

## 🔧 Tools

| Tool | Source | Use Case |
|---|---|---|
| Wikipedia | MediaWiki API (own client) | General scientific concepts |
| ArXiv | arXiv Atom API (own client) | Recent research papers |
| PubMed | NCBI E-utilities API | Biomedical & clinical research |
| Calculator | Custom `@tool` | Mathematical calculations |

---

## 🖥️ Web Application

- **Framework**: Streamlit
- **Key aspects**:
  - Chat bubble style UI
  - Agent reasoning steps visible per query
  - Session state management for conversation history
  - Sidebar with live statistics and export
  - Deployed on Streamlit Community Cloud

---

## 🧪 Testing & Evaluation

**Automated tests — 95 tests, run on every push (<a href="https://github.com/slastrzelec/research-agent-langchain/actions/workflows/ci.yml" target="_blank">GitHub Actions</a>) with lint and a dependency audit.** The suite needs no API key and no network, so it runs in seconds.

- **Security:** the calculator rejects code injection and resource-exhaustion input (a test proves a malicious expression never touches the file system); HTML in questions and answers is escaped; Markdown images are stripped from model output; CSV export is protected against formula injection.
- **Agent logic:** the real LangGraph agent is driven by a scripted fake model — tool calls, token counting, source collection, recursion limit, history truncation.
- **Resilience:** Wikipedia / ArXiv / PubMed clients are tested against timeouts, HTTP errors, malformed JSON/XML and XML-bomb input; they never crash the agent.
- **Cost control & privacy:** per-session and daily budgets, per-session data isolation, SQL-injection strings stay inert, schema migration and 30-day retention.
- **UI:** Streamlit `AppTest` checks rendering, limits and that one visitor never sees another's history.

**Evaluation harness** (<a href="https://github.com/slastrzelec/research-agent-langchain/tree/main/evaluation" target="_blank">code, cases and raw results</a>): 32 hand-written questions split into `dev` (for tuning) and `test` (run once per configuration, enforced by the runner), scored on tool choice, calculator correctness, safety behaviour and source coverage, with 95 % confidence intervals. A test also checks that no evaluation question leaks into the prompt or code. Results are published only after a real run.

**Dev-set results (16 cases, gpt-4o-mini, one real run):** tool choice 14/14 (95 % CI 0.79–1.00), calculator 3/3, safety 2/2, sources 10/10; about 1,000 tokens and 5.5 s per question. The `test` split has not been run yet, and with 16 cases the intervals are wide — treat these as a smoke check, not a benchmark.

**Not covered (stated honestly):** real calls to OpenAI and the search APIs are verified by hand on the live demo, and the factual quality of free-text answers is not measured automatically.

---

## 🧰 Tech Stack

- **Python 3.11**
- **LangChain + LangGraph** – agent framework
- **OpenAI API** – GPT-4o-mini
- **LangFuse** – LLM observability
- **Streamlit** – web deployment
- **SQLite** – conversation logging
- **Plotly / Pandas** – data visualization
- **Git & GitHub**

---

## 🚀 Use Cases

- Scientific literature research automation
- AI agent development reference
- LLM observability and monitoring demo
- LangChain / LangGraph portfolio showcase
- Technical interviews for AI Engineer roles

---

## 📂 Repository

🔗 <a href="https://github.com/slastrzelec/research-agent-langchain" target="_blank">GitHub Repository</a>  
📐 <a href="https://github.com/slastrzelec/research-agent-langchain/blob/main/SPEC.md" target="_blank">Spec and threat model (SPEC.md)</a>  
🧪 <a href="https://github.com/slastrzelec/research-agent-langchain/tree/main/tests" target="_blank">Tests</a> · <a href="https://github.com/slastrzelec/research-agent-langchain/tree/main/evaluation" target="_blank">Evaluation</a> · <a href="https://github.com/slastrzelec/research-agent-langchain/actions" target="_blank">CI runs</a>  
📖 <a href="https://github.com/slastrzelec/research-agent-langchain#testing" target="_blank">README: Testing</a> · <a href="https://github.com/slastrzelec/research-agent-langchain#evaluation" target="_blank">README: Evaluation</a>

### Related projects

- [Carbon Nanotubes RAG System](../carbon-nanotubes-rag/index.md) — retrieval-augmented generation with evaluation (RAGAs)
- [CV-Job Matching System](../cv-job-matcher/index.md) — OpenAI embeddings and semantic ranking, with a Streamlit app

---

## 👨‍💻 Author

**Sławomir Strzelec**  
Data Scientist | Machine Learning Practitioner  

- 📍 Kraków, Poland  
- 💼 <a href="https://www.linkedin.com/in/sławomir-strzelec" target="_blank">LinkedIn</a>  
- 💻 <a href="https://github.com/slastrzelec/research-agent-langchain" target="_blank">GitHub</a>  

---

## 📌 Project Status

✅ Completed & Deployed  

🔧 Potential extensions:

- Persistent database (PostgreSQL / Supabase)
- LangFuse evaluations and scoring
- Multi-agent pipeline (LangGraph multi-node)
- Docker deployment
- User authentication