# A Computational Study of the Basal Ganglia Loops in Incremental Decision Making

**A biologically inspired computational model of incremental learning and decision making**

---
<p align="center">
  <strong>A biologically inspired computational model of incremental learning and decision making</strong>
</p>---

Overview

This repository contains the computational implementation accompanying the PhD dissertation:

«A Computational Study of the Basal Ganglia Loops in Incremental Decision Making»

The project investigates how visual information acquired incrementally over time can be integrated to support category learning and decision making through interactions within cortico-basal ganglia-thalamo-cortical circuits.

The model focuses on the dynamic interaction of the three principal basal ganglia pathways:

- Direct pathway — D1 striatal pathway
- Indirect pathway — D2 striatal pathway
- Hyperdirect pathway — STN pathway

Rather than considering these pathways independently, the model investigates how their interaction contributes to competition between alternative actions and the emergence of a categorical decision.

---

Research Question

Many decisions must be made before all relevant information has been observed.

This project therefore addresses the following computational question:

«How can partial and sequentially acquired information be integrated over time to support a categorical decision?»

The model provides a biologically inspired framework for studying this question using basal ganglia circuits, reinforcement-based learning, and incremental visual information processing.

---

Model

The model consists of interconnected neural populations representing sensory processing, memory, basal ganglia circuits, thalamic output, motor response, and dopaminergic modulation.

Main Neural Populations

Population| Function
IT| Sensory feature representation
MTL| Representation of previously sampled information
StrD1| D1-type striatal population
StrD2| D2-type striatal population
STN| Hyperdirect pathway
GPe| Indirect pathway
GPi| Basal ganglia output
Thal| Thalamic relay
PM| Behavioral decision output
SNc| Dopaminergic modulation and reward prediction
PPN| Reward-related input

The network contains both fixed and plastic synaptic connections. Learning is modulated by activity-dependent traces and dopamine-related signals.

---

Incremental Visual Categorization

The model performs a visual categorization task using schematic fish exemplars.

Each exemplar is defined by four feature dimensions:

- DF — Dorsal Fin
- TF — Tail Fin
- VF — Ventral Fin
- MA — Mouth Area

Information is acquired incrementally rather than presenting the complete stimulus representation simultaneously.

In the current implementation, feature sampling follows a randomized sampling process. Activity associated with previously sampled features can persist and interact with subsequently acquired information, allowing the model to integrate information across successive sampling events.

---

Basal Ganglia Pathways

Direct Pathway

The D1 striatal pathway projects toward the GPi and contributes to the facilitation of selected actions.

Indirect Pathway

The D2 striatal pathway interacts with the GPe and contributes to the suppression of competing action representations.

Hyperdirect Pathway

The IT → STN → GPi pathway provides a rapid excitatory influence on the GPi and can contribute to suppressing or delaying premature responses.

Central Idea

The primary computational focus is the interaction among the direct, indirect, and hyperdirect pathways during incremental learning and decision formation.

---

Learning

The model incorporates dopamine-modulated synaptic plasticity across multiple connections, including:

IT → MTL
IT → StrD1
IT → StrD2
MTL → StrD1
MTL → StrD2
IT → STN
StrD1 → GPi
StrD2 → GPe
STN → GPi
StrD1 → SNc

Activity-dependent traces provide a temporal mechanism for associating neural activity with subsequent dopaminergic modulation.

The SNc population additionally implements reward-prediction dynamics based on network activity and reward-related input.

---

## Decision Mechanism

The final behavioral response is generated through the PM population.

A categorical decision is made when the strongest PM response exceeds the response threshold and sufficiently dominates the competing response.

Conceptually:
Conceptually:

```text
Maximum PM activity ≥ response threshold
AND
Winner–competitor activity difference ≥ margin threshold
        ↓
Categorical decision
```

Computational Framework

The model is implemented in Python using the ANNarchy neural simulation framework.

The main implementation is provided in:

incremental_decision_making_model.ipynb

The notebook contains the model construction, neural populations, synaptic connections, learning mechanisms, experimental procedures, and analysis routines.

---

Repository

Repository: "kakakeyvan/Myphdthesis"

The repository is intended to provide the computational implementation associated with the dissertation and to facilitate inspection, reproduction, and further development of the model.

---

Dissertation

Keyvan Yahya (2025)

A Computational Study of the Basal Ganglia Loops in Incremental Decision Making

PhD Dissertation, Dr. rer. nat.

---

Citation

If you use this code or model in academic work, please cite the associated dissertation:

@phdthesis{yahya2025incremental,
  author = {Yahya, Keyvan},
  title  = {A Computational Study of the Basal Ganglia Loops in Incremental Decision Making},
  year   = {2025},
  type   = {PhD Dissertation}
}

---

Status

Research code accompanying a PhD dissertation.

The repository is under active development as the computational model and associated analyses are further organized and documented.

---

<p align="center">
  <strong>Computational Neuroscience · Basal Ganglia · Reinforcement Learning · Incremental Decision Making</strong>
</p>
