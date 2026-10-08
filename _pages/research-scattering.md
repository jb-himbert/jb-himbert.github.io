---
title: "Scattering transforms for physical systems"
permalink: /research/scattering/
author_profile: true
excerpt: "Diffusion-based sample generation with scattering-spectra models for Lagrangian turbulence trajectories."
---

<p class="project-context">Research internship · ENS Ulm, Center of Data Science · April–September 2024<br>Supervisor: Stéphane Mallat</p>

## Problem

Turbulent fluid mechanics in 3D is known to have a multiscale structure. Kolmogorov formulated it in 1941, and described a schematic where the kinetic energy of the fluid is continuously passed down across scales. This phenomenon is both a curse and a blessing for generative modelling of such flows: where traditional PDE solvers need a very fine resolution to properly model such interactions, [Li et al](https://arxiv.org/abs/2507.19103) showed that a diffusion model could accurately reproduce high order statistics, leveraging the multiscale prior of Unet backbones.

However, the diffusion model was large and complex, and trained on millions of costly turbulence trajectories. One can ask itself if it is possible to reproduce such results with the most minimal model: indeed, the correct set of statistics could spark new advances in machine learning architectures and parametrization.

## Approach

I used a framework developped by Rudy Morel called scattering-spectra model, which is a principled way to compute multiscale features using cascaded wavelet transforms. In particular, the scale decomposition enables the covariance matrix of those features to be sparse, leading to a rich yet robust set of statistics. 

I modified the framework to include score-matching for generating new samples, then applied it to Lagrangian turbulence trajectories. The aim was to connect a structured statistical description of the data with a sample-generation procedure.

<figure class="project-figure">
  <a href="{{ '/images/research_ens/scale_dependencies.png' | relative_url }}">
    <img src="{{ '/images/research_ens/scale_dependencies.png' | relative_url }}" alt="Two signals above their wavelet amplitude and phase representations at different scales." loading="lazy">
  </a>
  <figcaption>Example signals and their wavelet representations, illustrating intermittency episodes propagate across scales. Left: sample from the Lagrangian trajectory dataset. Right: Generated Hawkes process. Open the image to inspect the detail.</figcaption>
</figure>

## Main results

The approahc lead to very interesting results: while the baseline fails to account extreme tails in the distribution, our tailored reparametrization using log-normal statistics managed to match statistics up to high orders, while having only 500-1000 parameters, compared to the 50 millions of the diffusion model.

<figure class="project-figure">
  <a href="{{ '/images/research_ens/rapport2_pdf.png' | relative_url }}">
    <img src="{{ '/images/research_ens/rapport2_pdf.png' | relative_url }}" alt="Velocity-increment distributions comparing data in blue and generated trajectories in red, for four models and time lags 1, 10, 50 and 100." loading="lazy">
  </a>
  <figcaption>Reference data (blue) and generated trajectories (red) statistics at different time lags (scales). Open the figure at full resolution to read the model labels and axes.</figcaption>
</figure>

## My contribution

I implemented all parts of the project: modifying the existing scattering-spectra framework to incorporate diffusion, generating samples, and applying and evaluating the models on Lagrangian turbulence trajectories. The work was supervised by Stéphane Mallat and built on Rudy Morel's framework.

## Links

- [Scattering Spectra](https://arxiv.org/abs/2204.10177)

[← All research projects]({{ '/research/' | relative_url }})
