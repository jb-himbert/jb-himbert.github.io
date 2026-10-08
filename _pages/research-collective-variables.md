---
title: "Learning slow collective variables for molecular dynamics"
permalink: /research/collective-variables/
author_profile: true
excerpt: "Machine-learning and spectral methods for slow collective variables and enhanced sampling."
---

<p class="project-context">PhD · École des Ponts / Inria MATHERIALS · 2025–present<br>Advisors: Tony Lelièvre and Gabriel Stoltz</p>

## Problem

Molecular simulations describe systems with many degrees of freedom, but their behaviour over long times often depends on a small number of slow processes. Metastability makes these processes difficult to observe: a trajectory can spend a long time within one state before making a rare transition to another.

One way to handle metastability is to bias the dynamics, in order to promote those transitions, but finding a physically relevant and statistically tractable bias is difficult. To solve the issue, we can reduce the problem and look for collective variables, which provide a low-dimensional description of the system. The challenge is therefore to find collective variables that retain the information needed to describe those transitions.

<figure class="project-figure">
  <img src="{{ '/images/research_phd/slow-dynamics.svg' | relative_url }}" alt="Two metastable states separated by an energy barrier, with rare transitions along a slow collective variable.">
  <figcaption>Conceptual illustration of metastability and a slow collective variable; this is a schematic, not a result from my research.</figcaption>
</figure>

## Approach

My PhD explores data-driven methods to learn ideal collective variables from simulation data. In practice, we try to define ideal characteristics of CV by analyzing dynamics theoretically, and derive this intuition into scalable algorithms for CV discovery, usable in enhanced sampling frameworks.

## Current work

I am currently studying CV discovery algorithms using spectral methods that capture slow transitions between metastable sets.

{% if site.data.profile.show_manuscript_status %}
**Reparametrization of Slow Modes for Collective Variable Discovery — manuscript in preparation.**
{% endif %}

## Collaborators

This project is part of my PhD research, and is joint work with Loucas Pillaud-Vivien, Tony Lelièvre and Gabriel Stoltz.

<!-- ## Links

- [CERMICS](https://cermics-lab.enpc.fr/)
- [Inria MATHERIALS](https://team.inria.fr/matherials/)
- [École des Ponts](https://ecoledesponts.fr/en) -->

[← All research projects]({{ '/research/' | relative_url }})
