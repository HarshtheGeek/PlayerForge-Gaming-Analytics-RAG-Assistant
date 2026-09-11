# Player Engagement

## Overview

Engagement describes a player's involvement and effectiveness in combat interactions.

The PlayerForge dataset does not contain a direct `engagement_score`.

Engagement should instead be inferred using:

- Kills
- Assists
- Deaths
- Accuracy
- Reaction Time
- Performance Score
- Player Role

## Combat Activity

Kills and deaths are the strongest available indicators of combat activity.

A player with high kills and high deaths is likely involved in frequent or aggressive engagements.

A player with low kills and low deaths may have a more passive or support-oriented engagement profile.

Therefore:

`High engagement ≠ automatically good performance`

Engagement quality must be evaluated together with efficiency.

## Kill + Death Profile

The combination of kills and deaths can provide useful engagement classifications.

### High Kills / Low Deaths

Indicates:

- High offensive impact
- Strong combat efficiency
- Strong survivability

This is generally a desirable engagement profile.

### High Kills / High Deaths

Indicates:

- Aggressive engagement style
- High combat involvement
- Potentially high risk

This profile can be particularly relevant for Entry Fraggers.

### Low Kills / Low Deaths

Indicates:

- Lower direct combat involvement
- Potentially passive or support-oriented play
- Requires assists and role context for proper interpretation

### Low Kills / High Deaths

Indicates:

- Low combat efficiency
- High risk without equivalent offensive output
- Potentially poor match performance

## Assists and Team Engagement

Assists provide evidence of team-oriented engagement.

High assists with moderate kills may indicate that a player frequently participates in team eliminations without securing the final kill.

This is particularly relevant when evaluating Support, Flex, and IGL players.

## Accuracy and Engagement Quality

Accuracy can help distinguish between simply participating in many engagements and performing effectively within those engagements.

For example:

- High engagement + high accuracy → effective combat involvement
- High engagement + low accuracy → frequent but potentially inefficient engagements

## Reaction Time

Lower reaction time generally indicates faster responses during engagements.

Reaction time should be interpreted together with kills, deaths, and accuracy.

## Derived Engagement Metrics

The following metrics can be calculated from the dataset when needed:

### K/D Ratio

`kills / deaths`

Measures elimination efficiency.

### Kill + Assist Contribution

`kills + assists`

Measures direct and assisted offensive contribution.

### Kill Participation Proxy

Because the dataset does not contain team-level total kills, an exact kill participation percentage cannot be calculated directly.

A simple contribution measure can instead use:

`kills + assists`

This should be described as a contribution metric rather than an official kill participation percentage.

## Important RAG Rule

Do not claim that the dataset contains:

- Engagement count
- Duels won
- First engagements
- Damage per engagement
- Entry attempts
- Clutch engagements

unless those metrics are explicitly calculated from additional data.