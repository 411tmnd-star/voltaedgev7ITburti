# VoltaEdge — Project Overview

## Purpose

VoltaEdge is an **IoT electricity intelligence layer**: an electricity-understanding system that turns measurements into an understandable explanation of energy use and its cost in Nigerian naira. The prototype's core experience is a chain from readings to a visual naira explanation, with the user asking: **“What ate my ₦20,000?”**

The primary measure of success is whether an insight leads to an action—not whether a dashboard merely displays data.

## Product boundary

VoltaEdge is not:
- a replacement for the utility meter;
- a certified electrical protection device;
- merely a dashboard.

It is a prototype for measuring, normalizing, interpreting, visualizing, explaining, alerting, and helping a user act on electricity-use information. Do not imply certification, safety-rated isolation, utility-grade accuracy, or completed physical validation without separate evidence.

## Core loop

`MEASURE → NORMALIZE → UNDERSTAND → VISUALIZE → EXPLAIN → ALERT → ACT → MEASURE AGAIN`

The loop should connect observed readings to a comprehensible explanation and then to a user action that can be evaluated by subsequent measurements.

## Example explanation

For a bill/energy example of ₦20,000 over 105 kWh:

- Implied average cost: ₦20,000 ÷ 105 kWh = approximately **₦190.48/kWh**.
- This is an illustrative calculation, not a claim about a current tariff or a measured household.

## Appliance attribution

Non-intrusive load monitoring (NILM) output is an **estimate**. When confidence is low, show uncertainty and request user confirmation instead of presenting the appliance identity as fact.

## Anomaly concept

The remembered anomaly rule is `mean + 3σ`. The population/window, baseline-update policy, minimum sample count, and handling of non-stationary loads must follow the canonical implementation/specification; they are not defined by this summary alone.

## Project context

The prototype was associated with SIWES / AI Hive. The system's value proposition is to make electricity use understandable in a way that supports a practical decision.
