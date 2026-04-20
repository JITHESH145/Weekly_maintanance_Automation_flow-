<div align="center">

# 🐟 Fishing Weekly Maintenance Automation Workflow

### A Complete End-to-End Automation Pipeline for Weekly Product Maintenance

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Automation](https://img.shields.io/badge/Automation-Agent%20%7C%20Skill%20%7C%20Code-green.svg)](#automation-approaches)
[![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen.svg)](#)
[![Year](https://img.shields.io/badge/Year-2026-orange.svg)](#)

*A highly efficient workflow leveraging modern automation technologies to handle the most uncertain and inconsistent product data in weekly maintenance cycles.*

---

**Created by Jithesh** · April 2026

[Getting Started](#-getting-started) · [Phases](#-automation-phases) · [Requirements](#-requirements) · [Contributing](#-contributing)

</div>

---

## 📖 Introduction

This repository documents a **fully automated weekly maintenance pipeline** designed to replace manual, repetitive product maintenance workflows. By combining three distinct automation approaches — **Agent-Based**, **Skill-Based**, and **Code-Based** — this system handles inconsistent product data across multiple merchants with minimal human intervention.

The pipeline is divided into **6 phases**, each targeting a specific stage of the maintenance cycle. Together, they achieve an estimated **50% reduction in time and effort**, serving as a strong foundation for fully automated workflows in the future.

> **⚠️ Important:** Always include a human in the loop to verify outputs and avoid failures. Proper research and time allocation are essential for successful execution.

---

## 🔧 Automation Approaches

This workflow uses three core automation techniques, each chosen based on the nature of the task:

### 🤖 Agent-Based

A fully automated agent hosted on a server or running locally. Best suited for **repetitive tasks** that remain consistent across every cycle. Agents run 24/7 in the cloud and can be scheduled to trigger at specific intervals.

### 📝 Skill-Based

A well-structured `skills.md` file that can be fed into any LLM (e.g., Claude) to give it a deep understanding of the process. Ideal for tasks where **data is highly inconsistent** and cannot be handled by static code or agents alone.

### 💻 Code-Based

A complete automation script designed for tasks that are **consistent and predictable**. Requires minimal to no changes between cycles, making it reliable and low-maintenance.

---

## 🔄 Automation Phases

```
┌──────────┐    ┌──────────────┐    ┌───────────────┐    ┌──────────────┐    ┌────────────┐    ┌─────────┐
│ Phase 1  │───▶│   Phase 2    │───▶│    Phase 3    │───▶│   Phase 4    │───▶│  Phase 5   │───▶│ Phase 6 │
│Extraction│    │  Processing  │    │Template Fill  │    │Data Curation │    │ Validation │    │ Testing │
│  🤖 Agent │    │  📝 Skill    │    │  💻 Code      │    │  📝 Skill    │    │  👤 Manual  │    │ 🤖 Agent│
└──────────┘    └──────────────┘    └───────────────┘    └──────────────┘    └────────────┘    └─────────┘
```

---

### Phase 1 — Extraction `🤖 Agent-Based`

**Problem:** The extraction code was being run manually every week for each merchant with minor changes, consuming significant time and effort.

**Solution:** Build an automated agent that triggers on a weekly schedule to run the extraction code for every merchant. This agent runs **24/7 in the cloud** using Claude agents available with enterprise plans, integrated with the Routines quota.

**Requirements:**
- Proper understanding of how the extraction code works — tools, technologies, and weekly changes in the codebase
- Proper knowledge transfer (KT) from the domain expert

**Bonus:** The agent can later be connected to **Google Drive** to automatically place extracted files in designated folders for documentation purposes.

---

### Phase 2 — Extract Processing (In-Scope & Out-of-Scope) `📝 Skill-Based`

**Problem:** This is the most time-consuming area where the majority of manual effort is spent. The data varies significantly across merchants, and this level of inconsistency cannot be handled by static code or agents.

**Solution:** Create a comprehensive `skills.md` file with detailed instructions, then feed it into Claude. The skill file defines how to categorize in-scope vs. out-of-scope products, what to filter, remove, and keep.

**Requirements:**
- Training and understanding of Claude Skills and how to use the Skills Builder
- A detailed list of requirements for categorizing in-scope/out-of-scope products per merchant category

**Perks:**
- Eliminates repetitive prompting — instructions are clearly embedded in the skill file
- Simply upload the skill file each time; no need to re-explain the process

**Output:** A well-structured file with clear labelling and filtered products.

---

### Phase 3 — Template Filling `💻 Code-Based`

**Problem:** Downloading templates for each product category and manually filling columns with values from the extract file is repetitive and time-consuming.

**Solution:** Build a complete automation script that maintains a **library of all available templates** for each merchant. When an extract file is uploaded, the script automatically:
1. Identifies the correct template from its library
2. Creates a copy of the template
3. Maps and fills the columns from the extract file (e.g., `variant_price` → `min_ad_price`, `Sku` → `variant_id`)
4. Outputs the completed template file

**Requirements:**
- Strong knowledge of **NumPy** and **Pandas** libraries
- Proficiency in **Python programming**
- A complete collection of all template files available for each merchant
- Clear mapping documentation for column-to-column relationships

**Output:** A well-structured file ready for data curation.

---

### Phase 4 — Data Curation `📝 Skill-Based`

**Problem:** Finding values for each product's attributes is a crucial phase. Traditionally, values were either searched manually or obtained through vague prompts to an LLM, leading to inconsistent data.

**Solution:** Create a dedicated `skills.md` file that clearly defines the attribute value retrieval process. This phase distinguishes between two types of attributes:

| Attribute Type | Description | Examples |
|:---|:---|:---|
| **Ruler-Based** | Custom attributes created to meet recommendation needs; do not exist as standard manufacturer specs | Connectivity (wireless connectivity), Physical Connectivity (wired connection options) |
| **Manufacturer-Based** | Standard attributes assigned to a product by its manufacturer | Weight, Color, Rod Length |

**Requirements:**
- Differentiate ruler-based from manufacturer-based attributes for each product category
- Define step-by-step retrieval processes in the skill file, including **sample values** to reduce hallucination
- Clearly specify **value formats** to avoid normalization issues later
- Understanding of connectors (Playwright, Chromium, Firecrawl, etc.) for better data extraction
- Proper understanding of Claude Skills

**Output:** A completed file ready for validation and loading.

---

### Phase 5 — Validation & Loading `👤 Manual`

This phase requires **no automation** as it is effortless and less time-consuming. Human review at this stage ensures data quality before final loading.

---

### Phase 6 — Testing `🤖 Agent-Based`

**Solution:** Automate testing using the **Playwright CLI** tool. The approach follows structured steps covered in prior knowledge-sharing sessions and can be refined through proper research, trial, and error.

---

## 📋 Requirements

### Technical Skills

| Skill | Phases |
|:---|:---|
| Python (NumPy, Pandas) | Phase 3 |
| Claude Skills / Skills Builder | Phase 2, Phase 4 |
| Claude Agents (Enterprise Plan) | Phase 1, Phase 6 |
| Playwright / Chromium / Firecrawl | Phase 4, Phase 6 |
| Google Drive API (optional) | Phase 1 |

### Resources Needed

- Access to Claude Enterprise Plan with Routines quota
- Domain expert for knowledge transfer on extraction code
- Complete collection of merchant template files
- Documented attribute categorization per product category
- Cloud infrastructure for running 24/7 agents

---

## 📊 Expected Impact

```
┌─────────────────────────────────────────────────┐
│          EFFICIENCY GAINS                       │
│                                                 │
│  ⏱️  Time Saved .............. ~50%             │
│  🔁  Manual Repetition ....... Eliminated       │
│  📈  Consistency ............. Significantly    │
│                                Improved         │
│  🔧  Flexibility ............. Fully            │
│                                Customizable     │
│  🧩  Scalability ............. Merchant-        │
│                                Agnostic         │
└─────────────────────────────────────────────────┘
```

---

## 🚀 Getting Started

1. **Clone this repository**
   ```bash
   git clone https://github.com/your-username/fishing-weekly-maintenance-automation.git
   cd fishing-weekly-maintenance-automation
   ```

2. **Review each phase's documentation** in the `/phases` directory

3. **Set up the required tools:**
   - Install Python dependencies: `pip install numpy pandas`
   - Set up Playwright: `npx playwright install`
   - Configure Claude Enterprise access

4. **Start with Phase 1** and progressively implement each phase

5. **Always validate outputs** with a human in the loop before loading

---

## 🗂️ Project Structure

```
fishing-weekly-maintenance-automation/
├── README.md
├── phases/
│   ├── phase-1-extraction/
│   │   └── agent-config.md
│   ├── phase-2-processing/
│   │   └── skills.md
│   ├── phase-3-template-filling/
│   │   ├── template-filler.py
│   │   └── templates/
│   ├── phase-4-data-curation/
│   │   └── skills.md
│   └── phase-6-testing/
│       └── playwright-tests/
├── config/
│   └── merchant-mappings.json
└── LICENSE
```

---

## 🤝 Contributing

Contributions are welcome! If you have ideas to improve any phase or want to add support for new merchant types:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📝 Notes

- This pipeline is **flexible** and can be customized based on specific needs and requirements
- It serves as a **starting point** for fully automated workflows
- **Human-in-the-loop verification** is strongly recommended at every stage to prevent failures
- Proper time allocation and research are essential — rushing implementation can lead to poor results

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">

**Built with purpose by Jithesh** · 2026

*Turning manual maintenance into automated excellence*

</div>
