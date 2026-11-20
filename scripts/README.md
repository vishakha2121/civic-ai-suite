<div align="center">

# 🏛️ Civic AI Suite
### AI-Powered Autonomous Digital Government Platform

[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org/)
[![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org/)
[![Google Gemini](https://img.shields.io/badge/Google%20Gemini-8E75B2?style=for-the-badge&logo=google&logoColor=white)](https://deepmind.google/technologies/gemini/)

*A multi-agent AI platform simulating an autonomous digital government, where AI agents manage citizen services end-to-end.*

</div>

---

## 🎯 Overview

**Civic AI Suite** reimagines how citizens interact with government services. Instead of navigating complex portals, citizens talk to specialized AI agents that understand their needs, guide them through workflows, and track requests from start to finish.

This project demonstrates **Multi-Agent Orchestration**, **Workflow Automation**, and **Large-Scale AI Processing** using Google Gemini, built as a CPU-friendly, practice-level system.

---

## 🧩 The Six Autonomous Agents

| Agent | Responsibilities |
|-------|-----------------|
| 🏦 **Taxation Agent** | Tax calculation, filing assistance, query resolution, refund status |
| 📜 **Licensing Agent** | License application, renewal, document verification, status tracking |
| 🏥 **Healthcare Agent** | Hospital/scheme discovery, appointment workflows, health records |
| 🏛️ **Public Services Agent** | Birth/death certificates, ration cards, utility connections |
| 🚗 **Transportation Agent** | Driving license, vehicle registration, challan queries |
| 📢 **Citizen Request Agent** | Complaints, grievances, feedback, general queries |

---

## ⚙️ Core Features

- **🤖 Multi-Agent Architecture** — 6 specialized AI agents with an intelligent router that dispatches queries to the correct department.
- **💬 AI Chat Interface** — Real-time conversations powered by Google Gemini (`gemini-1.5-flash`), complete with typing indicators and message history.
- **🔄 Workflow Engine** — State-machine-driven multi-step approval flows *(Apply → Verify → Review → Approve → Notify)*.
- **📊 Governance Dashboard** — Admin panel to monitor agents, track all requests, view audit logs, and manage users.
- **🔐 Role-Based Access** — Separate citizen and admin experiences with JWT authentication.
- **📜 Audit Logging** — Every agent action, request change, and user operation is recorded for transparency.
- **🔔 Notifications** — In-app alerts when request status changes.

---

## 🏗️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | React 18, Vite, Tailwind CSS, React Router, Axios |
| **Backend** | Python 3.10+, FastAPI, SQLAlchemy, Uvicorn |
| **Database** | SQLite (File-based, CPU-friendly) |
| **AI Engine** | Google Gemini API (`gemini-1.5-flash`) |
| **Security** | JWT (JSON Web Tokens), Bcrypt |
| **Architecture** | Multi-Agent System, State Machine Workflows, REST API |

---

## 📂 Project Structure

```text
civic-ai-suite/
│
├── frontend/              # React + Vite + Tailwind UI
│   ├── src/
│   │   ├── components/    # Reusable UI components
│   │   ├── pages/         # Full page views
│   │   ├── services/      # API call logic
│   │   ├── context/       # Global state (Auth, Theme)
│   │   └── hooks/         # Custom React hooks
│   └── package.json
│
├── backend/               # FastAPI Python Backend
│   ├── app/
│   │   ├── models/        # SQLAlchemy DB models
│   │   ├── schemas/       # Pydantic validation schemas
│   │   ├── routers/       # API endpoints
│   │   ├── services/      # Business logic
│   │   ├── agents/        # 6 AI Agents + Router
│   │   ├── ai/            # Gemini API integration
│   │   ├── workflows/     # Workflow state machine
│   │   └── core/          # Config, Security, Utils
│   ├── requirements.txt
│   └── run.py
│
├── database/              # SQLite database files
│   └── digital_gov.db
│
└── docs/                  # Documentation & Diagrams