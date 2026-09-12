# A Computational Study of the Basal Ganglia Loops in Incremental Decision Making

<p align="center">
  <strong>A biologically inspired computational model of incremental learning, decision making, and basal ganglia pathway interactions</strong>
</p>

---

## Overview

This repository contains the computational implementation accompanying the PhD dissertation:

> **A Computational Study of the Basal Ganglia Loops in Incremental Decision Making**

The project develops a biologically inspired computational framework for investigating how information acquired incrementally over time can be integrated to support visual category learning and decision making.

The model is centered on the interaction of the three principal basal ganglia pathways:

- **Direct pathway** — D1 striatal pathway
- **Indirect pathway** — D2 striatal pathway
- **Hyperdirect pathway** — STN pathway

These pathways interact through the basal ganglia-thalamo-cortical circuitry and contribute to action selection, competition between alternatives, and the emergence of a categorical decision.

---

## Research Motivation

Many decision-making tasks require an agent to make a decision before all available information has been observed.

Instead of receiving the complete stimulus at once, information can be acquired sequentially through successive samples.

This raises a fundamental computational question:

> **How does the brain integrate partial information over time and determine when enough evidence has been accumulated to commit to a decision?**

This project investigates this question using a computational model of cortico-basal ganglia-thalamo-cortical interactions.

---

## Model Architecture

The model integrates several neural populations and pathways involved in sensory processing, learning, action selection, and dopaminergic modulation.

### Main populations

| Population | Description |
|---|---|
| IT | Inferior temporal cortex; sensory feature representation |
| MTL | Memory-related representation of previously sampled information |
| StrD1 | D1-type striatal neurons |
| StrD2 | D2-type striatal neurons |
| STN | Subthalamic nucleus |
| GPe | External globus pallidus |
| GPi | Internal globus pallidus |
| Thal | Thalamic output |
| PM | Premotor cortex; behavioral decision output |
| SNc | Dopaminergic modulation and reward prediction |
| PPN | Reward-related input |

The architecture contains both fixed and plastic connections. Synaptic plasticity is modulated by activity-dependent traces and dopamine-related signals.

---

## Incremental Decision Making

A central characteristic of the model is that visual information is acquired incrementally.

Each stimulus exemplar is represented by four visual features:

- **DF** — dorsal fin
- **TF** — tail fin
- **VF** — ventral fin
- **MA** — mouth area

Rather than presenting the complete feature vector simultaneously, the model processes individual features sequentially.

In the current implementation, feature sampling is determined by a randomized sampling process.

The information retained in the IT/MTL representations allows activity associated with previously sampled features to persist and interact with newly acquired information.

This provides a computational mechanism for integrating information across successive sampling events.

---

## Basal Ganglia Pathways

### Direct pathway

The direct pathway is implemented through D1-type striatal neurons.

It contributes to the facilitation of selected actions through inhibitory projections toward the GPi.

### Indirect pathway

The indirect pathway is implemented through D2-type striatal neurons and the GPe.

Its activity contributes to the suppression of competing action representations.

### Hyperdirect pathway

The hyperdirect pathway connects cortical sensory representations to the STN and subsequently to the GPi.

This pathway provides a rapid excitatory influence on the GPi and can therefore contribute to the suppression or delay of premature responses.

### Pathway interaction

The main computational interest of the model is not the isolated function of these pathways, but their **dynamic interaction during incremental learning and decision formation**.

---

## Learning Mechanisms

Learning is implemented through dopamine-modulated synaptic plasticity across multiple connections in the network.

The model includes plastic projections involving:

- IT → MTL
- IT → StrD1
- IT → StrD2
- MTL → StrD1
- MTL → StrD2
- IT → STN
- StrD1 → GPi
- StrD2 → GPe
- STN → GPi
- StrD1 → SNc

Activity-dependent traces provide a temporal mechanism for associating neural activity with subsequent dopaminergic modulation.

The SNc population additionally implements a reward-prediction mechanism based on network activity and reward-related input.

---

## Decision Mechanism

The model produces a behavioral response through the PM population.

A decision is made when the strongest PM response exceeds the response threshold and sufficiently dominates the competing response.

Conceptually:

```text
Maximum PM activity ≥ response threshold
AND
Winner–competitor activity difference ≥ margin threshold
        ↓
Categorical decision
