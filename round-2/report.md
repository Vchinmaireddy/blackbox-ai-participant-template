# round-2 — Investigate
**Team:** BB-017  
**Queries used:** 76 / 100

## What we concluded

We found that the system's output is highly sensitive to some input changes, while several other changes produced only small score variations. In particular, changing `years_registered` in our recent investigation produced a small increase in the score (+0.0012), suggesting a possible positive effect, but not enough evidence to classify it as a strong relationship.

We also observed that the score generally remains high for many tested combinations, while certain combinations can cause noticeable drops toward the DECLINE region.

## How we got there

We investigated the system by submitting repeated queries and comparing the resulting scores and decisions. We focused on changing individual input fields and observing how the output changed relative to the previous query.

Across 76 queries, we compared the score changes and used the observed score/decision transitions to identify features that may influence the result.

Our strongest current observation is associated with `years_registered`, although the observed change is relatively small and requires further controlled testing.



## What we ruled out

We ruled out the assumption that every input change has a large effect on the final score.

We also did not treat a single successful query or a small score increase as sufficient evidence for a strong causal relationship. We avoided concluding that a feature is important solely because it appears in a high-scoring query.

## What we are still unsure about

We are still unsure about the exact strength and direction of several individual feature effects.

In particular, we need more controlled one-variable-at-a-time experiments to determine whether `years_registered` consistently increases the score and whether other features have stronger effects.

We are also still investigating which combinations of features are responsible for the larger score drops and transitions between APPROVE and DECLINE.
