---
layout: archive
title: "Open code"
permalink: /code/
author_profile: true
redirect_from:
  - /software
---

{% include base_path %}

I contribute software to several open source projects, particularly the [BrainIAK](https://brainiak.org/) Python package for fMRI analysis. You can find code repositories associated with my research projects on my GitHub profile: [`GitHub`](https://github.com/snastase)

---

## Predicting brain activity from word embeddings during natural language comprehension [`GitHub`](https://github.com/snastase/encling-tutorial) [`Colab`](https://colab.research.google.com/drive/1L565z54Oth7oNIbzZDt1pLG-l4iOmRaD?usp=sharing)

This tutorial introduces a typical **enc**oding framework for mapping **ling**uistic embeddings onto human brain activity during natural language comprehension. The tutorial includes worked examples for both fMRI and ECoG datasets collected while subjects listened to naturalistic spoken narratives. Two types of word embeddings are obtained based on the stimulus transcripts: static word embeddings from word2vec and contextual word embeddings from GPT-2. Encoding models are estimated using banded ridge regression—this allows us to predict brain activity from word embeddings for left-out segments of data. The tutorial can be retrieved from [GitHub](https://github.com/snastase/encling-tutorial) or run interactively on [Colab](https://colab.research.google.com/drive/1L565z54Oth7oNIbzZDt1pLG-l4iOmRaD?usp=sharing).

---

## BrainIAK: The Brain Imaging Analysis Kit [`website`](https://brainiak.org/) [`GitHub`](https://github.com/brainiak/brainiak)

The Brain Imaging Analysis Kit (BrainIAK) is a free and open source Python package for computationally-optimized advanced fMRI analysis. BrainIAK supports a variety of methods including intersubject correlation (ISC) and intersubject functional connectivity (ISFC), the shared response model (SRM), full correlation matrix analysis (FCMA), Bayesian representational similarity analysis (BRSA), event segmentation using hidden Markov models, topographic factor analysis (TFA), inverted encoding models (IEM), fMRI data simulation (fmrisim), and real-time fMRI neurofeedback.

Kumar, M., Anderson, M. J., Antony, J. W., Baldassano, C., Brooks, P. P., Cai, M. B., Chen, P.-H. C., Ellis, C. T., Henselman-Petrusek, G., Huberdeau, D., Hutchinson, J. B., Li, P. Y., Lu, Q., Manning, J. R., Mennen, A. C., **Nastase, S. A.**, Richard, H., Schapiro, A. C., Schuck, N. W., Shvartsman, M., Sundaraman, N., Suo, D., Turek, J. S., Turner, D. M., Vo, V. A., Wallace, G., Wang, Y., Williams, J. A., Zhang, H., Zhu, X., Capota, M., Cohen, J. D., Hasson, U., Li, K., Ramadge, P. J., Turk-Browne, N. B., Willke, T. L., & Norman, K. A. (2021). BrainIAK: The Brain Imaging Analysis Kit. *Aperture Neuro*, *1*(4). [`DOI`](http://doi.org/10.52294/31bb5b68-2184-411b-8c00-a1dacb61e1da) [`PDF`](https://snastase.github.io/files/Kumar_Aperture_2021.pdf) [`GitHub`](https://github.com/brainiak/brainiak-aperture)

---

## Princeton Handbook for Reproducible Neuroimaging [`DOI`](http://doi.org/10.5281/zenodo.3688789) [`Handbook`](https://brainhack-princeton.github.io/handbook/)

The goal of this handbook is to provide a reference for best practices in reproducible fMRI research. There’s no single “right” answer for many questions in fMRI, but here we try to provide helpful references and recommendations. Many elements of the handbook are specific to the Princeton Neuroscience Institute computing infrastructure, but the principles are widely applicable. This document will be updated over time as best practices evolve.

Brooks, P. P., McDevitt, E. A., Mennen, A. C., Testerman, M., Kim, N. Y., Visconti di Oleggio Castello, M., & Nastase, S. A. (2020). Princeton Handbook for Reproducible Neuroimaging. 
 [`DOI`](http://doi.org/10.5281/zenodo.3688789)

---

## Intersubject correlation tutorial  [`DOI`](https://doi.org/10.5281/zenodo.3693161) [`GitHub`](https://github.com/snastase/isc-tutorial)

This tutorial introduces intersubject correlation (ISC) analysis and corresponding statistical tests using a Jupyter Notebook. The analysis are implemented in Python using the Brain Imaging Analysis Kit ([BrainIAK](http://brainiak.org/)). To run the analyses interactively in the cloud using Google Colab, click here: [Tutorial in Google Colab](https://colab.research.google.com/drive/1EHI9buw-nvj5UDNg7MWUiQ1ITVJSswtH). This tutorial accompanies a "tools of the trade" article published in *Social Cognitive and Affective Neuroscience*:

Nastase, S. A., Gazzola, V., Hasson, U., & Keysers, C. (2019). Measuring shared responses across subjects using intersubject correlation. *Social Cognitive and Affective Neuroscience*, *14*(6), 667–685. [`DOI`](https://doi.org/10.1093/scan/nsz037) [`PDF`](https://snastase.github.io/files/Nastase_SCAN_2019.pdf)


