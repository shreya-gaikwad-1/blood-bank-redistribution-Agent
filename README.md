# blood-bank-redistribution-Agent

# 🩸 HemoSync AI – Autonomous Blood Donation Coordination Agent

> An AI-powered multi-agent system that autonomously coordinates emergency blood requests between hospitals using planning, email automation, and intelligent decision-making, Build using n8n.


# 🌍 Sustainable Development Goal (SDG)

**SDG 3 – Good Health and Well-being**

HemoSync AI reduces delays in emergency blood allocation by autonomously coordinating communication between hospitals, minimizing manual intervention and improving response time.

---

# 🚨 Problem Statement

During emergencies, hospitals often rely on phone calls and manual coordination to locate compatible blood units from nearby hospitals.

This process is:
- Slow
- Manual
- Difficult to track
- Prone to duplicate requests
- Inefficient during emergencies

Every minute lost can cost lives.

---

# 💡 Solution

HemoSync AI is an autonomous multi-agent system that:

- Detects new blood requests
- Finds compatible blood bags
- Prioritizes nearby hospitals
- Sends emails automatically
- Waits for responses
- Replans if hospitals don't respond
- Stops contacting hospitals once blood is secured
- Updates inventory and maintains communication logs

---

# 🤖 AI Agents

## 1. Planner Agent

Responsible for:

- Finding compatible blood bags
- Ranking hospitals based on:
  - Distance
  - Available blood bags
  - Number of hospitals required
- Generating an execution plan

---

## 2. Email Coordinator 

Responsible for:

- Sending blood request emails
- Waiting for responses
- Monitoring inbox
- Triggering next hospital if no reply
- Sending thank-you emails
- Sending cancellation emails once blood is arranged


# 🔄 Workflow

```
                    Blood Request
                           │
                           ▼
                Google Sheets Trigger
                           │
                           ▼
                Filter Compatible Blood
                           │
                           ▼
                   Planner AI Agent
                           │
                           ▼
             Rank Candidate Hospitals
                           │
                           ▼
                  Send Email (Gmail)
                           │
                           ▼
                 Wait 15 Minutes
                           │
                           ▼
              Check for Email Reply
                    │            │
                    │            │
                 Reply        No Reply
                    │            │
                    ▼            ▼
            Email Parser AI   Next Hospital
                    │
                    ▼
              Accepted?
             ┌──────┴───────┐
             │              │
            Yes             No
             │              │
             ▼              ▼
      Reserve Blood    Next Hospital
             │
             ▼
 Blood Received Confirmation
             │
             ▼
 Notify All Previously Contacted Hospitals
             │
             ▼
 Update Inventory & Logs
```

---

# 🛠 Tech Stack

| Component | Technology |
|------------|------------|
| Workflow Automation | n8n |
| AI Models | Open Ai gpt 5 mini |
| Database | Google Sheets |
| Email Service | Gmail |
| Programming | JavaScript |
| Version Control | Git + GitHub |

---

# 📂 Project Structure

```
HemoSync-AI-Agent/

│── project/
│     blood-bank-redistribution-Agent.json

│── datasets/
│     hospitals.csv
│     blood_inventory.csv
│     blood_requests.csv

│── prompts/
│     planner_prompt.md
│     planner_structured_output_schema_prompt.md

│── docs/
│     architecture.png
│     
│     

│── README.md
│── LICENSE
```

---

# 📊 Sample Datasets

- Hospital Information
- Blood Inventory
- Blood Requests
- Email Logs

---

# 🚀 Features

- Autonomous Planning
- Agentic Architecture
- Email Automation
- Intelligent Hospital Ranking
- Memory using Google Sheets
- Structured AI Outputs
- Inventory Management
- Duplicate Donation Prevention

---

# 🧠 Why This Is an AI Agent

Unlike a chatbot or simple LLM application, HemoSync AI:

- Has a clear goal
- Plans multiple steps
- Uses external tools
- Maintains memory
- Observes outcomes
- Learns system state
- Replans when necessary
- Continues until the request is fulfilled

It follows the agentic loop:

```
Observe
   ↓
Reason
   ↓
Plan
   ↓
Act
   ↓
Observe
   ↓
Evaluate
   ↓
Replan
```

---

# 📥 Installation

## Clone Repository

```bash
git clone https://github.com/shreya-gaikwad-1/blood-bank-redistribution-Agent.git
cd project
```

---

## Import Workflow

Open n8n

```
Import Workflow
```

Select

```
workflows/hemosync_workflow.json
```

---

## Configure Credentials

Add:

- Gmail OAuth Credentials
- Google Sheets Credentials

---

## Update Google Sheet IDs

Replace the Google Sheet IDs in the workflow with your own.

---

## Run

Start the workflow by creating a new blood request in the Google Sheet.

---

# 📈 Future Improvements

- Twilio Voice Calling
- WhatsApp Notifications
- Hospital Dashboard
- Blood Transport Optimization
- Multi-City Deployment
- Hospital ERP Integration
- Predictive Blood Demand Forecasting

---

# 📜 License

This project is licensed under the MIT License.

---

# ⭐ If you found this project interesting, please consider giving it a star!
