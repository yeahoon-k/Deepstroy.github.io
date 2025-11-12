---
layout: page
title: "Non-Stationary Structural Causal Bandits — Explanation"
permalink: /ns-scb-explainer/
---

## TL;DR
We model a non-stationary bandit problem as a time-indexed **Structural Causal Model (SCM)** whose variables and information flow can change over time. This makes it possible to (i) **separate what changes** (transition edges, noise, or reward distribution) from what stays stable, and (ii) choose **interventions (arms)** that remain near-optimal even when the environment shifts.

## What problem do we solve?
Classical SCM-based bandits assume a stationary environment: once you know the diagram and the reward mechanism, you keep exploiting it. Real systems (healthcare, platforms, operations) **shift over time**—policies that were optimal yesterday degrade today. We address **how to act efficiently when the causal structure and/or reward distribution evolve**, leveraging a temporal SCM to reason about **which variables to intervene on and when**.

## Key ideas
1. **NS-SCM-MAB formulation.** We represent each time slice by an SCM \(\mathcal{M}_t\) and make explicit the **transition edges** that carry information across time. Non-stationarity is defined as a **reward distribution shift** and/or a change in the temporal information flow.
2. **Temporal model view.** Instead of treating all history as flat context, we reason in a **time-expanded causal diagram** that clarifies which past variables actually transmit useful information to the current reward.
3. **POMIS+ intervention sequences.** We extend the idea of “Possibly-Optimal Manipulative Sets” to time, constructing **intervention sequences** that remain (near-)optimal across slices by targeting variables whose effects persist through the temporal graph.
4. **Efficiency by structure.** By exploiting graph structure (parents, mediators, confounders, transition edges), we reduce exploration on irrelevant levers and **avoid chasing spurious non-stationarity**.

## What do we show?
- A formalization of **Non-Stationary SCM-MAB** and precise conditions under which stationary solutions fail.
- An algorithmic recipe (POMIS+) for building **intervention sequences** that adapt to temporal information flow.
- Experiments demonstrating **lower regret** and **higher optimal-action probability** than stationary or naive baselines when the environment shifts.

## Paper/resources
- Paper PDF: (link)
- Code: [(link)](https://github.com/yeahoon-k/NS-SCMMAB)
- Poster/Slides: (optional link)

