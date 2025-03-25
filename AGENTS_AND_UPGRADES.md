# 🧠 Exelant Script Generator – Multi-Agent Workflow Guide

This document outlines the complete multi-agent system for script generation, refactoring, composition, and governance across spatial workflows. It complements the `README.md` and should be used as the reference for how the project operates.

---

## 🔄 Full Process Overview

| Step | Agent | Purpose | Input | Output |
|------|-------|---------|-------|--------|
| 1️⃣ | **Script Generator Agent** | First pass generation from structured config | Script name, description, config, category, languages | Initial .py or .sql script |
| 2️⃣ | **Script Refactor Agent** | Polish and modularize with refactored logic | Existing script + new config/goal | Cleaned-up script |
| 3️⃣ | **Workflow Composer Agent** | Integrate related scripts into one pipeline | List of scripts in a category | Master pipeline + summary |
| 4️⃣ | **Meta Agent (Vision Tracker)** | Manage the universe of scripts, flag overlaps | New script + manifest | Duplicates, merge ideas, meta manifest update |

---

## 📦 Output Behavior

All generated and refactored scripts are saved to the `/output/` directory by default. Scripts are named using a slugified version of the script title (e.g., `zoning_violation_detector.py`).

Associated metadata is saved in:
- `/config/scripts_index.yaml`
- Planned: `/output_metadata/` for logging, versioning, and testing

---

## 🧪 Testing & Review Enhancements

### ✅ Unit Testing Generator (Planned)
Each script will optionally generate a `test_<script>.py` file inside `/tests/` using `pytest`.

### ✅ Code Review Loop
After generation or refactor, scripts can be sent back to GPT for:
- Comment quality
- Logic review
- Docstring + config validation

---

## 🧠 Prompt Improvements (To Implement)

| Area | Upgrade |
|------|---------|
| Prompting Quality | Refactor prompts to include test case examples or I/O examples |
| Storage | Add DuckDB or PostgreSQL logging of generation history |
| Sheet Sync | Two-way sync with Google Sheet (update script name + file status) |
| Unit Testing | Autogenerate `pytest` tests for each script |
| Code Review Loop | Auto-send refactored scripts to GPT for review & annotation |

---

## 🗂️ Script Input Format

Each script entry should follow this YAML format (pulled from CSV or Sheet):

```yaml
- script: "zoning envelope builder"
  description: "calculate maximum building envelope from zoning rules and parcel shape"
  config: "input: parcel shapefile and zoning csv; process: apply rule-based modifiers (far, height, setbacks); output: constrained 2d/3d polygon layer"
  org: "exelant"
  category: "zoning & land use"
  languages: "python"