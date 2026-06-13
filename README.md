# Steam Game Success — Tableau Dashboard & Data Story

**Module:** Machine Learning and Visualization for Data (MLVDA) · MSc Information Technology Management · BSBI
**Author:** Ibrahim Eren Kilisli · Student ID: Q1119709 · 2026

---

## Live Dashboard

[![Open Tableau Dashboard](https://img.shields.io/badge/Tableau-Open%20Dashboard-blue?logo=tableau)](https://public.tableau.com/app/profile/ibrahim.eren.kilisli/viz/steam_dashboard_17813512662100/Dashboard1?publish=yes)

**[https://public.tableau.com/app/profile/ibrahim.eren.kilisli/viz/steam_dashboard_17813512662100/Dashboard1?publish=yes](https://public.tableau.com/app/profile/ibrahim.eren.kilisli/viz/steam_dashboard_17813512662100/Dashboard1?publish=yes)**

---

## Overview

This repository contains the Tableau workbook and supporting files for the MLVDA assignment *"Tableau Dashboard and Data Story"*. The dashboard takes the output of a prior machine-learning project — Wilson-scored success labels and K-Means market archetypes for 56,632 Steam games — and turns them into an interactive, prescriptive analytics tool aimed at indie developers and small publishers.

The dashboard answers one question: **given a game's market segment, price, genre and platform reach, what does the data say about its chances of success on Steam, and what should a developer do about it?**

---

## What the dashboard contains

Five views, three KPI cards and a live success-threshold slider, all built on `steam_clean.csv` (56,632 games, 18 columns).

| View | Chart type | Question it answers |
|---|---|---|
| Archetype Success | Sorted horizontal bar | Which market segment succeeds most often? |
| Market Trend | Dual-axis combo (bars + line) | How have release volume and success rate moved over time? |
| Price vs Success | Scatter plot (point size = game count) | Does a higher price mean a better-received game? |
| Genre Performance | Treemap (size = count, colour = success rate) | Which genres punch above their weight? |
| Platform Heatmap | Heatmap with labelled cells | Does platform reach pay for every archetype? |

The **Success Threshold** parameter (range 0.50–0.95, step 0.05, default 0.80) recalculates every number on the board when dragged, so the reader, not the author, decides where the bar for success belongs.

A filter action on the archetype bar chart turns the whole board into a single-archetype view on click; clicking empty space restores the full market.

---

## Key findings

- **Archetype is the dominant factor.** Proven Classics succeed 45 % of the time; Budget/Casual games succeed 16 %. The threefold gap dwarfs any genre or price effect.
- **Price does not buy reception.** New Premium releases (~$10) succeed 29 %; Proven Classics (~$5) succeed 45 %.
- **The market is crowded and the bar has not dropped.** The success rate slides as annual releases surge through the 2010s; the post-2018 rebound is partly a survivorship effect in recent review counts.
- **Genre tilts the odds modestly.** RPG, Adventure and Strategy lead at 33, 32 and 30 %; the spread is real but small compared to the archetype gap.
- **Platform reach pays only for established games.** Proven Classics climb from 40 % (one platform) to 79 % (three). New Premium releases on three platforms succeed 0 % — 63 games, none cleared the bar.

---

## Recommendations for indie developers

1. **Position before planning.** Identify the archetype the game will enter and treat its success rate as the honest baseline — it varies threefold.
2. **Set price for revenue, not reputation.** Higher prices bring no reception benefit.
3. **Sequence platforms after proof.** Port a well-received game aggressively; do not launch a new premium title across three platforms at once.
4. **Choose genre within the stronger bands**, but do not treat genre alone as a strategy.

---

## Data source

The dashboard runs on `steam_clean.csv`, produced by cleaning the [Steam Games Dataset (FronkonGames, Kaggle)](https://www.kaggle.com/datasets/fronkongames/steam-games-dataset). The Wilson lower-bound scoring, log transforms and K-Means clustering were settled in the prior ML project and are not reproduced inside Tableau — a single flat file means every number on the board traces directly back to the model that produced it.

---

## Repository contents

| File | Description |
|---|---|
| `steam_dashboard.twbx` | Packaged Tableau workbook (dashboard + data story) |
| `README.md` | This file |
| `LICENSE` | MIT |

---

## Citation

> Kilisli, I.E. (2026) *Steam game Tableau dashboard* [Tableau workbook and supporting files]. BSBI, MSc Information Technology Management.
> Available at: [https://github.com/ErenKilisli/steam-game-tableu](https://github.com/ErenKilisli/steam-game-tableu)
