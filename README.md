# Courts Without Borders: Global Sports League Scheduling

**IMMC 2025 Global Finalist.** Team paper for the International Mathematical Modeling Challenge, defended in person at the global finalist presentation in Hong Kong. My role: algorithm lead.

The task: design a fair and efficient season for a new international league. We chose basketball, selected 20 teams, compared competition formats, and scheduled the group stage so travel stays short and evenly shared.

## 1. Team selection (AHP)
* Ranked teams with the Analytic Hierarchy Process on three indicators: team honors, popularity, and market value.
* Geographic representation was a hard constraint. Result: 20 teams from 16 countries on 6 continents.

## 2. Format comparison (Monte Carlo)
* Compared our "play-in-and-off" format (preseason, double round-robin groups, play-in, knockout) with World Cup, double round-robin, MLS, and Swiss formats.
* Simulated 10,000 seasons per format in Python, drawing each match result from a Bradley-Terry model on seed ratings.
* Fairness: the Top-4 difference (gap between seed and simulated finish for the top four seeds) and the Jensen-Shannon divergence between the #1 seed's finish distribution and the double round-robin benchmark.
* Attractiveness: match quality (sum of the two ratings) times competitiveness (1 minus the normalized rating gap).
* After normalizing and weighting the three measures, play-in-and-off ranked first. Its JS divergence from double round-robin was 0.42, against 0.53 for Swiss and World Cup.

## 3. Group-stage schedule (NSGA-II genetic algorithm)
* Four groups of five teams play a double round-robin with one bye per round, no back-to-back games between the same two teams, and direct flights between consecutive away games.
* Two objectives: total travel distance, and the standard deviation of travel distance across teams. Search uses NSGA-II selection, two-point crossover, and swap mutation.
* From the Pareto front we took the shortest schedule whose standard deviation stays under one day of flying (19,200 km at 800 km/h).
* Result: 155,405 km of total travel with a 4,034 km standard deviation. In one group, the LA Lakers fly 28,190 km and the Guangdong Southern Tigers 27,868 km.
* Turned the match order into a nine-month timetable that accounts for jet lag and rest days, and extended the model to 24 teams (total travel rises by 70,039 km).

## Files
* `IMMC_Paper.pdf`: the full paper, with AHP matrices, simulation results, GA pseudocode, and the season schedule.
