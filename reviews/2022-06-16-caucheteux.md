---
layout: archive
title: "Open reviews"
permalink: /reviews/2022-06-16-caucheteux
author_profile: true
---

{% include base_path %}


### June 16, 2022 &mdash; Open review of preprint by Caucheteux and colleagues:
Caucheteux, C., Gramfort, A., & King, J. R. (2021). Long-range and hierarchical language predictions in brains and algorithms. *arXiv*. [`link`](https://arxiv.org/abs/2111.14232)

---

Caucheteux and colleagues use word embeddings from a large language model (GPT-2) with fMRI acquired during natural language comprehension to demonstrate that the brain predictively encodes meaning several words into the future. The results indicate that encoding performance peaks when ~8 future words are incorporated into the model; the authors support this result with analyses manipulating GPT-2 layer and comparing semantic/syntactic features, as well as several other control analyses. In general, I think the methods are solid and the results are convincing. I think a few methodological details about aggregating/downsampling embeddings should be expanded to convince readers that this forecasting effect is “real” given the low temporal resolution of fMRI. My other comments pertain to clarifying the methods and terminology.

### Major comments:

One of the core claims of the paper is that including embeddings for future words improves model performance, achieving peak performance with ~8 future words. This raises some important questions about how you aggregate/downsample word embeddings into TRs, given that fMRI has a pretty slow sampling rate (1.5 s in this dataset). How many words typically occur within each TR? I imagine that several words occur per TR on average, which suggests that ~8 future words correspond to only one or two future TRs. Following Huth et al., 2016, you sum the embeddings for words occurring within the same TR; is there any particular motivation for summing rather than e.g. averaging embeddings? How do you handle embeddings for words that span a TR boundary? In any case, I imagine the summed vectors are highly similar across forecast windows; i.e. sliding the forecast window by one word will change the summed embedding very little (especially for words where the GPT-2 embedding may change very little from the previous word). Do you think this accounts for the relatively small effect size for the forecast scores (e.g. Fig. 2D)? In general, I think a more detailed treatment of these questions would go a long way in convincing readers that your forecasting result is a “real” effect.

The authors account for varying hemodynamic lag by duplicating the GPT-2 embeddings at six lags (line 329) and fit the regression model across all lags. Following on the previous comment, I worry that this might make it even trickier to interpret the relatively small forecasting effects. 
First question: which six lags are you including? I’m assuming you mean lags ranging from 0 to 9 seconds, but this should be explicitly stated. Is it possible, for certain voxels, that the regression model assigns higher weights to earlier lags for farther forecast windows? If I understand correctly, this flexibility in fitting across lags should only reduce the observed effect—is this correct? Would examining the weights assigned to the varying lags clear this up at all? To be clear, I think the forecasting effect, on average, holds up and is still quite clear—but the authors should do whatever they can to convince readers that hemodynamic lag/variability isn’t somehow contributing to the forecasting effect.

Two related questions about model estimation: (1) Do the authors include any confound variables (e.g. word rate, phoneme rate) during model estimation? (2) How do the authors deal with silent periods (i.e. TRs with no words) in the stimuli? For example, do the authors excise the empty TRs? Do they populate these TRs with zero vectors? In our work, we’ve found that these different approaches can have a fairly large effect on encoding performance in early auditory areas; I suspect the simple on/off structure of silent period drives a considerable proportion of encoding performance in early auditory cortex (e.g. Heschl’s gyrus).

I don’t fully understand the “shared response model” used to estimate the noise ceiling described at line 775. First of all, I’m not sure I would use the term “shared response model” here, because this specific term is used to describe a hyperalignment model developed by [Chen et al., 2015](https://proceedings.neurips.cc/paper/2015/file/b3967a0e938dc2a6340e258630febd5a-Paper.pdf) (where each voxel is modeled as a linear combination of other voxels from other subjects with certain orthogonality constraints). As far as I can tell, here the noise ceiling is derived using a weighted-average variant of intersubject correlation (e.g. [Nastase et al., 2019](https://doi.org/10.1093/scan/nsz037)). However, I’m not sure I correctly understand the role of W. You use the same five-fold cross-validation scheme to learn a W that optimally weights each subject’s time series for a given voxel to best predict that voxel’s time series in a left-out subject—is this correct? In this case, each subject’s voxel time series is correlated with a weighted average of other subjects’ voxel time series? Since this is a fairly novel implementation of a noise ceiling, we could use a little more detailed explanation here.

In Fig. 4B, we see negative forecast scores at longer distances to the current word, particularly for the syntactic forecasts. How should we interpret these negative scores? If I understand correctly, this means that the model with no forecasting performs better; is this correct?

At line 79, you mention that you used a fixed forecast window width of seven words. What’s the motivation for using this width?

Can you more explicitly describe the dimensionality of the model? If I understand correctly, the full model for a given (e.g. 8th) layer is 768 GPT-2 features × 6 lags = 4608 parameters. Then, according to the footnote at line 334, you reduce this to 20 dimensions using PCA. Is this correct? Or do you reduce the 768 GPT-2 features to 20 dimensions and then stack the reduced model across 6 lags (120 dimensions total)? In my experience, the “elbow” is not usually very obvious with dimensionality reduction. What proportion of variance in the original 8th layer is explained by the first 20 PCs?

This is largely a terminological quibble: The authors use terms like “depth” and “abstract” to describe later layers of GPT-2 (with reference to [Jawahar et al., 2019](https://doi.org/10.18653/v1/P19-1356)). I’m not sure it’s completely obvious that the later layers of GPT-2 are strictly more abstract. The embeddings accumulate contextual information layer by layer, but I’m not sure how exactly this maps onto abstractness. For example, the final layers of GPT-2 are specialized for next-word prediction and are likely less abstract than late-intermediate layers. The authors may be able to adjust the terminology to accommodate this concern, or they could point to additional references from the NLP literature to support the “abstractness” claim.

It seems like we’re missing some panels (C–E; forecast depth) in Figure S8? Maybe I’m just misunderstanding the figure caption, but it seems to imply more panels.

I would make very clear throughout the manuscript that you’re “enhancing” (e.g. line 10) the encoding models with forecasting, not the language model itself (i.e. you’re not modifying GPT-2 or anything like that).

### Minor comments:

Abstract, line 8: remove “each”—just to make sure readers don’t think that each and every subject listens to the full 70 minutes of stimuli.

Line 72: “long-range forecast” > “long-range forecasting”

Line 119: you might specify early (e.g. here) on that this implementation of GPT-2 has 12 layers 

Line 123: “that” > “than”

Lines 127, 130, etc: “Heschel” > “Heschl”

Line 282: “as voxels simplicity” > “as voxels for simplicity”

### References:

Chen, P.-H. C., Chen, J., Yeshurun, Y., Hasson, U., Haxby, J., & Ramadge, P. J. (2015). A reduced-dimension fMRI shared response model. In C. Cortes, N. Lawrence, D. Lee, M. Sugiyama, & R. Garnett (Eds.), *Advances in Neural Information Processing Systems* (Vol. 28). Curran Associates, Inc. [`link`](https://proceedings.neurips.cc/paper/2015/file/b3967a0e938dc2a6340e258630febd5a-Paper.pdf)

Jawahar, G., Sagot, B., & Seddah, D. (2019). What does BERT learn about the structure of language? In *Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics* (pp. 3651–3657). Association for Computational Linguistics. [`DOI`](https://doi.org/10.18653/v1/P19-1356)

Nastase, S. A., Gazzola, V., Hasson, U., & Keysers, C. (2019). Measuring shared responses across subjects using intersubject correlation. *Social Cognitive and Affective Neuroscience*, *14*(6), 667-685. [`DOI`](https://doi.org/10.1093/scan/nsz037)

