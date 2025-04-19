# Oracle Agentic AI DBA Assistant

## 🧠 Project Overview
This project aims to build an **agentic AI system** that automates decision-making in Oracle database monitoring. Specifically, the agent will analyze tablespace usage and decide whether to:
- Ignore the issue
- Autoextend the tablespace
- Alert the DBA

The project utilizes **n8n workflows**, **CrewAI agents**, **Python scripting**, and **Oracle Database (XE)** to create an intelligent, modular system designed for production-like environments.

---

## 🚀 Tech Stack

### Core Technologies
- **Oracle Database XE** (or target production Oracle DB)
- **n8n** (self-hosted in Docker)
- **Python** (with `cx_Oracle` and AI agent logic)
- **CrewAI** (agent orchestration)
- **Docker Compose** (for environment setup)

### Optional Add-ons
- **Streamlit** (optional UI/dashboard)
- **Grafana + Loki** (for observability/logs)
- **Slack/Telegram** (alerting options)

---

## 📈 Project Goals

### Short-Term Goals (Mini Project: ~100 hrs)
- [ ] Connect to Oracle DB from Python
- [ ] Retrieve tablespace usage data
- [ ] Build initial n8n workflow
- [ ] Implement a basic agent to respond with action
- [ ] Route action in n8n: log, extend, or alert

### Main Project Goals (~300+ hrs)
- [ ] Develop smart AI prompt chaining and state memory
- [ ] Integrate historical monitoring data
- [ ] Build autoextend script safely
- [ ] Add Streamlit dashboard
- [ ] Document all modules and workflows
- [ ] Deploy in containerized environment (Docker Compose)

---

## 🔁 System Workflow (High-Level)

```text
┌──────────────────┐
│ Cron (n8n)       │
└────────┬─────────┘
         ↓
┌─────────────────────────┐
│ Python Oracle Query     │
│ (tablespace % usage)    │
└────────┬────────────────┘
         ↓
┌──────────────────────────────┐
│ CrewAI Agent Decision Layer │
└────────┬─────────────────────┘
         ↓
┌──────────────────────────────┐
│ Decision: IGNORE / ALERT /   │
│ AUTOEXTEND                   │
└────────┬─────────────────────┘
         ↓
┌──────────────────────────────┐
│ Conditional Logic in n8n     │
└──────────────────────────────┘
