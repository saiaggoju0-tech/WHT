# 🚚 Logistics Automation Suite

<p align="center">

**Production-scale logistics automation tools for reconciliation, monitoring, intelligent alerting, and AI-ready operational assistance.**

Built with **JavaScript**, **Tampermonkey**, **DOM automation**, **cross-system data correlation**, **Slack integrations**, and a modular architecture designed for future **LLM-powered logistics operations**.

</p>

---

# 📚 Table of Contents

- Overview
- Business Impact
- Engineering Metrics
- Projects
  - FMC–YMS Reconciler
  - Misloads Deficit Alert System
  - Yard Ops Assistant
  - FYCON Cancel Check
- Architecture
- Technology Stack
- Repository Structure
- Installation
- Usage
- Testing
- Engineering Challenges
- Screenshots & Demo
- Roadmap
- Why This Project?
- License

---

# 🚀 Overview

**Logistics Automation Suite** is a collection of browser automation tools built to simplify daily logistics operations by eliminating repetitive manual work.

The suite automates:

- Cross-system reconciliation
- Yard management analysis
- Trailer deficit detection
- Slack notifications
- Operational analytics
- Conversational data retrieval

Instead of requiring operators to manually compare multiple logistics systems, these tools gather, correlate, analyze, and present operational information automatically.

The architecture is intentionally designed to support future **AI-powered operational assistants** using modern Large Language Models.

---

# 📈 Business Impact

| Metric | Impact |
|---------|--------|
| Manual reconciliation | Reduced from ~20 minutes to near-instant |
| FYCON cancel detection | Automated cancelled VRID detection for IXD |
| Case count reduction | Early deficit alerts prevent escalations |
| Sites supported | 25+ logistics sites |
| Manual copy-paste | Eliminated |
| Slack notifications | Automated operational alerts |
| Future readiness | AI / LLM-ready architecture |

---

# 📊 Engineering Metrics

- 🚚 4 Production Automation Projects
- 🌍 Supports 25+ Logistics Sites
- ⚡ Near-Instant Reconciliation
- 🔔 Automated Slack Alerting
- 📈 Operational Analytics
- 🤖 AI-Ready Architecture
- 🧪 Property-Based Testing
- ♻️ Modular & Reusable Components

---

# 📦 Projects

---

# 1️⃣ FMC–YMS Reconciler

## Overview

A one-click reconciliation tool that automatically correlates FMC and YMS operational data.

Previously, operators manually copied information between systems one trailer at a time. This tool performs the reconciliation instantly.

---

## Features

- One-click reconciliation
- FMC data extraction
- YMS data extraction
- Trailer matching
- Arrival window analysis
- Multi-site support
- Intelligent operational summaries

---

## Data Sources

### FMC

- VRID
- Dock arrival timestamp
- Shipment information

### YMS

- Trailer ID
- PS Count
- DD Count
- Additional inventory counts
- Yard location
- Load notes

---

## Arrival Intelligence

Automatically groups trailers into:

- Last 4 Hours
- Last 12 Hours
- Last 24 Hours

Helping operations teams prioritize work proactively.

---

## Business Impact

- Reduced reconciliation from approximately **20 minutes** to near-instant.
- Eliminated repetitive copy-paste.
- Improved operational visibility.
- Reduced reconciliation errors.

---

# 2️⃣ Misloads Deficit Alert System

## Overview

An automated monitoring system that proactively detects trailer deficits by comparing scheduled pickups from FMC with available empty trailers in YMS. The tool identifies shortages before they impact operations and automatically notifies stakeholders through Slack, enabling faster intervention and reducing downstream escalations.

---

## Features

- Automated trailer deficit detection
- Cross-system comparison between FMC and YMS
- Carrier-level and site-level analysis
- Automatic Slack notifications to 25+ logistics sites
- Intelligent duplicate alert management to reduce notification fatigue
- Ongoing issue tracking until deficits are resolved
- Configurable thresholds and reusable alert logic

---

## Workflow

```text
FMC Scheduled Pickups
          │
          ▼
Retrieve Pickup Data
          │
          ▼
Compare with YMS Empty Trailer Inventory
          │
          ▼
Identify Trailer Deficits
          │
          ▼
Generate Alert Summary
          │
          ▼
Send Slack Notifications
          │
          ▼
Operations Teams (25+ Sites)
```

---

## Technical Highlights

- Browser automation using Tampermonkey
- DOM scraping and structured data extraction
- Cross-system data correlation
- Carrier-wise and site-wise deficit analysis
- Slack webhook integration
- Modular alert engine for reusable business rules

---

## Current Status

Currently executed manually three times per day as part of operational monitoring.

---

## Future Enhancements

- Python automation service
- Selenium-based browser automation
- AWS EventBridge scheduling
- 24/7 unattended execution
- Historical trend reporting and analytics dashboard

---

## Business Impact

- Detects trailer shortages before operational escalations occur.
- Reduces manual monitoring effort across multiple systems.
- Enables proactive planning for operations teams.
- Helps reduce case volume by identifying deficits early.
- Improves visibility across 25+ logistics sites through automated notifications.

# 3️⃣ Yard Ops Assistant

## Overview

A conversational assistant embedded directly inside YMS.

Instead of manually searching tables, operators simply type natural-language requests.

Examples:

```text
carts

totes at PS

attached trailers

empty trailers

site inventory

carrier details
```

---

## Features

- Natural language interface
- Embedded inside YMS
- Modular data providers
- Read-tool architecture
- AI-ready design

---

## Architecture

```text
Operator

    │

Natural Language

    │

Read Tool Layer

    │

Structured Data

    │

Response Generator
```

---

## Future AI Integration

Planned support for:

- AWS Bedrock
- Google Gemini
- Enterprise LLMs

Future queries:

> Show attached trailers arriving in the last 12 hours.

> Which carriers have shortages today?

---

## Business Impact

- Faster operational decisions.
- Reduced manual searching.
- Single conversational interface.
- Foundation for AI-powered logistics.

---

# 4️⃣ FYCON Cancel Check

## Overview

Automatically detects cancelled "attached" VRIDs by cross-referencing FMC and YMS.

Previously, operators manually verified trailer status across multiple systems.

---

## Features

- Cross-system cancelled VRID detection
- Red / Green status visualization
- Running cancelled count
- Live operational updates
- Prevents incorrect dispatches

---

## Business Impact

- Eliminates manual verification.
- Detects cancellations earlier.
- Prevents dispatch mistakes.
- Improves operational accuracy.

---

# 🏗 Architecture

```text
                    Browser

                       │

                       ▼

            Tampermonkey Userscripts

                       │

      ┌────────────────┼─────────────────┐

      ▼                ▼                 ▼

     FMC              YMS            Slack API

      │                │

      └───────────┬────┘

                  ▼

        Data Correlation Engine

                  ▼

        Business Logic Layer

                  ▼

      Analytics & Decision Engine

                  ▼

      Dashboards • Alerts • Reports
```

---

# 💻 Technology Stack

| Category | Technology |
|----------|------------|
| Language | JavaScript (ES2022) |
| Browser Automation | Tampermonkey |
| DOM Parsing | Native DOM APIs |
| Correlation | Custom Matching Engine |
| Notifications | Slack Webhooks |
| Testing | Vitest |
| Property Testing | fast-check |
| Future Automation | Python + Selenium |
| Cloud | AWS |
| AI | AWS Bedrock / Google Gemini |

---

# 📁 Repository Structure

```text
Logistics-Automation-Suite/

│
├── userscripts/
│   ├── reconciler.user.js
│   ├── slack_auto_alert.user.js
│   ├── yard-assistant.user.js
│   ├── cancel-check.user.js
│   └── shared.js
│
├── src/
│   └── core/
│
├── test/
│
├── screenshots/
│
├── demo/
│
├── .kiro/
│   └── specs/
│
├── LICENSE
│
└── README.md
```

---

# ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/Logistics-Automation-Suite.git
```

Install dependencies:

```bash
npm install
```

Run tests:

```bash
npm test
```

Build:

```bash
npm run build
```

Install the desired Tampermonkey userscript and open the supported logistics pages.

---

# ▶️ Usage

Typical workflow:

```text
Open FMC

↓

Open YMS

↓

Run Userscript

↓

Automatic Data Collection

↓

Cross-System Analysis

↓

Operational Dashboard

↓

Slack Notifications
```

---

# 🧪 Testing

The project includes automated testing to ensure reliable behavior across changing operational scenarios.

### Test Strategy

- Unit Testing
- Property-Based Testing
- Parser Validation
- Correlation Verification
- Edge Case Coverage

Frameworks:

- Vitest
- fast-check

---

# 🧠 Engineering Challenges

This project demonstrates solutions to practical engineering problems:

- Cross-system data correlation between independent logistics platforms.
- Reliable DOM parsing for dynamic web applications.
- Intelligent Slack alert suppression while keeping unresolved issues visible.
- Reusable modules shared across multiple automation scripts.
- Multi-site deployments through configurable site mappings.
- Separation of data collection, business logic, and presentation to support future AI integration.

---

# 📸 Screenshots 

## FMC–YMS Reconciler

```
<img width="805" height="456" alt="image" src="https://github.com/user-attachments/assets/74b30540-3303-426f-9437-54fefe385da0" />

<img width="224" height="668" alt="image" src="https://github.com/user-attachments/assets/83abbe47-b829-4ef5-9a4b-129c1d6ea7aa" />



---

## Misloads Deficit Alerts

<img width="867" height="510" alt="image" src="https://github.com/user-attachments/assets/e1ab0af2-4eac-4d74-b241-bd4c75442ccb" />
<img width="513" height="297" alt="image" src="https://github.com/user-attachments/assets/024c2236-47ca-4379-94d2-b2cf33d011d4" />

```

---

## Yard Ops Assistant

```
screenshots/yard-assistant.png
```

---

## FYCON Cancel Check

```
```

---

---

# 🛣 Roadmap

- Python automation service
- Selenium-based execution
- AWS EventBridge scheduling
- Cloud-hosted monitoring
- AI-powered operational assistant
- Predictive trailer shortage forecasting
- Conversational analytics
- Operational dashboards
- LLM-generated summaries

---

# ⭐ Why This Project?

These projects demonstrate **production-scale logistics automation** serving real teams across **25+ sites**, with measurable improvements in operational efficiency, error reduction, and proactive case prevention.

The architecture separates **data acquisition**, **business logic**, and **presentation**, making it ready for future **AI and LLM integration** while delivering immediate business value through automation, analytics, and intelligent decision support.

---

# 📄 License

This repository is intended for educational, portfolio, and technical interview purposes. Any proprietary business logic or organization-specific implementation details have been generalized or excluded.
