# Big Data Derby 2022 — Horse Racing Tracking Analysis

Team submission for the [Big Data Derby 2022](https://www.kaggle.com/competitions/big-data-derby-2022) Kaggle competition — an **Analytics** competition (no leaderboard; entries are judged as writeups). It uses NYRA (New York Racing Association) per-stride GPS tracking data from Aqueduct, Belmont, and Saratoga to find insights into racing strategy and horse welfare.

![Relative position animation](relative_position.gif)

## Data

The competition provides ~5 Hz GPS tracking (`trakus`) for every horse in every race, plus race and start tables. Each record is a horse's latitude/longitude over time, converted to track-relative coordinates, cumulative distance, and inter-horse spacing. All notebooks here run on a consolidated master dataset, `tarratana/big-derby-master`, built for the team.

## Contents

### `final-writeup.ipynb` — the submitted analysis
The team's final competition writeup:

- **Problem statement** — what is the optimal strategy for a horse to run a race?
- **Distance analysis** — distance ran vs. finishing position, by course type and race type, including a per-segment breakdown. Finding: high placers tend to run *more* in the second half relative to their peers.
- **Ranking by segment** — how relative position evolves across the race under different track/race conditions.
- **Zone analysis** — classifying each horse's position into directional zones and tracking zone changes (most positional churn happens early).
- **Conclusion** — actionable takeaways on race strategy.

### `relative-position-visualization.ipynb` — my contribution
An **animated relative-position view** (see GIF above): each horse's position relative to the field over the course of a race, derived from the trakus table — angle/zone computation and a frame-by-frame `trakus_index` animation. This was an exploratory component developed alongside the final writeup.

## My role

Built the consolidated `big-derby-master` dataset the team's analysis runs on, and the relative-position visualization. The final writeup was authored collaboratively (primary author: teammate [rungrawinwarunanont](https://www.kaggle.com/rungrawinwarunanont)).

## Stack

`pandas` · `seaborn` · `matplotlib` (animation)
