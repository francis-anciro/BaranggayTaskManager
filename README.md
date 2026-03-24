# MyBarangay
A CLI-based task management and civic engagement platform that enables barangay residents to submit community concerns, vote on priorities, and track resolution progress.

---

## Problem

Local barangay governance is largely reactive — residents report issues through walk-ins, physical forms, or hotlines like 8888, with no structured way to prioritize or track resolution. Urgent concerns like broken infrastructure or safety hazards get buried in informal queues. MyBarangay replaces that with a democratic, structured pipeline: submit, vote, prioritize, resolve.

---

## Overview
MyBarangay addresses the gap between citizens and local governance by providing a structured, democratic process for surfacing and resolving community issues — aligned with **SDG 11** (Sustainable, Inclusive Communities) and the **NIASD "Mabagal" scenario**.

---

## Features
- Submit community concerns/suggestions
- Duplicate detection via normalized string matching
- Vote-based prioritization
- Completion tracking with ordered resolution

---

## Design Decisions

The core challenge was enforcing a structured civic workflow while keeping it lightweight with no external dependencies.

| Structure | Role | Why |
|-----------|------|-----|
| `ArrayList` | Stores and iterates task objects | Ordered, sortable by vote count |
| `Dictionary` | Task lookup by ID | O(1) access for fast retrieval during voting |
| `Set` | Duplicate prevention | O(1) lookup to reject redundant submissions |

---

## Project Structure
```
MyBarangay/
├── Task.py          # Task model (taskID, taskName, votes)
├── TaskManager.py   # Core logic (suggest, vote, done, finalize, showList)
└── main.py          # Entry point and user interaction loop
```

---

## How It Works
1. **Suggestion Period** — Users input concerns; duplicates are rejected automatically.
2. **Voting Period** — Users vote by Task ID; list displays live standings.
3. **Finalization** — Tasks are sorted by vote count (descending).
4. **Completion Period** — Officials mark top-priority tasks as done sequentially.

---

## Usage
```bash
python main.py
```
Follow the prompts for each period. Enter `STOP` to end the suggestion phase; enter `0` to close voting.

---

## Requirements
- Python 3.x
- No external dependencies

---

## Alignment

| Framework | Relevance |
|-----------|-----------|
| SDG 11 | Promotes inclusive, participatory governance at the community level |
| NIASD "Mabagal" | Philippine framework describing society's lag in adopting technology for civic response — this app directly counters that pattern |
