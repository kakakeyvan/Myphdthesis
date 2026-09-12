



# A Computational Study of the Basal Ganglia Loops in Incremental Decision Making

## A biologically inspired computational model of incremental learning and decision making

<p align="center">
  <strong>Computational Neuroscience · Basal Ganglia · Reinforcement Learning · Incremental Decision Making</strong>
</p>

---

Overview

This repository contains the computational implementation accompanying the PhD dissertation:

“A Computational Study of the Basal Ganglia Loops in Incremental Decision Making”  
Keyvan Yahya (2025), Dr. rer. nat.

The project investigates how partial and sequentially acquired visual information can be integrated over time to support category learning and decision making through interactions within cortico–basal ganglia–thalamo–cortical circuits.

The model emphasizes the dynamic interplay among the three principal basal ganglia pathways:

- Direct pathway (D1)  
- Indirect pathway (D2)  
- Hyperdirect pathway (STN)

---

Research Question

Many real-world decisions must be made before all relevant information is available.

> How can partial and sequentially acquired information be integrated over time to support a categorical decision?

The model provides a biologically inspired framework using:

- Basal ganglia circuits  
- Reinforcement-based learning  
- Incremental visual information processing  

---

Model Architecture

The model consists of interconnected neural populations representing sensory processing, memory, basal ganglia circuits, thalamic output, motor response, and dopaminergic modulation.

Main Neural Populations

| Population | Function |
|-----------|----------|
| IT | Sensory feature representation |
| MTL | Memory of previously sampled features |
| StrD1 | Direct pathway (D1-type striatum) |
| StrD2 | Indirect pathway (D2-type striatum) |
| STN | Hyperdirect pathway |
| GPe | Indirect pathway relay |
| GPi | Basal ganglia output |
| Thal | Thalamic relay |
| PM | Behavioral decision output |
| SNc | Dopaminergic modulation & reward prediction |
| PPN | Reward-related input |

The network includes both fixed and plastic synaptic connections. Learning is modulated by activity-dependent traces and dopamine-related signals.

---

Incremental Visual Categorization

The model performs a visual categorization task using schematic fish exemplars.

Each exemplar is defined by four feature dimensions:

- Dorsal Fin (DF)  
- Tail Fin (TF)  
- Ventral Fin (VF)  
- Mouth Area (MA)

Information is acquired incrementally, allowing previously sampled features to leave persistent activity traces that interact with newly acquired information.

---

Basal Ganglia Pathways

Direct Pathway (D1)
Facilitates selected actions via StrD1 → GPi projections.

Indirect Pathway (D2)
Suppresses competing actions via StrD2 → GPe → GPi interactions.

Hyperdirect Pathway (STN)
Provides rapid excitatory input to GPi, helping suppress premature responses.

Central Idea
The model focuses on how direct, indirect, and hyperdirect pathways jointly shape:

- Competition  
- Decision timing  
- Action selection  

---

Learning Mechanisms

Dopamine-modulated plasticity is implemented across multiple connections:

- IT → MTL  
- IT → StrD1 / StrD2  
- MTL → StrD1 / StrD2  
- IT → STN  
- StrD1 → GPi  
- StrD2 → GPe  
- STN → GPi  
- StrD1 → SNc  

Activity-dependent traces allow temporal association between neural activity and subsequent dopaminergic signals.

The SNc population implements reward prediction dynamics based on network activity and reward-related input.

---

## Decision Mechanism

A categorical decision is generated through the PM population when two criteria are satisfied:

1. **Response strength:** Maximum PM activity exceeds the response threshold.
2. **Response confidence:** The difference between the winning and competing responses exceeds the margin threshold.

```text
Maximum PM activity ≥ response threshold
AND
Winner–competitor difference ≥ margin threshold
```

This ensures that decisions are both **strong** and **confident**.

---

Computational Framework

The model is implemented in Python using the ANNarchy neural simulation framework.

Main implementation notebook:

`
incrementaldecisionmaking_model.ipynb
`

The notebook includes:

- Model construction  
- Neural populations  
- Synaptic connections  
- Learning mechanisms  
- Experimental procedures  
- Analysis routines  

---

Repository

Repository: kakakeyvan/Myphdthesis

This repository provides the computational implementation associated with the dissertation and supports:

- Inspection  
- Reproduction  
- Further development  

---

Citation

If you use this code or model in academic work, please cite:

`bibtex
@phdthesis{yahya2025incremental,
  author = {Yahya, Keyvan},
  title  = {A Computational Study of the Basal Ganglia Loops in Incremental Decision Making},
  year   = {2025},
  type   = {PhD Dissertation}
}
`

---

Status

Research code accompanying a PhD dissertation.  
The repository is under active development as the computational model and analyses are further organized and documented.

---

<p align="center">
  <strong>Computational Neuroscience · Basal Ganglia · Reinforcement Learning · Incremental Decision Making</strong>
</p>

---
