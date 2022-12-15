# A-B-Testing-Mobile-Games
As players progress through the levels of the game, they will occasionally encounter gates that force them to wait a non-trivial amount of time or make an in-app purchase to progress. In addition to driving in-app purchases, these gates serve the important purpose of giving players an enforced break from playing the game, hopefully resulting in that the player's enjoyment of the game being increased and prolonged. This dataset includes A/B test results of Cookie Cats to examine what happens when the first gate in the game was moved from level 30 to level 40. When a player installed the game, he or she was randomly assigned to either gate30 or gate40.

## Goal/Objective
A/B test results of Cookie Cats to examine what happens when the first gate in the game was moved from level 30 to level 40. When a player installed the game, he or she was randomly assigned to either gate30 or gate40.

## General Problem
As players progress through the levels of the game, they will occasionally encounter gates that force them to wait a non-trivial amount of time or make an in-app purchase to progress. In addition to driving in-app purchases, these gates serve the important purpose of giving players an enforced break from playing the game, hopefully resulting in that the player's enjoyment of the game being increased and prolonged.

## Root Cause Analysis
- Does treatment (moved from gate30 to gate40) result in increased and prolonged enjoyment of the player in playing?
- Does treatment (moved from gate30 to gate40) increase in-app purchases?

## Problem Statement
Should the proposed gate at Level 40 be implemented over the existing gate at Level 30 based on day 1 and 7 player retention rates.

## Proposed Solution
There are two primary EDA that we can perform, the first EDA with the number of game rounds played and the second EDA with the 1 and 7 day retention rates.
A/B Testing using bootstrap analysis and proportional z-tests was done on Day 1 and 7 Retention rates, and bootstrap analysis and Mann-Whitney U test on gamerounds played.

## Key Metrics
retention rates

## Population
- 90189 user
- Sample : 759  user ~ 1000 user

## Business Hypothesis
The business question relates specifically to changing the gates based on the day 1 and 7 retention rates. We can also perform an A/B test on sum_gamerounds to check if there is a statistically significant difference in the number of gamerounds played based on assigned group.
Therefore, A/B tests on three separate targets: retention_1, retention_7, and sum_gamerounds
A confidence interval of 95% will be taken for all tests.

## Hypothesis
- H0 = The proportions are the same
- H1 = The proportions are different

## Experiment Groups and Period
- Sample 1000 Users random
- Control	:  user who gate30
- Treatment	:  user who moved from gate30 to gate40/ gate40
- Period : Day 1 and 7 Retention rates

## Experiment Monitoring
Dataset
Duplicated data
Missing data
dataset balance
EDA
Game Round Played
Univariate
Bivariate
the 1 and 7 Day Retention Rate
Univariate
Bivariate
A/B Testing
Day 1 and 7 Retention rates
bootstrap analysis
proportional z-tests
Gamerounds played
bootstrap analysis
Mann-Whitney U test


## Analysis

### Descriptive Analyst
#### Observations on rounds played
All values are with respect to the week after installation.
There are no obvious links between gamerounds played and the group the player was assigned to.
The number of players decreases as levels increase. The exception is that a number of players installed the game and did not complete any levels (installed and did not play).
- 3,994 (~4.4%) players did not play the game
- ~27.4% of players played five or less rounds
- 50% of players played 16 or less rounds
- 75% of players played less than 50 rounds

#### Retention Rate Observations\n
Considering the entire sample, the 1 and 7 Day Retention Rate are 0.445 and 0.186 respectively.
Graphically, there is not much to see. The values for Day 1 and Day 7 retention rates are slightly higher for the control group, gate_30, with a 1 and 7 Day retention rate of 0.448 and 0.190 respectively, compared with the the treatment group, gate_40, rates of 0.442 and 0.182. The control groups retention rates are greater than the retention rates for the entire sample.
AB tests will be performed to see if these values are statistically significant or not.
Looking at the combined 1 and 7 Day Retention Rates, it looks like slightly more players assigned to the control group, gate_30, played the game both on Day 1 and with 7 Days (True-True), and more players assigned to the treatment group, gate_40, played neither on Day 1 or Day 7 (False-False)

## Inferential analyst\n
In this an analysis, an exploratory data analysis was performed on the gamerounds completed by each user and the Day 1 and 7 Retention rates. The data was clean with the exception of a single disproportionate outlier that was corrected for. A/B Testing using bootstrap analysis and proportional z-tests was done on Day 1 and 7 Retention rates, and bootstrap analysis and Mann-Whitney U test on gamerounds played.
Based on the results of the z-test, there is strong evidence that Day 7 retention rates are higher when the gate is at Level 30. Therefore, the gate should not be moved. The bootstrap analysis suggests that the Level 30 gate is better for Day 1 Retention. Further investigation is required.
Looking at the cumulative number of games played per person, there where no statistically significant results.

## Action Plan
With churn happening at relatively low number of rounds played, there is an opportunity to increase retention. Fact finding (exit surveys) and incentives could lead to higher retention rates. More research is required. Rounds played could be examined further, for example to see if there is any impact on in-app micro transactions.
