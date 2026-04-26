# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project: Castello Rosso Marketing Campaign

Castello Rosso is an Italian-themed showcase bakery, café, and bistro in Pilisvörösvár, Hungary. This repository contains the marketing agent infrastructure for outbound B2B prospecting.

## Marketing Specialist Agent

The primary agent lives at `agents/marketing-specialist.md`. Read that file at the start of every session — it contains the agent's full persona, scoring system, workflow, and red flags.

**To activate the agent**, start a Claude Code session and say something like:
- *"Prospect for corporate catering clients in Budapest — find 10 leads"*
- *"Find event venues near Pilisvörösvár and score them"*
- *"Show me all 🟢 contacts from the tracker"*
- *"Research [business name] and add them to the tracker"*

The agent will use web search to find businesses, score them, and append rows to `data/prospect-tracker.csv`.

## Repository Structure

```
agents/
  marketing-specialist.md   # Agent persona, scoring criteria, workflow
data/
  prospect-tracker.csv      # Running prospect list (append only)
```

## Scoring System

Prospects are scored out of 12 across 8 columns (D–K). See `agents/marketing-specialist.md` for the full breakdown. The scoring criteria should be updated from the official Scoring Guide (Tab 2) when available.

Status thresholds:
- 🟢 Contact Now: 8–12 points
- 🟡 Monitor: 5–7 points
- 🔴 Skip: 0–4 points

## Key Rules

- **Always append** to `prospect-tracker.csv` — never overwrite existing rows
- **Always read** `agents/marketing-specialist.md` before prospecting
- Update scoring criteria and red flags in the agent file when the official Scoring Guide and Red Flags tabs are shared
