---
title: "Foveated multiscale tokenization for vision transformers"
permalink: /research/foveated-tokenization/
author_profile: true
excerpt: "Comparing tokenization schemes for astrophysical data and developing efficient foveated tokens using the discrete wavelet transform."
---

<p class="project-context">Research internship · Flatiron Institute, Center for Computational Mathematics · June–August 2024<br>Supervisors: François Lanusse, Alberto Bietti and Stéphane Mallat</p>

## Problem

Astrophysical observations contain information at several spatial scales. These inputs can be viewed as images, but they also represent sensor measurements with physical structure. Local detail and the wider spatial context both matter when choosing a representation.

Vision transformers process these inputs through tokens. The goal of this project was to compare different tokenization schemes for astrophysical data and explore how a multiscale construction could make the structure of the observations available to a model: indeed, an efficient and principled tokenizer could prove key for the emergence of foundation models for physics.

## Approach

We developed a tokenizer based on foveation: representing local detail together with information from a wider region at coarser resolutions. This connects a spatial location with its surrounding context through a multiscale representation.

The construction can be computed efficiently using the discrete wavelet transform (DWT). Wavelet coefficients provide access to different spatial resolutions, allowing foveated tokens to be assembled from the decomposition rather than treating every scale independently.

<figure class="project-figure">
  <a href="{{ '/images/research_flatiron/multiscale_tokenization.png' | relative_url }}">
    <img src="{{ '/images/research_flatiron/multiscale_tokenization.png' | relative_url }}" alt="An astronomical image transformed by a discrete wavelet transform into multiscale patches, with fovea extraction and reconstruction by an inverse wavelet transform." loading="lazy">
  </a>
  <figcaption>Wavelet-based multiscale tokenization and fovea extraction. DWT and IDWT denote the discrete wavelet transform and its inverse.</figcaption>
</figure>

## Project outcome

I implemented and compared different tokenization schemes for astrophysical data, including the foveated tokenizer. The central construction is illustrated above: an image is decomposed into wavelet coefficients, which support both multiscale patch extraction and the construction of a fovea.

The tokenizer works well and managed impressive compression, in particular compared to baseline ViT patches and a naive multiscale approach, but suffered from the conditional learning of the fovea centers, making it difficult to scale across datasets. Neverless, this work contributed to Polymathic AI's research on representations for scientific data and generative modelling.

## My contribution

I implemented all parts of the project, including the tokenization schemes, the DWT-based foveated construction, and the comparisons on astrophysical data. I worked with François Lanusse, Alberto Bietti and Stéphane Mallat at the Flatiron Institute's Center for Computational Mathematics.

## Links

- [Polymathic AI](https://polymathic-ai.org/)
- [Flatiron Institute — Center for Computational Mathematics](https://www.simonsfoundation.org/flatiron/center-for-computational-mathematics/)
- [Fovea description](https://en.wikipedia.org/wiki/Fovea_centralis)

[← All research projects]({{ '/research/' | relative_url }})
