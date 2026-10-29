# Sławomir Strzelec — AI/ML Engineer

<p>
I build and deploy AI applications: from retrieval and evaluation to APIs, containers and cloud delivery. My work includes a public RAG API with measured quality, an MCP server with an evaluated agent client, a tested Python package and a startup application migrated to Google Cloud.
</p>

<p>
My background is in chemistry and nanotechnology, which is why I care about measurable results and honest evaluation, not just demos.
</p>

<p>
<strong>Looking for:</strong> AI/ML Engineer roles · Kraków, Poland
</p>

[Selected projects](#selected-projects){ .md-button .md-button--primary } [About me](o-mnie.md){ .md-button } [Contact](mailto:sla.strzelec@gmail.com){ .md-button }

## Selected projects

<div class="card" markdown>

### [Carbon Nanotubes RAG System](carbon-nanotubes-rag/index.md)

* **Problem:** answering questions about 24 research papers with traceable sources.
* **My contribution:** designed and built it end to end: hybrid FAISS + BM25 retrieval, FastAPI service, Docker, CI and deployment.
* **Result:** 31 automated tests, RAGAs faithfulness ≈ 0.80–0.82 (14-question domain set), cost limits and structured logging.
* **Evidence:** [project page](carbon-nanotubes-rag/index.md) · [live demo](https://carbon-nanotubes-raman-rag.streamlit.app/) · [repository](https://github.com/slastrzelec/carbon-nanotubes-rag)

</div>

<div class="card" markdown>

### [Carbon Nanotubes RAG over MCP](carbon-nanotubes-rag-mcp/index.md)

* **Problem:** letting an AI agent use the RAG system safely, with a protocol other clients can reuse.
* **My contribution:** an MCP server with three read-only tools, protection against prompt injection and cost abuse, and a LangGraph agent client.
* **Result:** 162 tests; agent behaviour measured on a frozen held-out set: 23 of 25 questions passed (95% interval 0.75–0.98), with both failures described.
* **Evidence:** [project page](carbon-nanotubes-rag-mcp/index.md) · [repository](https://github.com/slastrzelec/carbon-nanotubes-rag-mcp)

</div>

<div class="card" markdown>

### [GadAround on Google Cloud](gadaround-gcp-deployment/index.md)

* **Problem:** an early-stage startup app ran as a Flask monolith on SQLite and needed a reliable place to run.
* **My contribution:** cloud migration and delivery pipeline in a two-person team: Cloud Run, Cloud SQL (PostgreSQL), Secret Manager, GitHub Actions with keyless authentication, custom domain through Cloudflare.
* **Result:** the app runs on its own domain; every merge to `main` builds and deploys automatically.
* **Evidence:** [live site](https://www.gadaround.pl/) · [project page](gadaround-gcp-deployment/index.md) · repository private

</div>

<div class="card" markdown>

### [ML Data Guard](ml-data-guard/index.md)

* **Problem:** data checks for ML pipelines are rarely measured for how often they miss a fault or raise a false alarm.
* **My contribution:** a benchmark of data-validation methods on twelve injected fault types, packaged as a library, a command-line tool and a GitHub Action.
* **Result:** published on PyPI, 780 tests, interactive results explorer.
* **Evidence:** [project page](ml-data-guard/index.md) · [PyPI](https://pypi.org/project/ml-data-guard/) · [repository](https://github.com/slastrzelec/ml-data-guard)

</div>

## More projects

**AI and ML**

* [🔍 SEM Nanostructure Classifier (PyTorch · ConvNeXt · Leakage-free evaluation)](sem-nanostructure-classifier/index.md)
* [🏺 Cuneiform Sign Classifier (PyTorch · Grad-CAM · HF Hub)](20_cuneiform-sign-classifier/index.md)
* [🤖 Scientific Research Agent (LangChain · LangGraph · LangFuse)](research-agent-langchain/index.md)
* [🎯 CV-Job Matching System (OpenAI embeddings · Streamlit)](cv-job-matcher/index.md)
* [⚡ KDB+/Q vs SQL Benchmark (kdb+/q · DuckDB · AWS · Prophet)](energy-forecasting-sql-vs-kdb/index.md)

**Computer vision**

* [🔬 Erythrocyte Analysis (OpenCV · Streamlit)](erythrocyte-shape-analyzer/index.md)
* [🚶 People Counter (YOLOX-nano · ONNX Runtime · ByteTrack)](people-counter-yolox/index.md)
* [😊 Emotion Recognition (PyTorch · ResNet18 · OpenCV · Streamlit)](emotion-recognition-cv/index.md)

**Cheminformatics and scientific ML**

* [🧪 Buchwald-Hartwig C-N Coupling Optimizer (RDKit · XGBoost)](buchwald-hartwig-optimizer/index.md)
* [💊 Drug Solubility Predictor (RDKit · scikit-learn)](drug-solubility-prediction/index.md)
* [🧬 logP Predictor (PyTorch)](molecular-lipophilicity-ai/index.md)

**Other**

* [🌈 Raman Spectroscopy Analyzer (SciPy · Plotly)](raman-spectroscopy-analyzer/index.md)
* [⛓️ Carbon Nanotube Visualizer (Plotly · ASE · Streamlit)](carbon-nanotube-visualizer/index.md)

## About & Contact

* [About Me](o-mnie.md) – background, skills and experience
* 📧 [sla.strzelec@gmail.com](mailto:sla.strzelec@gmail.com) · 💼 [LinkedIn](https://www.linkedin.com/in/s%C5%82awomir-strzelec/) · 🐙 [GitHub](https://github.com/slastrzelec)
