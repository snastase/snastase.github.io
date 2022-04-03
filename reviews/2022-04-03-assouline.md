---
layout: archive
title: "Open reviews"
permalink: /reviews/2022-04-03-assouline
author_profile: true
---

{% include base_path %}


### April 3, 2022 &mdash; Open review of preprint by Assouline and Mendelsohn:
Assouline, A., & Mendelsohn, A. (2019). Weaving a story: narrative formation over prolonged time scales engages social cognition and fronto-parietal networks. *bioRxiv*. [`link`](https://doi.org/10.1101/667618)

---

Assouline and Mendelsohn presented participants with clips comprising two versions of an audiovisual narrative: one played in the correct order, allowing participants to follow the temporal/causal structure of events; the other played in reverse order, disrupting the causal relations among events. The authors use a functional connectivity analysis to identify brain regions with different connectivity for the two stimulus conditions, then perform an exploratory seed-based connectivity analysis (during both the clips and the inter-scene blank periods). Readers need a more detailed description of the methodology to understand and interpret the results. I also have some questions / suggestions about particular analytic choices. Note that my review is based on an updated version of the manuscript sent by the journal that appears to be newer than the bioRxiv preprint.

### Major comments:

I didn’t fully understand the combination of functional connectivity, PCA, and MVPA in the initial analysis stage for identifying brain areas that differ between the two stimulus conditions. As far as I understand, you first compute voxelwise functional connectivity separately for the two groups. This will result in a n\_voxels x n\_voxels functional connectivity matrix. Then you run PCA on this matrix, retain the first three PCs, resulting in a n\_voxels x 3 matrix (is this correct?). Why only three? Was this choice based on variance accounted for, or some precedent in the field? I assume these three PCs will roughly correspond to whole-brain networks (e.g. DMN), thus these reduced-dimension matrices capture each voxel’s participation in three major networks. Then you supply these reduced-dimension connectivity matrices to some MVPA-like algorithm… but how? First of all, how do you reformat the `n\_voxels x 3` matrix for MVPA, do you just flatten the matrix into a single 3 * n\_voxels vector? I don’t see any mention of typical MVPA-style classification algorithms (e.g. correlation-based classifier, logistic regression, SVM)... If I understand correctly you’re passing the reduced-dimension connectivity matrices into a group-level ANOVA? I don’t really understand how this mimics classical MVPA… for example, there’s no cross-validation in play here. What is the structure of this “second-level general linear model (GLM)” and how does it qualify as MVPA? What is the “MVPA effect” you refer to later, a group-level omnibus F-statistic reflecting any connectivity values that predict the group assignment? We need a good bit more detailed description of the methodology here to understand and interpret the results.

That said, the regions with a significant connectivity-based MVPA effect—calcarine sulcus and cerebellum—are not really among the regions I would expect to see in a narrative manipulation. Do the authors have any explanation for why these particular regions might show up beyond what’s already in the text? If we were to lower the significance threshold a bit, would other areas show up?

I also wonder whether using intersubject functional connectivity (ISFC) rather than the traditional within-subject functional connectivity (WSFC) used here would better reveal stimulus-driven differences in network configuration. Simony and colleagues ([2016](https://doi.org/10.1038/ncomms12141); Figures 2 and 3) pretty convincingly demonstrate that ISFC better captures changes in connectivity related to the structure of a narrative stimulus; WSFC is dominated by intrinsic fluctuations (and motion) that largely obscure stimulus-driven effects. I’m not demanding that the authors perform ISFC analysis, but I suspect it could strengthen their results.

If I understand the structure of the experiment, I would expect to see big stimulus onset/offset response transients throughout the brain when each clip begins and ends. I’m curious whether the authors control for this or omit these onsets/offsets when computing connectivity (e.g. in the context of naturalistic stimuli, we’ve recommended omitting the first ~10 seconds to avoid the wholesale stimulus-on brain response; [Nastase et al., 2019](https://doi.org/10.1093/scan/nsz037)). These onset/offset transients could drive uninteresting connectivity, and omitting them may allow the connectivity estimate to better capture more subtle stimulus/task differences.

The authors also measure functional connectivity during the inter-scene blank periods. I’m curious how this analysis was performed. The inter-scene blank periods are only 10 seconds long, comprising only 5 TRs; we can’t get a very reliable correlation estimate from only 5 values. I assume the authors are somehow splicing out and concatenating these inter-scene blank periods prior to computing functional connectivity—is this correct? Related to the previous comment, do you account for the hemodynamic lag or the onset/offset transients?

The area revealed by the seed-based functional connectivity map for the calcarine seed seems awfully close to the seed itself (Figure 2B, top). Are we sure that this area is not spatially overlapping with the seed itself? I worry that with 8 mm smoothing, this “functionally connected” area is effectively bleeding over from the seed itself.

I’m not very familiar with using pupil dilation as a measure of attentional engagement. I understand that pupil dilation will largely track the dynamic luminance of the video clip. Is the logic that if pupil diameters roughly match (per clip) across the two episodes, participants must be similarly engaged?


### Minor comments:

I would encourage the authors to share the materials used for behavioral assessment (e.g. the questionnaire testing narrative comprehension).

Page 8: “principle components” > “principal components”

Page 8: What proportion of variance in functional connectivity was accounted for by the first three PCs?

Figure 2: “chronoligical” > “chronological”

Discussion: Might be worth further discussing other differences between the two stimulus conditions that might drive differences in neural activity; i.e. are there other possible explanations beside the causal relationships among events?

Page 17: “designed to control for a core component” > I think “manipulate” is probably more appropriate than “control for” here

Page 20: “In conclusion, narratives are of great importance not only to normal human
functioning but also to mental health.” I would change this because this is not a conclusion of the current study and seems largely unrelated to the question at hand.

References: “Oatley, 1992” citation (page 3) is missing from the reference list

### References:

Nastase, S. A., Gazzola, V., Hasson, U., & Keysers, C. (2019). Measuring shared responses across subjects using intersubject correlation. Social Cognitive and Affective Neuroscience, 14(6), 667-685. [`DOI`](https://doi.org/10.1093/scan/nsz037)

Oatley, K. (1992). Best Laid Schemes: The Psychology of the Emotions. Cambridge University Press.

Simony, E., Honey, C. J., Chen, J., Lositsky, O., Yeshurun, Y., Wiesel, A., & Hasson, U. (2016). Dynamic reconfiguration of the default mode network during narrative comprehension. Nature Communications, 7, 12141. [`DOI`](https://doi.org/10.1038/ncomms12141)

