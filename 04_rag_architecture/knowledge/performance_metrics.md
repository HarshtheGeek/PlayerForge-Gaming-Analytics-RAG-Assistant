# Performance Metrics

## Overview

The PlayerForge dataset contains several metrics used to evaluate esports player performance.

Core performance metrics include:

- Kills
- Assists
- Deaths
- Accuracy Percentage
- Reaction Time
- Fatigue Index
- Performance Score
- Win Probability
- Match Outcome
- MVP Award

## Kills

Column: `kills`

Number of opponents eliminated by the player.

Higher values generally indicate greater direct offensive output.

Dataset range:
- 4 to 30
- Median: approximately 15

## Assists

Column: `assists`

Number of assisted eliminations.

Higher values generally indicate greater team contribution.

Dataset range:
- 0 to 20
- Median: approximately 8

## Deaths

Column: `deaths`

Number of times the player was eliminated.

Lower values generally indicate better survivability.

Dataset range:
- 1 to 22
- Median: approximately 10

Deaths should always be interpreted in the context of player role.

## Accuracy Percentage

Column: `accuracy_percent`

Percentage of shots that hit the intended target.

Higher values indicate greater shooting accuracy.

Dataset range:
- Approximately 20.46% to 71.79%
- Median: approximately 44.93%

Missing values exist in the raw dataset.

## Reaction Time

Column: `reaction_time_ms`

Player reaction time measured in milliseconds.

Lower values indicate faster reactions.

Dataset range:
- Approximately 118.73 ms to 314.44 ms
- Median: approximately 220.69 ms

Missing values exist in the raw dataset.

## Fatigue Index

Column: `fatigue_index`

Represents player fatigue on a normalized scale from 0 to 1.

Interpretation:

- 0 → lowest fatigue
- 1 → highest fatigue

Higher fatigue may be associated with reduced consistency or slower reactions.

Missing values exist in the raw dataset.

## Performance Score

Column: `performance_score`

A numerical overall performance indicator provided by the dataset.

Dataset range:
- Approximately 16.58 to 87.36
- Median: approximately 44.94

Higher performance score generally indicates stronger overall performance.

The exact mathematical formula used to generate the original performance score is not specified by the CSV schema.

Therefore, the RAG assistant must not claim a specific formula unless the formula is documented elsewhere.

## Win Probability

Column: `win_probability`

Represents the probability associated with the player's/team's expected match win outcome.

Dataset range:
- Approximately 0.47 to 1.00

Values can be interpreted as probabilities.

For example:

`0.83 = 83%`

The field should not automatically be interpreted as a player's individual probability of winning a duel.

## Match Outcome

Column: `match_outcome`

Possible values:

- Win
- Loss

This represents the recorded match result.

## MVP Award

Column: `mvp_award`

Possible values:

- Yes
- No

An MVP award indicates that the player received the MVP designation for that record/match.

## Derived Metrics

Several useful metrics can be calculated from the raw columns.

### K/D Ratio

`kills / deaths`

Higher values indicate better elimination efficiency.

### Kill + Assist Contribution

`kills + assists`

Represents direct and assisted offensive contribution.

### Kill-to-Total-Combat Ratio

A simple derived ratio can be calculated as:

`kills / (kills + deaths)`

This provides an approximate measure of elimination efficiency relative to combat eliminations and deaths.

It is not an official game statistic.

## Comparing Players

When comparing players, use multiple metrics rather than relying on one metric.

Recommended comparison order:

1. Performance Score
2. Kills
3. Deaths
4. Assists
5. Accuracy
6. Reaction Time
7. Fatigue Index
8. Win Probability
9. Match Outcome
10. MVP Award

The player's role, map, and match type should also be considered.

## Aggregation

When analyzing a player across multiple records, averages can be used for:

- Kills
- Assists
- Deaths
- Accuracy
- Reaction Time
- Fatigue Index
- Performance Score
- Win Probability

Counts or percentages can be used for:

- Wins
- Losses
- MVP awards

For example:

`Average Performance Score = mean(performance_score)`

`Win Rate = wins / total matches`

`MVP Rate = MVP awards / total matches`

## Missing Values

The raw dataset contains missing values in several columns.

Known missing-value counts include:

- team_name: 28
- player_role: 28
- map_played: 28
- match_type: 28
- accuracy_percent: 140
- reaction_time_ms: 140
- fatigue_index: 112
- performance_score: 84
- win_probability: 84
- match_outcome: 28
- mvp_award: 56

Numeric metrics should not be treated as zero simply because they are missing.

Missing values mean that the measurement is unavailable.

## Important RAG Rule

The assistant should clearly distinguish between:

1. Raw metrics present in the dataset
2. Metrics calculated from raw data
3. Metrics that do not exist in the dataset

Never fabricate unavailable statistics.