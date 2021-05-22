---
layout: archive
title: "Open reviews"
permalink: /reviews/2021-05-22-leemasson
author_profile: true
---

{% include base_path %}

### May 22, 2021 &mdash; Open review of preprint by Lee Masson and Isik: [`PubPeer`](https://pubpeer.com/publications/4F8269B5FADD9BE14441D96A4CD4A6#1)
Lee Masson, H. & Isik, L. (2021). Functional selectivity for naturalistic social interaction perception in the human superior temporal sulcus. *bioRxiv*. [`DOI`](https://doi.org/10.1101/2021.03.26.437258)

---
Lee Masson and Isik use a forward encoding analysis with two public movie-watching fMRI datasets to isolate cortical representations of social-affective content. Their findings reveal that superior temporal cortex encodes social interaction while controlling for a variety of other variables in a naturalistic context. This paper tackles an interesting question with very sophisticated (and clearly-described) methods for model estimation and comparison. I particularly like how the authors frame "preference mapping" and "variance partitioning" in the context of evaluating forward encoding models. My primary comment is that I think a more quantitative description of the model features—particularly the social-affective annotations—would make readers more confident in interpreting model performance. I outline a few other interpretational concerns, as well as some minor comments and typos.

### Major comments:

I think readers would benefit from a more quantitative description of the stimulus features used here—in particular the hand-annotated social-affective model features. The authors describe the model features thoroughly in the text (pages 5–8), but I still felt unsure. For example, how correlated are these features? It could be useful to visualize a feature-by-feature correlation matrix for the social-affective model features as well as the low-dimensional (non-DNN) perceptual features. Another example: is the presence of "faces" really a perceptual feature more so than a social-affective feature, and how closely related is it to the "social interaction" feature? I'm also curious about the "actual" dimensionality of these correlated features? For example, how many PCs account for 99% of the variance in the social-affective representation of the stimulus. It could also be helpful to know about the relative frequency of occurrence of the binary features (like how often does "speaking" occur and how often does "social interaction" occur?). With large differences in the frequency of occurrence it's hard to disentangle whether a particular feature doesn't account for much variance in a general way, or just doesn't account for much variance in this particular stimulus where it occurs very infrequently. Maybe a table, or additional panels in Figure 1 would be helpful to better quantify or visualize the features/annotations.

I'm somewhat concerned that model performance attributed to social-affective features like social interaction could be confounded with the linguistic or semantic content of speech in the movie. The cortical areas with high performance for the social-affective and social interaction models include superior temporal cortex, TPJ, and IFG (Figures 6C, 6D, 7A, 7B)—but these are areas where we might also expect good performance for semantic models during language comprehension (e.g. [Huth et al., 2016](https://doi.org/10.1038/nature17637); [de Heer et al., 2017](https://doi.org/10.1523/JNEUROSCI.3267-16.2017)). As far as I understand, the only auditory features included in the current model are the audio amplitude, pitch, a binary variable indicating the presence of music, and a binary variable indicating whether or not a person is speaking. These relatively simple features probably don't really capture any of the semantic content of language present in the movies. I'm not suggesting the authors rerun everything with an additional language model, and the authors note that this language confound is "difficult to rule out" (line 503), but I think this potential limitation in interpretation is deserving of a bit more discussion.

I really like the description of "preference mapping" and "variance partitioning"—but I think the authors could be a little more clear about the interpretational distinction between these two approaches. What complementary insights do these two approaches provide?

The authors should be cautious about how they use the word "generalize" (e.g. lines 35, 473). The authors fit separate models within each subject and each dataset, summarize results across subjects, and demonstrate that the results are qualitatively consistent across the two datasets (i.e. the cortical maps of model performance look visually similar). This sort of consistency across datasets is good, but it's a relatively weak form of generalization; for example, a strong test of generalization would be to fit the encoding model on one dataset and demonstrate that the fitted model has good prediction performance on the other dataset (also generalization across subjects due to the non-overlapping samples)—but the authors are not doing this (cf. [Yarkoni & Westfall, 2017](https://doi.org/10.1177%2F1745691617693393)).

Despite the same smoothing kernel being used in the two different preprocessing pipelines, the Sherlock dataset looks considerably smoother than the Summer dataset (presumably because it started with greater "intrinsic" smoothness). I don't really think this is an issue for the current results, but rather than simply applying the same smoothing kernel to both datasets, I would consider using an adaptive smoothing algorithm to match the ultimate smoothness of the two datasets (e.g. AFNI's [3dBlurToFWHM](https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dBlurToFWHM.html)).

This manuscript is interesting in that the encoding strategy combines both high-dimensional models intended to capture the stimulus in a geometric vector space (e.g. the DNN) and human-annotated binary variables simply indicating the presence or absence of some complex stimulus feature such a "social interaction." But it's worth noting that a one-dimensional indicator of "social interaction" does not really capture the "content" of social interaction; i.e. these annotations are not really "models" in the same way that a DNN can serve as model of vision, and have no "geometry" of the kind in DNNs (or among semantic word embeddings). These one-dimensional indicator variables are more similar to the regressors used in a traditional event-related GLM than the rich feature spaces used in some high-profile forward encoding analyses.

### Minor comments:

The term "prediction accuracy" was a bit confusing at first because "accuracy" has a particular meaning in related machine learning analyses, but this is really just a correlation value (between predicted and actual test time series). Maybe something like "prediction performance" would have a bit less baggage?

As far as I understand, no noise ceiling normalization is performed here. The authors should make this explicit in the Methods section.

Line 66: "stronger and reliable" > "stronger and more reliable"

Line 249: reword this "Procedurally…" sentence

Line 301: "feature" > "features"

Line 301: "nest" > "next"

Line 388: "Fig 6" > "Fig 5"?

### References:

de Heer, W. A., Huth, A. G., Griffiths, T. L., Gallant, J. L., & Theunissen, F. E. (2017). The hierarchical cortical organization of human speech processing. *Journal of Neuroscience*, *37*(27), 6539-6557. [`DOI`](https://doi.org/10.1523/JNEUROSCI.3267-16.2017)

Huth, A. G., De Heer, W. A., Griffiths, T. L., Theunissen, F. E., & Gallant, J. L. (2016). Natural speech reveals the semantic maps that tile human cerebral cortex. *Nature*, *532*(7600), 453-458. [`DOI`](https://doi.org/10.1038/nature17637)

Yarkoni, T., & Westfall, J. (2017). Choosing prediction over explanation in psychology: Lessons from machine learning. *Perspectives on Psychological Science*, *12*(6), 1100-1122. [`DOI`](https://doi.org/10.1177%2F1745691617693393)

