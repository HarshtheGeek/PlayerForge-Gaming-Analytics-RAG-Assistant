# Defensive Performance

## Overview

Defensive performance represents how effectively a player avoids deaths, maintains survivability, and contributes to preventing the opposing team from gaining an advantage.

The PlayerForge dataset does not contain an explicit `defensive_score` column.

Defensive performance must therefore be interpreted using available variables such as:

- Deaths
- Kills
- Assists
- Reaction Time
- Fatigue Index
- Performance Score
- Match Outcome
- Win Probability

## Deaths

`deaths` represents the number of times a player was eliminated during a match.

Lower deaths generally indicate better survivability.

Dataset range:
- Minimum: 1
- Maximum: 22
- Median: approximately 10

Deaths should not automatically be interpreted as poor performance.

For example, an Entry Fragger may have a high death count because the role requires aggressive engagements.

## Kill-to-Death Relationship

Kills and deaths should be considered together.

A useful derived metric is:

`K/D Ratio = kills / deaths`

Higher K/D generally indicates greater elimination efficiency.

Examples:

- High kills + low deaths → highly efficient performance
- High kills + high deaths → aggressive performance
- Low kills + low deaths → passive or survival-oriented performance
- Low kills + high deaths → weak overall combat efficiency

The K/D ratio is not directly stored in the dataset and can be calculated when required.

## Survivability

Survivability should primarily be evaluated using deaths.

A player with fewer deaths may provide greater consistency because they remain available to contribute to later engagements.

However, survivability alone does not determine overall performance.

A player with very low deaths but also very low kills may have less overall impact than a player with many kills and moderate deaths.

## Reaction Time

`reaction_time_ms` represents reaction time in milliseconds.

Lower reaction time generally indicates faster responses.

Dataset range:
- Minimum: approximately 118.73 ms
- Maximum: approximately 314.44 ms
- Median: approximately 220.69 ms

Lower reaction time can be considered a positive indicator when analyzing defensive reactions and combat responsiveness.

## Fatigue

`fatigue_index` ranges from 0 to 1.

Interpretation:

- 0 → minimal fatigue
- 1 → maximum fatigue

Higher fatigue may negatively affect consistency, reaction time, and overall performance.

Fatigue should be analyzed alongside reaction time and performance score rather than treated as an independent measure of skill.

## Defensive Interpretation

Examples:

- Low deaths + low fatigue → strong survivability and potentially consistent performance
- Low deaths + high fatigue → player is surviving despite elevated fatigue
- High deaths + high fatigue → possible fatigue-related performance degradation
- Low deaths + high performance score → strong overall contribution with good survivability

## Important RAG Rule

Do not claim that a player has a specific defensive ability such as:

- Block success rate
- Damage mitigation
- Utility denial
- Defensive objective success

because these metrics do not exist in the PlayerForge dataset.