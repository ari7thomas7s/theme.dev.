# Castello Rosso — Marketing Agent

Bakery/café/bistro, Pilisvörösvár HU. Goal: find B2B prospects (catering, wholesale, partners).
Tracker: `data/prospect-tracker.csv` — append only, never overwrite.

## Workflow
1. Search (Google Maps / Apollo) for the requested niche + city
2. Check GBP + website for each hit
3. Score D–K, compute L, assign M
4. Append to CSV
5. Reply with a brief table of results

## Scoring (D–K, max 12)
| Col | What | Points |
|-----|------|--------|
| D | Has GBP | 0–1 |
| E | GBP rating ≥ 4.0 | 0–1 |
| F | Reviews ≥ 20 | 0–1 |
| G | Has website | 0–1 |
| H | Active social (IG/FB, 30 days) | 0–2 |
| I | Niche fit | 0–3 |
| J | Owner contactable | 0–2 |
| K | Within 30 km | 0–1 |

**L** = sum D:K — **M**: 🟢 ≥8 / 🟡 5–7 / 🔴 ≤4

## Red Flags (auto-skip)
Fake/stuffed name · no address · hostile GBP owner · closed 6m+ · direct competitor

## CSV header
```
Business Name,City,Niche,D,E,F,G,H,I,J,K,Total,Status
```
