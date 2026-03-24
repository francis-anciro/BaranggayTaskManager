# MyBarangay

A CLI-based task management and civic engagement platform that enables barangay residents to submit community concerns, vote on priorities, and track resolution progress.

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

## Data Structures

| Structure | Role | Time Complexity |
|-----------|------|-----------------|
| `ArrayList` | Stores and iterates task objects | O(N) sort |
| `Dictionary` | Task lookup by ID | O(1) average |
| `Set` | Duplicate prevention | O(1) lookup |

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
| SDG 11 | Inclusive, safe, resilient communities |
| NIASD "Mabagal" | Counters slow civic response via digital tooling |
