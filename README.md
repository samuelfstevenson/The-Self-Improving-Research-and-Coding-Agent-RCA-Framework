# The-Self-Improving-Research-and-Coding-Agent-RCA-Framework
multi-agent system designed for autonomous code generation, research, quality assurance (CI/CD), and continuous self-improvement. It leverages GraphRAG for contextual knowledge retrieval and the Agent2Agent (A2A) protocol for structured communication.
1.3. Dual Concurrent Workflows
The Supervisor manages two parallel workflows, ensuring that user work and internal framework
improvement do not block each other:
1. Workflow A (User Project): Triggered by a user request. The Coding Agent initiates an
A2A request to the Research Agent for project context, saving results to the isolated
user_project_dir/.
2. Workflow B (Framework Improvement): Automatically triggered by framework code
updates. The Verification Agent runs the full CI/CD pipeline, and only on PASS are
version numbers incremented (logged to improvement.log) and changes implemented into
the core framework.
2. Installation and Setup
The framework supports cross-platform installation on Windows, Mac, and Linux via three
primary methods.
2.1. Prerequisites
1. Python: Python 3.10+ is required.
2. Git: Required for cloning external codebases.
3. Neo4j: A running Neo4j instance (version 5.11+ is recommended) is necessary to host
the GraphRAG knowledge base.
○ Installation: Use Neo4j Desktop (Windows/Mac) or the Linux Executable
(Linux/Docker) for local setup.
4. Ollama (Optional): Required only if using local LLMs (Ollama, LM Studio) via the
ProviderAgent.
○ Installation (Linux/Mac): curl -fsSL https://ollama.com/install.sh | sh
