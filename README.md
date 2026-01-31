# Nirvikalpa-Agent
— Private autonomous AI agent platform for software generation, evaluation, and MLOps experimentation.
🚀 Nirvikalpa Agent

Nirvikalpa Agent is a self-hosted, Docker-native autonomous AI platform for software generation, evaluation loops, and MLOps experimentation.

🔥 Key Features

🧠 Multi-agent decomposition & repair loops

🐳 Docker-native deployment

🔐 Sandboxed code execution

📊 Observability-first design

📚 RAG pipelines for repo-scale reasoning

🧪 Prompt regression testing

📦 Model benchmarking & versioning

⚙️ CPU-friendly laptop configs (Scalable to Cloud GPUs/CPU)

🔁 Hybrid local/cloud backends


================================================================================

flowchart TB

    %% ======================
    %% External Clients
    %% ======================
    User[User / CLI / UI]
    CI[CI Pipeline / Eval Jobs]

    %% ======================
    %% API Layer
    %% ======================
    API[Flask Agent API<br/>Control Plane]

    %% ======================
    %% Agent System
    %% ======================
    Planner[Planner Agent]
    Coder[Coder Agent]
    Tester[Tester Agent]
    Fixer[Fixer Agent]

    %% ======================
    %% Model Runtime
    %% ======================
    Ollama[Ollama Runtime<br/>Local LLMs]

    %% ======================
    %% Tool Execution
    %% ======================
    Sandbox[Sandbox Runner<br/>Docker-Isolated]

    %% ======================
    %% Data / Memory
    %% ======================
    Qdrant[Qdrant Vector DB<br/>RAG Memory]
    Workspace[(Shared Workspace Volume)]

    %% ======================
    %% Observability
    %% ======================
    Prometheus[Prometheus Metrics]
    Grafana[Grafana Dashboards]

    %% ======================
    %% Flows
    %% ======================

    User --> API
    CI --> API

    API --> Planner
    Planner --> Coder
    Coder --> Tester
    Tester --> Fixer
    Fixer --> Coder

    Planner --> Ollama
    Coder --> Ollama
    Fixer --> Ollama

    Tester --> Sandbox
    Sandbox --> Workspace

    API -



