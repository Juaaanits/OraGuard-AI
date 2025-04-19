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
