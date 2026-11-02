# Project Checkpoint: Research Questions and Task Formulation

**The NBA's Three-Point Revolution, 2004–2024** · Group members: [add names]

## Project Overview

**Topic.** How NBA shot selection shifted away from mid-range jumpers toward three-pointers and shots at the rim between 2004 and 2024, and whether that shift paid off for teams.

**Dataset.** [NBA_Shots_04_24](https://github.com/DomSamangy/NBA_Shots_04_24): every regular-season NBA shot attempt from 2003–04 to 2023–24 (about 4 million rows, one CSV per season), collected from the NBA Stats API. Each row is one shot, with season, date, team, player, position, made/missed, shot type (2PT/3PT), court zone, distance, x/y court location, quarter and time left. We will join team win–loss records per season from [Basketball-Reference](https://www.basketball-reference.com/).

**Domain.** Sports analytics. Around the mid-2010s, teams began using data to show that a three-pointer at about 35% is worth more per shot than a long two at about 45%. Our dashboard lets fans, students and analysts see how that idea reshaped the game.

Below, each high-level question is a task in Gotz and Zhou's framework, each mid-level question is a sub-task, and each low-level question is written as an abstract action–target pair, using Amar et al.'s low-level analytic primitives as the action verbs.

## Research Questions: Task, Sub-task and Operation Levels

### Task 1: Understand how the league's shot selection changed from 2004 to 2024.

| Mid-level question (sub-task) | Action (Amar primitive) | Target |
|---|---|---|
| 1a. How has the share of shots taken at the rim, from mid-range and from three changed across seasons? | Characterize Distribution | Proportion of shot attempts by zone, per season (trend over time) |
| 1b. In which seasons did the three-point attempt rate grow the fastest? | Compute Derived Value → Find Extremum | Year-over-year change in league three-point attempt rate |

### Task 2: Evaluate whether the shift toward threes was justified by the value of each shot.

| Mid-level question (sub-task) | Action (Amar primitive) | Target |
|---|---|---|
| 2a. Which shot zones produce the most points per shot attempt? | Compute Derived Value → Sort | Points per shot (made % × point value) for each zone |
| 2b. Did three-point accuracy go down as teams took more threes? | Correlate | Relationship between league three-point attempts and three-point percentage across seasons |

### Task 3: Identify which teams led the change and whether it helped them win.

| Mid-level question (sub-task) | Action (Amar primitive) | Target |
|---|---|---|
| 3a. Which teams had the highest three-point attempt rate in each season? | Filter (season) → Find Extremum | Team three-point attempt rate within a selected season |
| 3b. Do teams that take more threes win more games? | Correlate | Relationship between team three-point attempt rate and win percentage (team-seasons) |

### Task 4: Explore how shooting changed for different positions and individual players.

| Mid-level question (sub-task) | Action (Amar primitive) | Target |
|---|---|---|
| 4a. How have the court locations of shots taken by centers changed between early and recent seasons? | Filter (position, season) → Characterize Distribution | Spatial distribution of shot locations on the court |
| 4b. Which players have shot profiles that are unusual for their position? | Find Anomalies | Outliers in player zone-share profiles compared with their position's average |
