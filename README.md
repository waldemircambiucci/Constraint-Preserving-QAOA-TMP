# Train Marshalling Problem (TMP) with QAOA and Constraint-Preserving Mixers in Ket-LANG

This repository explores the **Train Marshalling Problem (TMP)** as a high-impact railway logistics challenge and investigates its potential for **hybrid quantum optimization**, with emphasis on **Variational Quantum Algorithms (VQAs)** and **Constraint-Preserving QAOA**.

The central idea is to position TMP not only as a classical combinatorial optimization problem, but as a structurally rich logistics problem whose constraints and operational rules make it a strong candidate for **domain-structured quantum optimization**. In this context, we introduce a **TMP-specific constrained QAOA** centered on a **Railway-Constrained Mixer (RCM)**, designed to preserve feasibility during the variational search.

Beyond railway yards, this work also highlights the broader relevance of **VQA-based optimization** for **port-related and intermodal logistics**, where rail, yard, and port operations are increasingly coupled.

---

## Motivation

Train marshalling remains a critical bottleneck in railway and intermodal logistics. Yard operations directly affect:

- train composition and departure readiness,
- classification-track usage,
- shunting and re-handling effort,
- synchronization with port, terminal, and hinterland flows,
- operational efficiency across rail-connected logistics corridors.

Because TMP is strongly constrained and combinatorial in nature, it provides a useful testbed for studying how **quantum optimization methods** can be adapted to realistic logistics settings.

---

## Strategic relevance of TMP for logistics

This repository frames TMP as a strategically important logistics problem because:

- railway yards remain central to **freight reorganization and network fluidity**;
- marshalling inefficiencies propagate into **rail-port and intermodal chains**;
- TMP combines **allocation, sequencing, and feasibility constraints**, making it representative of many real logistics optimization problems;
- improvements in TMP modeling can inform broader optimization challenges in **rail yards, terminals, and port logistics**.

---

## Problem and opportunity for quantum optimization

Classical methods remain essential for operational TMP solving, but realistic variants quickly become challenging due to the combination of:

- discrete assignment decisions,
- ordering and sequencing dependencies,
- capacity constraints,
- operational feasibility rules,
- combinatorial growth of the search space.

This makes TMP an interesting candidate for **hybrid quantum-classical optimization**, especially under the lens of:

- **QUBO-based modeling**,
- **Ising/cost-Hamiltonian mappings**,
- **QAOA and other VQAs**,
- **problem-structured mixers** that better respect operational feasibility.

A key observation of this work is that a naive one-hot QUBO encoding can become qubit-expensive very quickly. Even small examples already show that direct encodings are conceptually valid, but not yet hardware-friendly. This motivates the search for **compressed formulations**, **constraint-preserving mixers**, and **domain-aware ansätze**.

---

## Core contribution

The main research direction explored here is the introduction of a **TMP-specific constrained QAOA**, centered on a **Railway-Constrained Mixer (RCM)**.

### Railway-Constrained Mixer (RCM)

The RCM is intended to move beyond the standard unconstrained QAOA mixer by embedding railway feasibility logic into the variational evolution. Instead of allowing arbitrary bit-flip exploration, the mixer is designed to preserve valid or near-valid TMP states during optimization.

Conceptually, this means:

- respecting assignment structure,
- reducing exploration of infeasible marshaling states,
- lowering dependence on heavy penalty terms,
- improving alignment between the quantum search process and railway-yard operations.

This is a natural evolution from baseline penalty-based QUBO/QAOA formulations toward **constraint-preserving quantum optimization for logistics**.

---

## Technical scope

This repository includes exploratory implementations and simulations around:

- **TMP formulated as QUBO**
- **QAOA-based optimization in Ket-LANG**
- **Constraint-preserving mixer experiments**
- **Ket-based local simulation workflows**
- **Didactic toy examples for small wagon instances**
- **Comparisons between standard and constrained mixers**

The code is intended as a research prototype and methodological exploration, not yet as a production-grade railway optimization solver.

---

## Repository agenda

This work is organized around the following agenda.

### 1. Strategic relevance of TMP for logistics
Why train marshalling is still a critical bottleneck for railway and intermodal logistics.

### 2. Problem and opportunity for quantum optimization
Limits of current optimization approaches and why TMP is a strong candidate for hybrid quantum methods.

### 3. Core contribution of the paper
Introduction of a TMP-specific constrained QAOA, centered on the **Railway-Constrained Mixer (RCM)**.

This includes a high-level view of:

- the **QUBO model**,
- the use of **Ket language**,
- the **Ket-based simulation strategy**,
- and the expected advantages of structured quantum optimization for TMP.

### 4. Conclusions and next steps
Implications for:

- rail-yard operations,
- port-rail logistics,
- and future developments in **domain-structured quantum optimization**.

---

## Notebooks in this repository

### [`TMP as QUBO with Constrained-Mixer.ipynb`](./TMP%20as%20QUBO%20with%20Constrained-Mixer.ipynb)
Explores TMP modeling as a QUBO while introducing the logic of a constrained mixer tailored to railway feasibility.

### [`TMP as QUBO as QAOA in KET.ipynb`](./TMP%20as%20QUBO%20as%20QAOA%20in%20KET.ipynb)
Presents a baseline QAOA implementation of TMP in **Ket-LANG**, using a direct QUBO-to-QAOA workflow.

### [`KET-LANG - QAOA Demo v1.ipynb`](./KET-LANG%20-%20QAOA%20Demo%20v1.ipynb)
Provides a simpler demonstration notebook for QAOA concepts and Ket-based local simulation.

### [`KET-LANG - QAOA Mixer Constraint - Demo v1.ipynb`](./KET-LANG%20-%20QAOA%20Mixer%20Constraint%20-%20Demo%20v1.ipynb)
Focuses on mixer behavior and experiments related to **constraint-preserving QAOA** in Ket-LANG.

---

## Why Ket-LANG

This repository uses **Ket-LANG** as the implementation environment for local simulation because it offers a flexible way to prototype:

- Hamiltonian-based formulations,
- QAOA-style variational circuits,
- custom mixer logic,
- and small-scale simulation workflows for research and experimentation.

Ket-LANG is used here as a practical environment to test ideas around **TMP-QUBO-QAOA pipelines** and structured mixer design.

For more information about Ket-LANG, visit the official project page: [QuantumKet](https://quantumket.org/).

---

## Main research message

This repository supports three main messages:

1. **TMP is a high-impact railway logistics problem** with strong relevance for rail-yard efficiency and intermodal logistics.
2. **Constraint-preserving QAOA**, through a **Railway-Constrained Mixer (RCM)**, is a promising direction for making quantum optimization more aligned with railway operational structure.
3. The broader lesson extends beyond rail: **VQA and domain-structured quantum optimization** may become relevant for **port-related logistics**, especially in tightly coupled rail-port systems.

---

## Current status

This is an exploratory research repository containing:

- conceptual formulations,
- toy instances,
- simulation notebooks,
- and early methodological prototypes.

The current implementations should be interpreted as **proof-of-concept studies** aimed at understanding how TMP can be connected to quantum optimization workflows, especially under **constraint-preserving variational strategies**.

---

## Future work

Planned next steps include:

- extending TMP models to more realistic yard-operation settings,
- refining the **Railway-Constrained Mixer (RCM)**,
- investigating more compact encodings,
- exploring larger wagon sets and richer constraints,
- comparing standard vs constrained QAOA more systematically,
- and connecting the methodology to **port-rail and intermodal logistics use cases**.

Longer term, this line of work aims to contribute to **domain-structured quantum optimization** for complex logistics systems.

---

## Suggested citation

If you use or reference this repository, please cite the associated paper, preprint, or project description when available.

---

## Author

**Waldemir Cambiucci**  
Founder, HYPAQ Technologies  
Research focus: AI-First Quantum-Ready architectures, quantum optimization, VQAs, and logistics-oriented deep-tech innovation.

---

## Disclaimer

This repository is intended for **research, education, and experimentation**. The notebooks and simulations are exploratory and should not be interpreted as validated operational solvers for real-world railway deployment without further methodological and empirical development.
