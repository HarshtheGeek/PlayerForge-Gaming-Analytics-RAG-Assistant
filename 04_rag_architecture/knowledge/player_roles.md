# Player Roles

## Overview

The PlayerForge dataset contains five player roles:

1. Entry Fragger
2. Support
3. IGL
4. Sniper
5. Flex

Role should always be considered when interpreting player performance.

A high number of kills may be expected from an Entry Fragger or Sniper, while Support and IGL performance may also be reflected through assists and broader team contribution.

## Entry Fragger

An Entry Fragger is an aggressive offensive role focused on initiating engagements and creating opportunities for the team.

Relevant dataset metrics:

- Kills
- Deaths
- Accuracy
- Reaction Time
- Performance Score
- Assists

When evaluating Entry Fraggers, prioritize offensive output and combat efficiency.

Useful derived metric:

`K/D Ratio = kills / deaths`

High kills with relatively controlled deaths generally indicate effective performance.

High kills with high deaths may indicate an aggressive but high-risk playstyle.

The dataset does not contain explicit entry-fragging statistics such as first kills or entry success rate.

## Support

Support players generally contribute to team success through coordinated play and assisted eliminations.

Relevant metrics:

- Assists
- Deaths
- Performance Score
- Accuracy
- Kills
- Win Probability

High assists can be especially meaningful when evaluating Support players.

A Support player should not be judged solely by kills.

## IGL

IGL stands for In-Game Leader.

An IGL is associated with leadership and strategic decision-making.

The dataset does not contain direct leadership metrics.

Available metrics for evaluating IGL records include:

- Performance Score
- Win Probability
- Match Outcome
- Assists
- Kills
- Deaths
- Accuracy

The assistant must not claim that an IGL has strong or weak leadership based solely on these metrics.

For example, a high win rate may indicate successful match outcomes, but it does not directly measure the quality of strategic calls.

## Sniper

Snipers generally specialize in precision-based engagements.

Relevant dataset metrics:

- Accuracy
- Kills
- Deaths
- Reaction Time
- Performance Score

Accuracy and reaction time can be especially useful when analyzing Sniper performance.

A Sniper with high accuracy and high kills may demonstrate strong precision and offensive impact.

However, the dataset does not contain:

- Headshot percentage
- Long-range kills
- One-shot kills
- Sniper-specific accuracy

Therefore, these metrics should not be invented.

## Flex

Flex players can adapt between different responsibilities depending on team requirements.

Relevant metrics:

- Kills
- Assists
- Deaths
- Accuracy
- Performance Score
- Win Probability

Because Flex players have broader responsibilities, performance should be evaluated using multiple metrics rather than a single specialized statistic.

## Role Comparison

The dataset contains approximately:

- Entry Fragger: 581 records
- IGL: 561 records
- Sniper: 556 records
- Flex: 548 records
- Support: 526 records

Role comparisons should use normalized or aggregated statistics where appropriate.

## Role-Aware Evaluation

The same statistical profile can mean different things for different roles.

Example:

A high death count may be more understandable for an Entry Fragger because the role involves aggressive engagements.

A Support player with high assists and moderate kills may still provide excellent team contribution.

An IGL's performance cannot be fully evaluated using kills because strategic leadership metrics are not present.

A Sniper's accuracy and reaction time may be particularly informative.

A Flex player's balanced kills and assists may indicate adaptability, although adaptability itself is not directly measured.

## Important RAG Rule

Do not infer undocumented role-specific abilities.

The dataset does not directly measure:

- Leadership quality
- Entry success
- Utility usage
- Objective control
- Clutch ability
- Communication quality
- Tactical decision quality
- Map-specific role execution

Use only the available data and clearly identify when an interpretation is an inference.