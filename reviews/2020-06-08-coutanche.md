---
layout: archive
title: "Open reviews"
permalink: /reviews/2020-06-08-coutanche
author_profile: true
---

{% include base_path %}

### June 8, 2020 &mdash; Open review of preprint by Coutanche and colleagues: [`PubPeer`](https://pubpeer.com/publications/CCB7262A58D2C5E4B71F7CA7F136A3#1)
Coutanche, M. N., Akpan, E., & Buckser, R. R. (2020). Representational connectivity analysis: identifying networks of shared changes in representational strength through jackknife resampling. *bioRxiv*. [`DOI`](https://doi.org/10.1101/2020.05.28.103077)

---

Coutanche and colleagues use jackknife resampling to estimate the contribution of each trial to overall representational geometry, then compare these jackknife vectors across ROIs as a measure of “representational connectivity” (RC). They compare this approach to two other related approaches&mdash;inter-areal similarity of RDMs (second-order RSA) and univariate functional (FC)&mdash;on a publicly available fMRI dataset. (I’m the primary author of this dataset.) The method introduced by the authors is interesting, but at times I found it difficult to understand how the method was implemented and how to interpret it. I provide some comments and suggestions on improving the clarity of the manuscript and helping readers understand what this method captures.

### Major comments:

My principal comment is that even after reading the manuscript in full, I don't feel like I have a very good intuition for what RC captures. Applying this new tool to an fMRI dataset and comparing the resulting maps to related methods provides qualitative insights&mdash;but the neurobiological interpretation is still somewhat opaque (to me). The method measures how much any given trial contributes to reproducing the RDM derived from all trials, and how this contribution varies trial-by-trial across brain areas. But what is the brain "doing" on a given trial that yields an activity pattern that better (or worse) approximates the overall pattern constituent of an RDM? Does this relate to intrinsic fluctuations, head motion, global signal, wakefulness/attention? Should this really be interpreted as representational "strength"? I also wonder how the metric for neural similarity may interact with the observed RC. Correlation normalizes for regional-average signal magnitude and variance, but also interacts with the implicit baseline of the GLM and the noise level ([Walther et al., 2016](https://doi.org/10.1016/j.neuroimage.2015.12.012)). I wonder if some kind of simulation or comparisons between jackknife vectors and other variables (e.g. global signal, framewise displacement) could help us better pin down what drives this effect. I don't think all these questions can be reasonably addressed in this single paper, but these interpretational hurdles should be discussed.

I don’t fully understand how you removed individual trials for jackknife resampling and how this relates to the structure of the GLM. I can imagine several ways in which this could be done. You describe using AFNI's [3dDeconvolve](https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dDeconvolve.html) to "to calculate beta coefficients for all TRs during which stimulus clips were presented" (page 7). Does this mean each trial received a separate regressor in one big design matrix, or you performed multiple GLMs where each trial is treated as the only regressor of interest (in the style of [Mumford et al., 2013](https://doi.org/10.1016/j.neuroimage.2011.08.076))? The former seems like a difficult estimation task if every regressor only gets one event, and Mumford et al.'s approach would seem better (e.g. via AFNI's [3dLSS](https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dLSS.html)). (Note that both of these are in contrast to the more typical GLM with 20 regressors for the 20 conditions where each regressor indexes multiple trials.) I assume the GLM is estimated independently for each run? If your GLM(s) returns a coefficient per trial, this simplifies the processing of jackknife resampling trials because you simply exclude each trial coefficient prior to aggregating trials into the RDM. But how do you aggregate the coefficients at each trial into the 20 x 20 RDM? Do you average the coefficient patterns across trials of the same condition prior to computing the RDM, or do you compute trial-by-trial dissimilarities and then aggregate these dissimilarities in the 20 x 20 RDM? To go back to the method of excluding trials for jackknife resample, I can also imagine an approach where you exclude trials before/during the GLM&mdash;i.e. by excluding time points (seems bad) or excluding individual trials when specifying the onsets in your regressor (complicated). The manuscript needs a more detailed explanation of how this was performed (to rule out alternative interpretations).

Following on the previous comment, the structure of these jackknife vectors sometimes wasn’t clear to me. For each iteration of the jackknife, you recompute the RDM with the current trial excluded, then compute the correlation between this RDM and the "whole-series RDM," yielding a vector of correlations. Is the whole-series RDM a single RDM averaged across the five left-out runs? Or do you keep a whole-series RDM separately for each left-out run? For 88 trials, this will yield an 88-long jackknife vector per run (440-long across five runs). (You might consider excluding the 8 button-press repetition trials from analysis, but it's up to you). The connectivity analysis then treats this as something similar to a time series. But this jackknife vector is not strictly a time series, because it excludes non-trial TRs, should have very literal temporal autocorrelation if the GLM is doing its job, and the trials could occur in any order as long as you have trial-to-trial correspondence across brain areas.

I think Figure 3 can be improved to help with the previous comment. The time series plotted in Figure 3 are pretty low-res and it's impossible to read the extraneous axis and tick labels. I think it would be worthwhile to dress this figure up a bit nicer and re-plot these jackknife vectors so their derivation and structure is a bit more obvious. I also don't understand what the middle matrices are supposed to represent. If they were RDMs, I'd expect them to be square, symmetric, with a strong diagonal.

Your leave-one-run-out cross-validation approach will give you "split-data RDMs" as described by [Henriksson et al., 2015](https://doi.org/10.1016/j.neuroimage.2015.04.026). How does the concern about intrinsic fluctuations addressed by Henriksson et al. fit into your understanding of the current approach?

How do you partial out white matter per searchlight? If I understand correctly, you're averaging across white matter voxels within each searchlight to compute a single white matter time series, then partialling this time series out of the correlation between jackknife vectors for each searchlight and VT? But the jackknife vectors are not full time series, they're vectors corresponding to trials (non-trial TRs are excluded); how is this accounted for? I realize this is orthogonal to the question of interest, but it seems like an interesting method and I'm not aware of any precedent in the literature (although it seems related to AFNI's ANATICOR; [Jo et al., 2010](https://doi.org/10.1016/j.neuroimage.2010.04.246)).

The brain maps do not include a correction for multiple tests. I think this is fine, but the authors should provide a justification for this&mdash;i.e. we want to qualitatively compare the permissively thresholded maps. It might also be interesting to report correlations between unthresholded brain maps as a way of quantifying similarity between the methods. It might be worth including the full maps for second-order RSA and FC as supplementary figures; currently only the overlap maps are included. I would also like to see the lateral surfaces! Many of the interesting effects in this dataset have to do with action representation, which is most prominent in lateral occipital, parietal, and somatomotor cortices (even given the VT seed).

In describing the method introduced here, make sure to point out how this method can (or cannot) be extended to other experimental designs differing from [Nastase et al., 2017](https://doi.org/10.1093/cercor/bhx138). For example, can this method be extended to block designs rather than an event-related design? 

In the Discussion on page 21, you mention the lack of significant task modulation. Note that we reported task comparisons in Supplementary Figure 4 ([Nastase et al., 2017](https://doi.org/10.1093/cercor/bhx138)), although these effects were not very compelling at the searchlight level. One potential reason for a nonsignificant effect here is that not all cells of the 20 x 20 RDM are relevant to the behavior vs. taxonomy task manipulation (e.g. should "bird eating" become more or less similar to "primate swimming" under this task manipulation?). Note the [Wen et al., 2018](https://doi.org/10.3389/fnins.2018.01003), also reported task-related differences in connectivity using an intersubject functional connectivity (ISFC) approach.

A couple notes on references: It might be worthwhile to cite an authoritative statistical reference to provide a background on jackknife resampling, but make it clear that you're not really using the jackknife for variance estimation as is typical. We also have a data descriptor paper corresponding to this data release ([Nastase et al., 2018](https://doi.org/10.3389/fnins.2018.00316)); I would also make sure the [OpenNeuro](https://openneuro.org/) accession number ([ds000233](https://openneuro.org/datasets/ds000233)) as well as the URL ([https://openneuro.org/datasets/ds000233](https://openneuro.org/datasets/ds000233)) and/or DOI (e.g. [https://doi.org/10.18112/openneuro.ds000233.v1.0.1](https://doi.org/10.18112/openneuro.ds000233.v1.0.1), depending on your version) are included in the main text somewhere.

I encourage the authors to publicly share their code (e.g. via [GitHub](https://github.com/)), so readers can more easily dig into the details and other researchers can more easily re-use the method.

### Minor comments:

Page 3: when introducing second-order ROI-by-ROI RSA, it might be worth pointing to some more recent examples; e.g. [Henriksson et al., 2015](https://doi.org/10.1016/j.neuroimage.2015.04.026), [Visconti di Oleggio Castello et al., 2017](https://doi.org/10.1038/s41598-017-12559-1), among others

Page 4: "collapsing of timepoints" is not strictly necessary with RSA (e.g., you can create a time-point-by-time-point RDM rather than collapsing over time via a GLM), but you certainly do need more than one time point

Page 6: Figure 1 and 2 might be better combined into a single image

Page 8: missing a period after "20 stimulus clip conditions"

Page 9: the term "modulation" vector seemed to come out of nowhere

Page 11: "RDMS" > "RDMs"

Figure 6 caption: "analysi" > "analysis"

Page 16: "threshold.There" > "threshold. There"

Page 18: the RC between VT and IPS may also be due to surprisingly robust representation of action information in VT as well as in IPS (as reported in [Nastase et al., 2017](https://doi.org/10.1093/cercor/bhx138), and [Haxby et al., 2020](https://doi.org/10.1016/j.neuroimage.2020.116561))


### References:

Haxby, J. V., Gobbini, M. I., & Nastase, S. A. (2020). Naturalistic stimuli reveal a dominant role for agentic action in visual representation. *NeuroImage*, 116561. [`DOI`](https://doi.org/10.1016/j.neuroimage.2020.116561)

Henriksson, L., Khaligh-Razavi, S. M., Kay, K., & Kriegeskorte, N. (2015). Visual representations are dominated by intrinsic fluctuations correlated between areas. *NeuroImage*, *114*, 275–286. [`DOI`](https://doi.org/10.1016/j.neuroimage.2015.04.026)

Jo, H. J., Saad, Z. S., Simmons, W. K., Milbury, L. A., & Cox, R. W. (2010). Mapping sources of correlation in resting state FMRI, with artifact detection and removal. *NeuroImage*, *52*(2), 571–582. [`DOI`](https://doi.org/10.1016/j.neuroimage.2010.04.246)

Mumford, J. A., Turner, B. O., Ashby, F. G., & Poldrack, R. A. (2012). Deconvolving BOLD activation in event-related designs for multivoxel pattern classification analyses. *NeuroImage*, *59*(3), 2636–2643. [`DOI`](https://doi.org/10.1016/j.neuroimage.2011.08.076)

Nastase, S. A., Halchenko, Y. O., Connolly, A. C., Gobbini, M. I., & Haxby, J. V. (2018). Neural responses to naturalistic clips of behaving animals in two different task contexts. *Frontiers in Neuroscience*, *12*, 316. [`DOI`](https://doi.org/10.3389/fnins.2018.00316)

Visconti di Oleggio Castello, M., Halchenko, Y. O., Guntupalli, J. S., Gors, J. D., & Gobbini, M. I. (2017). The neural representation of personally familiar and unfamiliar faces in the distributed system for face perception. *Scientific Reports*, *7*, 12237. [`DOI`](https://doi.org/10.1038/s41598-017-12559-1)

Walther, A., Nili, H., Ejaz, N., Alink, A., Kriegeskorte, N., & Diedrichsen, J. (2016). Reliability of dissimilarity measures for multi-voxel pattern analysis. *NeuroImage*, *137*, 188-200. [`DOI`](https://doi.org/10.1016/j.neuroimage.2015.12.012)

Wen, Z., Yu, T., Yang, X., & Li, Y. (2018). Goal-directed processing of naturalistic stimuli modulates large-scale functional connectivity. *Frontiers in Neuroscience*, *12*, 1003. [`DOI`](https://doi.org/10.3389/fnins.2018.01003)
