# Attacking Performance

## Overview

Attacking performance describes how effectively a player contributes to offensive actions during an esports match.

In the PlayerForge dataset, attacking performance is primarily represented through:

- Kills
- Assists
- Accuracy
- Performance Score
- Win Probability
- Match Outcome
- Player Role

The dataset does not contain explicit attacking-event columns such as entry success rate, damage dealt, headshot percentage, or objective captures. Therefore, attacking ability should be inferred from the available performance metrics rather than from unavailable statistics.

## Kills

`kills` represents the number of opponents eliminated by a player in a match.

Higher kills generally indicate stronger direct offensive impact.

Dataset range:
- Minimum: 4
- Maximum: 30
- Median: approximately 15

Kills are especially relevant when evaluating Entry Fraggers and Snipers, but kills should not be interpreted independently from deaths, assists, and accuracy.

## Assists

`assists` represents the number of eliminations a player contributed to without necessarily securing the final elimination.

Higher assists can indicate strong team contribution and coordinated offensive play.

Dataset range:
- Minimum: 0
- Maximum: 20
- Median: approximately 8

Assists are particularly relevant when evaluating Support and Flex players.

## Accuracy

`accuracy_percent` represents the percentage of shots that successfully hit their intended target.

Higher accuracy generally indicates better shooting precision.

Dataset range:
- Minimum: approximately 20.46%
- Maximum: approximately 71.79%
- Median: approximately 44.93%

Accuracy should be interpreted together with kills. A player may have high accuracy but relatively low kills, or high kills with lower accuracy because of a more aggressive playstyle.

## Offensive Interpretation

A player can be considered to have strong offensive performance when multiple indicators support the conclusion.

For example:

- High kills + high accuracy = strong direct offensive output
- High kills + high deaths = aggressive but potentially risky playstyle
- Moderate kills + high assists = strong team-oriented contribution
- High kills + low deaths = efficient offensive performance
- High performance score + strong kills = strong overall match contribution

## Entry Fragger Consideration

Entry Fraggers are expected to have strong offensive involvement.

When evaluating an Entry Fragger, prioritize:

1. Kills
2. Deaths
3. Accuracy
4. Assists
5. Performance Score

However, the dataset does not contain an explicit entry-success metric. Do not claim that a player has a high entry success rate unless such a metric is calculated separately.

## Important RAG Rule

Do not invent offensive metrics that do not exist in the dataset.

For example, the following cannot be directly answered from the CSV unless calculated from available data:

- Damage per round
- Headshot percentage
- Entry success rate
- First kill percentage
- Objective success rate
- Clutch percentage