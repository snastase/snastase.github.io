---
layout: archive
title: "Open reviews"
permalink: /reviews/2021-11-23-chowdhury
author_profile: true
---

{% include base_path %}


### November 23, 2021 &mdash; Open review of preprint by Chowdhury and colleagues: [`PubPeer`](https://pubpeer.com/publications/17194DD37E24090F12E75310103A6E#1)
Chowdhury, P. R., Wadhwa, A., & Tyagi, N. (2021). Brain inspired face recognition: a computational framework. *arXiv*. [`link`](https://arxiv.org/abs/2105.07237)

---

Chowdhury and colleagues draw on the neuroscience literature to synthesize several brain-inspired feature detectors into a face recognition algorithm (brain-inspired face recognition; BIFR). In general, I like the goal of this paper: distilling neuroscientific findings into simple computational motifs and constructing a functional model based on these motifs. However, lack of clarity in the writing makes it difficult to evaluate their model; for example, it’s not very clear how the neuroscientific results motivate certain feature detectors, and it’s difficult to tell how the model is evaluated across datasets. The writing needs a good bit of work. I provide some high-level comments below.

### Major comments:

Although I very much appreciate the approach of looking at the neuroscience literature and trying to distill what computation or algorithm each face area supports, I’m not convinced that the experimental findings cited provide very strong constraints. For example, in the case of lateral fusiform gyrus (or FFA), the authors want a representation that is size-/position-invariant but not viewpoint-/lighting-invariant—but the passing reference to Kanwisher papers doesn’t make a very strong argument. Are BOLD response magnitudes in FFA similar across experimental manipulations of size and position, but decreased or different across viewpoints and lighting conditions? What are the actual experiments or results that lead the authors to interpret FFA in this way? If the authors want to make a strong claim that fMRI results can tell us what computations are taking place, I think we’ll need a bit more in-depth discussion of which experimental results guide our interpretation of the computation. One nice example that comes to mind (not cited here) is work by Freiwald and Tsao ([2010](https://doi.org/10.1126/science.1194908)) demonstrating that early macaque face patches (ML/MF) have viewpoint-specific responses, while anterior face patch AL has partially viewpoint-specific mirror-invariant responses, and the anterior face patch AM has fully viewpoint-invariant responses.

It wasn’t very clear to me how exactly the model is being tested (especially if the reader is not familiar with these datasets), making it difficult to interpret the performance. For example, are we talking about face identity classification or identifying whether or not a face is present in an image? Initially, I assumed the former, but the first paragraph of the Introduction suggests otherwise (see next comment). On the other hand, I thought some of these datasets only contain faces, in which case you must be classifying identity? In Table 1, you list the number test samples for each dataset, but it’s not clear what these datasets actually contain, or what the classification problem is (e.g. binary face vs. nonface? multi-class face identity as in Figure 7?). I understand that many of the recognition rates are very high (e.g. 95%+), but it’s difficult to interpret this without better understanding what classification problem is being solved (e.g. what’s the chance level?).

In the first Introduction paragraph, I’m not sure I follow the two “stages” of superordinate and subordinate category recognition, and how this is relevant to the current work (or the “human thinking process”). Is this intended to create a distinction between (a) categorizing faces relative to other superordinate object categories vs (b) categorizing face images of particular individuals? When you say that in the current study you focus on “global categorization,” does this mean categorizing faces relative to other objects? Or classify whether an image contains a face or not? From the use of the term “face recognition” early in the manuscript, I initially thought the paper was about face identity classification, but this paragraph makes it unclear. Then when I get to the “Recognition results” section, it seems to be about identity classification. This should be made abundantly clear at the outset.

With a multi-component model like this, I wonder: do the authors have a sense of how much each component contributes to performance? For example, is it possible that just the HOG module is driving most of the performance? Would it be possible to reevaluate performance after lesioning each subcomponent to assess how much each subcomponent contributes to performance?

The comparison to deep learning models is not very compelling until we better understand how performance is being evaluated here. The authors include ResNet, VGG, and Xception for comparison on two datasets. Are these datasets rich enough to really challenge the models? Are these models actually trained for face recognition or just general object recognition? They also do not include some of the iconic or state-of-the-art face recognition models; e.g. DeepFace ([Taigman et al., 2014](https://openaccess.thecvf.com/content_cvpr_2014/html/Taigman_DeepFace_Closing_the_2014_CVPR_paper.html)), FaceNet ([Schroff et al., 2015](https://www.cv-foundation.org/openaccess/content_cvpr_2015/html/Schroff_FaceNet_A_Unified_2015_CVPR_paper.html)), ArcFace ([Deng et al., 2019](https://openaccess.thecvf.com/content_CVPR_2019/html/Deng_ArcFace_Additive_Angular_Margin_Loss_for_Deep_Face_Recognition_CVPR_2019_paper.html)). I don’t think the authors strictly need to compare all these models; but if they want to argue that their model performs face recognition on par with deep learning models, including a model like ArcFace would strengthen their claim.

The introductory sections on “Representation and the need for dimensionality reduction,” “Classification models,” and “Engineering basis of biological process” seem to contain a bit too much exposition for the current work. It feels a bit like a laundry list or chronology of prior studies, and it’s hard to track the relevance of each item to the current work. I would try to condense this introductory material into a couple shorter and more focused paragraphs.

In the “Related work” section, I’m not sure I see the motivation for this distinction between “represesentation” and “classification.” Is the goal here to highlight that your model uses particular brain-inspired representations?

### Minor comments:

Abstract: “clubbed” > “combined” or “synthesized”

Figure 1: I’m not sure this comparison of optimizers needs to be included in the main text; might be better as a supplementary figure.

Figure 9: I would cap the y-axis at 100%.

### References:

Deng, J., Guo, J., Xue, N., & Zafeiriou, S. (2019). ArcFace: additive angular margin loss for deep face recognition. In *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition* (pp. 4690–4699). [`link`](https://openaccess.thecvf.com/content_CVPR_2019/html/Deng_ArcFace_Additive_Angular_Margin_Loss_for_Deep_Face_Recognition_CVPR_2019_paper.html)

Freiwald, W. A., & Tsao, D. Y. (2010). Functional compartmentalization and viewpoint generalization within the macaque face-processing system. *Science*, *330*(6005), 845–851. [`DOI`](https://doi.org/10.1126/science.1194908)

Schroff, F., Kalenichenko, D., & Philbin, J. (2015). FaceNet: a unified embedding for face recognition and clustering. In *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition* (pp. 815–823). [`link`](https://www.cv-foundation.org/openaccess/content_cvpr_2015/html/Schroff_FaceNet_A_Unified_2015_CVPR_paper.html)

Taigman, Y., Yang, M., Ranzato, M. A., & Wolf, L. (2014). DeepFace: closing the gap to human-level performance in face verification. In *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition* (pp. 1701–1708). [`link`](https://openaccess.thecvf.com/content_cvpr_2014/html/Taigman_DeepFace_Closing_the_2014_CVPR_paper.html)

