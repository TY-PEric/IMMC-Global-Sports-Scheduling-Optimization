# Courts Without Borders: Global Sports League Scheduling Optimization

**Achievement: Global Finalist, International Mathematical Modeling Challenge (IMMC)**
**Defense Location: Invited for the Global Finalist Presentation in Hong Kong**

This repository contains our team's research paper and algorithmic framework submitted to the **IMMC**. Advancing past rigorous preliminary rounds, our team was selected to travel to **Hong Kong** to deliver a live, in-person presentation and defense for the Global Finalist Award. This project constructs a comprehensive mathematical model to design, simulate, and schedule a fair and efficient Global Sports League (GSL).

## Project Overview
To establish a sustainable global tournament, we tackled team selection, tournament format design, and logistical travel optimization. 
* **Sport & Team Selection:** Identified basketball as the optimal sport for global accessibility and selected 20 teams from 16 countries across 6 continents.
* **Format Simulation:** Designed a novel "Play-in-and-off" format and benchmarked it against World Cup, Double Round Robin (DRR), MLS, and Swiss formats. 
* **Travel Optimization:** Addressed the massive carbon footprint and fatigue of international travel by minimizing total global flight distances while balancing equitable rest periods.

## Core Mathematical Modeling & Algorithms

### 1. Team Selection via AHP
* Applied the **Analytic Hierarchy Process (AHP)** to objectively rank teams based on three indicators: team honor, popularity, and market value. 
* Implemented strict geographical constraints to ensure every continent was represented.

### 2. Format Evaluation via Monte Carlo Simulation
* **10,000-Season Simulation:** Used Monte Carlo methods to sample 10,000 seasons to evaluate format fairness and audience attractiveness.
* **Fairness Metrics:** Calculated Top-4 Difference and utilized **Jensen-Shannon (JS) Divergence** to compare the first seed's rank distribution against a DRR benchmark.
* **Attractiveness Metrics:** Evaluated game quality and competitiveness dynamically using the **Bradley-Terry model**.

### 3. Schedule Optimization via Genetic Algorithms (GA)
* Formulated a multi-objective optimization problem to minimize both total travel distance and the standard deviation of travel distances across groups.
* Implemented a custom **Genetic Algorithm** (utilizing two-point crossover and swap mutation) with constraints to prevent back-to-back matches and manage bye rounds.

## Key Results
* **Live Defense:** Successfully defended our optimization methodology and algorithmic choices before an international panel of judges in Hong Kong.
* **Format Validation:** Our proposed "Play-in-and-off" format (preseason, DRR group stage, play-in, knockout) scored the highest overall in balancing fairness and attractiveness.
* **Travel Reduction:** The Genetic Algorithm optimized the total travel distance to **155,405 km**, representing a **57% optimization** compared to the worst-case routing scenario.

## Repository Contents
* `IMMC_Paper.pdf`: The complete mathematical modeling paper featuring the AHP matrices, Monte Carlo simulation results, GA pseudocode, and final optimized season schedules.
