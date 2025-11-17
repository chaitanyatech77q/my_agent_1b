# my_agent_1b
Day 1b - Agent Architectures
✅ README.md — Multi-Agent Systems & Workflow Patterns (Google ADK)
🚀 Multi-Agent Systems & Workflow Patterns Using Google ADK

This repository contains the complete implementation for Day 1B (Multi-Agent Systems) of the Kaggle 5-Day Agents Course, demonstrating how to use Google’s Agent Development Kit (ADK) to build:

Specialized agents

Coordinator agents

Sequential pipelines

Parallel workflows

Iterative refinement loops

This notebook scales beyond a single agent and teaches you how to orchestrate complex, multi-step AI systems.

📌 What This Project Covers
✅ Gemini API Key Setup
✅ ADK Imports & Retry Configuration
✅ Research + Summarization Multi-Agent Workflow
✅ Sequential Blog Generation Pipeline
✅ Parallel Multi-Domain Research System
✅ Loop Agent for Iterative Story Refinement
✅ State Passing Between Agents (via output_key)
✅ Using AgentTool & FunctionTool

Each section showcases a real, production-style multi-agent architecture.

🧠 Core Concepts Demonstrated
1. LLM-Orchestrated Agents

A coordinator agent (LLM-driven) calls sub-agents as tools.

2. Sequential Workflow (Pipeline)

Runs in a fixed order:

Outline → Write → Edit

3. Parallel Workflow (Concurrent Research)

Runs independent agents at the same time:

Tech + Health + Finance → Aggregator

4. Loop Workflow (Refinement Cycle)

Executes repeated review → rewrite → review until "APPROVED".

🛠️ How to Run This Code (Important)

Place these instructions as code comments at the top of your notebook or Python file.
Here's the exact version optimized for your repo:

# ============================================================
# HOW TO RUN THIS NOTEBOOK (IMPORTANT)
# ============================================================
# 1. Open this notebook in Kaggle.
# 2. Go to "Add-ons" → "Secrets".
# 3. Create a new secret:
#       Name: GOOGLE_API_KEY
#       Value: <your Gemini API Key from Google AI Studio>
# 4. Enable the checkbox to attach the secret to this notebook.
# 5. Run each cell ONE BY ONE (do NOT click "Run All").
#    Running all cells at once may cause 429 (rate limit) errors.
# 6. Every section in this notebook is independent.
#    You can run:
#       - Section 1 (Research System)
#       - Section 2 (Blog Pipeline)
#       - Section 3 (Parallel Research System)
#       - Section 4 (Story Refinement Loop)
#    individually without interference.
# ============================================================

📦 Code Structure

Your notebook includes 4 complete multi-agent systems:

/
├── Section 1 — Research + Summarization Multi-Agent System
├── Section 2 — Sequential Blog Writing Pipeline
├── Section 3 — Parallel Multi-Topic Research System
└── Section 4 — Loop-Based Story Refinement Workflow


Each system runs independently using InMemoryRunner.

🧩 Key ADK Features Used
🔹 Agent

Defines a task-specific LLM agent.

🔹 AgentTool

Wraps an agent so another agent can call it like a tool.

🔹 FunctionTool

Lets an agent call a Python function (used for loop exit).

🔹 SequentialAgent

Ensures a fixed step-by-step workflow.

🔹 ParallelAgent

Runs multiple agents at the same time.

🔹 LoopAgent

Runs critic and refiner repeatedly until approved.

🧪 Example: How Workflows Execute
Research + Summarization
User → Coordinator → ResearchAgent → SummarizerAgent → Final Answer

Blog Writing Pipeline
OutlineAgent → WriterAgent → EditorAgent → Final Blog

Parallel Research
TechResearcher  
HealthResearcher  
FinanceResearcher  
   └── run together → AggregatorAgent → Summary Report

Story Refinement Loop
InitialWriter → [Critic → Refiner] x N → Final Story

▶️ Running a Workflow

Example:

runner = InMemoryRunner(agent=root_agent)
response = await runner.run_debug("Write a blog about multi-agent systems")


run_debug() shows the full trace of each agent’s memory, state, and steps.

📚 Documentation

Google ADK → https://github.com/google/adk

Kaggle 5-Day Agents Course

Gemini Models → Google AI Studio

📝 License

This repository is for learning & educational purposes as part of the Kaggle AI Agents program.
You may modify and use the code in your own projects.

🎉 You're Ready For Day 2!

This notebook completes Day 1B.
Next up: Custom Functions, MCP Tools, Long Running Ops & Advanced Orchestration.
