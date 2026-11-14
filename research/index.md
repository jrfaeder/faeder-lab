---
title: Research
nav:
  order: 1
  tooltip: Research areas and publications
---

# {% include icon.html icon="fa-solid fa-microscope" %}Research

Cells make decisions using networks of interacting proteins, genes, and small molecules.
Even a single receptor can give rise to thousands of distinct molecular complexes, which is why conventional reaction-network models break down.
**Rule-based modeling**, an approach our lab helped pioneer, describes these systems compactly as rules for how molecules and their sites interact.
We develop the theory, algorithms, and software for building, simulating, and calibrating such models, and apply them with experimental collaborators to questions in immunology, virology, and cell biology.

{% include section.html %}

## Research areas

### Rule-based modeling and simulation methods
We develop [BioNetGen](https://bionetgen.org) (see our open textbook, [*Rule-Based Modeling of Biological Systems*](https://ruleworld.github.io/bionetgen-book/)) and related tools for specifying, simulating, and analyzing rule-based models, including network-free simulation (NFsim), hybrid particle/population methods, and spatial simulation through MCell4.
Current work focuses on fast, exact stochastic simulation of very large models, such as whole-cell and multicellular systems.

### Parameter estimation and uncertainty quantification
Detailed models have many unknown parameters.
We develop and benchmark Bayesian and optimization methods, from parallel tempering to sequential Monte Carlo and particle filtering, to fit models to experimental data and to quantify what the data can and cannot tell us.

### Immune signaling and cytokine networks
With immunology collaborators, we model T cell receptor signaling and T cell fate decisions, and JAK-STAT signaling downstream of cytokines such as IL-6, IL-10, IL-27, and type I interferons.
We link these mechanistic models to omics data and machine learning to predict how gene expression responds to signaling perturbations.

### Viral replication dynamics
We have built a detailed kinetic model of the replication cycle of Eastern equine encephalitis virus, an alphavirus, in host cells.
Ongoing work extends it to stochastic dynamics, data-driven calibration, and the antiviral interferon response.

### Receptor trafficking and signal transduction
We model how receptor trafficking, co-receptors, and processive enzyme activity shape signaling, including Ras activation by SOS and growth factor receptor trafficking in endothelial cells.

### Stochastic dynamics and rare events
Many important cellular events are rare on simulation timescales.
We adapt rare-event sampling methods, such as weighted ensemble, to biochemical models, and study how noise shapes collective behavior in cell populations.

### Gene expression
In collaboration with the Subramaniam lab at Fred Hutch, we are developing detailed rule-based models of transcription and translation.

{% include section.html %}

## Highlighted publications

{% include list.html data="citations" component="citation" style="rich" filter="group == 'highlighted'" %}

{% include section.html %}

## All publications

Generated automatically from [ORCID](https://orcid.org/0000-0001-8127-609X).

{% include search-box.html %}

{% include search-info.html %}

{% include list.html data="citations" component="citation" style="rich" %}
