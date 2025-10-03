# NBA Data Analysis: The Stephen Curry Effect

## Overview
In this project, I investigate one of my favorite obsessions—the NBA!  

One of the most significant figures in modern basketball is **Stephen Curry**, son of former Toronto Raptor player Dell Curry. His exceptional skills and record-breaking performances have led to championships and MVP awards, and there is ongoing discussion about how he has fundamentally changed the game with his shooting style.  

This analysis explores the correlation between Curry’s presence in the NBA and changes in the league’s dynamics using historical player statistics from 1999–2000 to 2019–2020 seasons.

---

## Dataset
The dataset used is `players_stats_by_season_full_details.csv`, which contains detailed player statistics for NBA, playoffs, and international leagues. Key features include:

- League, Season, Season Stage, Player Name  
- Games Played (GP), Total Minutes (MIN), Field Goals Made (FGM), Field Goal Attempts (FGA)  
- Three-Pointers Made (3PM), Three-Pointers Attempted (3PA)  
- Free Throws Made (FTM), Free Throws Attempted (FTA)  
- Turnovers (TOV), Personal Fouls (PF), Rebounds, Assists, Steals, Blocks, Points (PTS)  
- Player physical information: Height, Weight, Birth Year/Month/Date  
- Draft and High School information  

---

## Approach
The analysis is divided into multiple parts:

### Part 1: Data Preprocessing
- Imported necessary libraries and loaded the dataset.
- Filtered for **NBA regular season** to maintain consistency across seasons.
- Handled missing values by imputing mean values for `birth_year`, `weight_kg`, and `height_cm`.
- Created **per-game statistics** columns such as:
  - `PPG`, `MPG`, `TOVPG`, `3PAPG`, `3PMPG`, `FGAPG`, `FGMPG`, `FPG`
- Calculated **True Shooting Percentage (TS%)** to measure player scoring efficiency:

`TS% = (Points Scored) / (2 * (Field Goal Attempts + 0.44 * Free Throw Attempts)) * 100`

- Aggregated player statistics per season and filtered players with at least 1000 shooting attempts for reliability.

---

### Part 2: General NBA Trends
- Split the data into **Before Curry (BC: 1999–2000 to 2008–2009)** and **After Curry (AC: 2009–2010 onwards)**.
- Analyzed physical and performance metrics:
  - Height, Weight, Age distributions
  - Games Played and Minutes Per Game
- Observations:
  - AC era players are generally taller, heavier, and have more variability in age.
  - BC players played more games and had higher minutes per game; AC players include more low-minute and low-game appearances.

**Height Distribution (BC vs AC):**  
![Height Comparison](https://github.com/D1Massacre007/NBA-Analytics/blob/efead3302a659b603b6f4028545705d01475113b/output1.png)

---

### Part 3: Game Analysis
- Focused on gameplay trends and statistical changes between BC and AC.
- Applied **t-tests** to examine if changes in metrics like `3PAPG`, `FPG`, and `TOVPG` were statistically significant.
- Observations:
  - Metrics like TOVPG and FPG showed statistically significant differences (p-value < 0.05), indicating shifts in gameplay style.

**BC vs AC Turnovers and Fouls Per Game:**  
![TOVPG and FPG Comparison](https://github.com/D1Massacre007/NBA-Analytics/blob/efead3302a659b603b6f4028545705d01475113b/output6.png)

---

### Part 4: In Praise of Stephen Curry
- Isolated Stephen Curry’s statistics and compared them with the rest of the league.
- Visualized Curry’s efficiency using **scatter plots** for:
  - `3PMPG` vs. `3PAPG` (3-point performance)
  - `FGMPG` vs. `FGAPG` (field goal performance)
- Observations:
  - Curry is an **outlier in efficiency**, outperforming most other NBA players in his era.

**Scatter Plots Comparing Curry with AC Players:**  
![Curry vs AC Players](https://github.com/D1Massacre007/NBA-Analytics/blob/efead3302a659b603b6f4028545705d01475113b/output7.png)

---

### Statistical Significance vs. Causality
While statistical tests show significant differences in NBA gameplay metrics after Curry’s emergence, **correlation does not imply causation**. Other factors (rule changes, player development, coaching strategies) may also have contributed to these trends. Careful analysis is required to avoid overstating Curry’s individual impact.

---

## Tools & Libraries
- Python 3.x  
- `pandas`, `numpy` – Data handling  
- `matplotlib`, `seaborn` – Visualizations  
- `scipy.stats` – Statistical testing  
 


## Key Takeaways
- NBA players’ physical attributes and playing styles have evolved significantly between BC and AC eras.  
- Stephen Curry has a notable statistical impact on 3-point shooting efficiency and league trends.  
- Statistical significance was observed in several metrics, but causal inference remains limited due to potential confounding variables.  

