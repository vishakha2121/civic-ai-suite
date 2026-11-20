<div align="center">

# 🏛️ Civic AI Suite
### AI-Powered Autonomous Digital Government Platform

[![React](https://img.shields.io/badge/React_18-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![Python](https://img.shields.io/badge/Python_3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org/)
[![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org/)
[![Google Gemini](https://img.shields.io/badge/Google_Gemini-8E75B2?style=for-the-badge&logo=google&logoColor=white)](https://deepmind.google/technologies/gemini/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

*A multi-agent AI platform simulating an autonomous digital government, where AI agents manage citizen services end-to-end.*

</div>

---

## 📌 Table of Contents
1. [Overview](#-overview)
2. [The Six Autonomous Agents](#-the-six-autonomous-agents)
3. [Core Features](#-core-features)
4. [Tech Stack](#-tech-stack)
5. [System Architecture](#-system-architecture)
6. [Database Schema](#-database-schema)
7. [API Endpoints Overview](#-api-endpoints-overview)
8. [Project Structure](#-project-structure)
9. [Getting Started (Local Setup)](#-getting-started-local-setup)
10. [Screenshots](#-screenshots)
11. [Future Scope](#-future-scope)
12. [Author](#-author)

---

## 🎯 Overview

**Civic AI Suite** is a full-stack, multi-agent AI application that reimagines how citizens interact with government services. 

Instead of navigating complex, fragmented portals, citizens talk to specialized AI agents that understand their needs, guide them through multi-step workflows, and track requests from start to finish. The system acts as an **autonomous digital government** where AI handles end-to-end service delivery.

This project is designed as a **practice-level, CPU-friendly** system (no GPU required) and demonstrates **Multi-Agent Orchestration**, **Workflow Automation**, and **Large-Scale AI Processing** using the Google Gemini API.

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

**How it works:** When a user asks a question (e.g., *"How do I renew my driving license?"*), the **Agent Router** analyzes the intent and dispatches it to the **Transportation Agent**, which uses Gemini to provide a contextual response and initiates a renewal workflow.

---

## ⚙️ Core Features

- **🤖 Multi-Agent Architecture** — 6 specialized AI agents with an intelligent router.
- **💬 AI Chat Interface** — Real-time conversations powered by Google Gemini (`gemini-1.5-flash`), complete with typing indicators and chat history.
- **🔄 Workflow Engine** — State-machine-driven multi-step approval flows *(Apply → Verify → Review → Approve → Notify)*.
- **📊 Governance Dashboard** — Admin panel to monitor agents, track all requests, view audit logs, and manage users.
- **🔐 Role-Based Access Control (RBAC)** — Separate citizen and admin experiences with JWT authentication.
- **📋 Request Lifecycle Tracking** — Every request goes through tracked states with visual steppers and timelines.
- **📜 Audit Logging** — Every agent action, request change, and user operation is recorded for governance transparency.
- **🔔 Notifications** — In-app alerts when request status changes.

---

## 🏗️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | React 18, Vite, Tailwind CSS, React Router, Axios |
| **Backend** | Python 3.10+, FastAPI, SQLAlchemy (ORM), Uvicorn |
| **Database** | SQLite (File-based, zero-configuration, CPU-friendly) |
| **AI Engine** | Google Gemini API (`gemini-1.5-flash` model) |
| **Security** | JWT (JSON Web Tokens), Bcrypt (Password Hashing) |
| **Architecture** | Multi-Agent System, State Machine Workflows, REST API |

---

## 🔄 System Architecture

Here is how a request flows through the system:

```text
[ User / Citizen ]
       │
       ▼
[ React Frontend ] ──(REST API)──► [ FastAPI Backend ]
                                         │
                       ┌─────────────────┴─────────────────┐
                       ▼                                   ▼
             [ Agent Router ]                     [ Auth & Security ]
                       │                                   │
         ┌─────────────┼─────────────┐                     ▼
         ▼             ▼             ▼               [ JWT / Bcrypt ]
   [ Taxation ]  [ Healthcare ]  [ Transport ]               │
     Agent          Agent          Agent                    │
         │             │             │                      │
         └─────────────┼─────────────┘                      ▼
                       ▼                             [ SQLite Database ]
                [ Gemini API ]                       - Users
                (LLM Engine)                         - Requests
                       │                             - Workflows
                       ▼                             - Audit Logs
              [ Workflow Engine ]
             (State Transitions)
                       │
                       ▼
              [ Audit & Logs ]