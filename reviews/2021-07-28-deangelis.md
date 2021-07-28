---
layout: archive
title: "Open reviews"
permalink: /reviews/2021-07-28-deangelis
author_profile: true
---

{% include base_path %}


### July 28, 2021 &mdash; Open review of preprint by De Angelis and colleagues: [`PubPeer`](https://pubpeer.com/publications/F68D34928B43B30632E41C529899E5#1)
De Angelis, L., Gazzola, V., & Keysers, C. (2021). Parametric tests for leave-one-out inter-subject correlations in fMRI provide adequate type I error control while providing high sensitivity. *bioRxiv*. [`DOI`](https://doi.org/10.1101/2020.07.16.206235)

---

De Angelis and colleagues examine cluster-level false positive rates (FPRs) when applying parametric statistical tests to leave-one-out intersubject correlations (ISCs). Intersubject correlations violate the assumption of independence inherent in many common parametric tests (e.g. t-tests) by definition (i.e. each subject contributes to every other subject’s ISC value), so the degree to which they inflate FPRs is an open question. In general, I think this is an increasingly important topic; the authors leverage several open fMRI datasets and provide some useful heuristics for controlling cluster-level FPRs. I have a couple suggestions: I think readers would benefit from a simple simulation showing how non-independence in leave-one-out ISC affects the FPR in a single test, and I think the authors should exercise some caution in using arbitrary cluster-size thresholds. I also include a few questions about methodological details and some minor suggestions on wording/typos.

### Major comments:

The authors evaluate FPRs at the level of cluster inference in real data (similarly to e.g. [Eklund et al., 2016](https://doi.org/10.1073/pnas.1602413113)); i.e. a false positive is registered when a cluster is found to be significant across the entire brain under the null hypothesis (e.g. using resting-state or misaligned naturalistic data where no ISC effect is expected). This has pragmatic value: it’s great to use real data, and many neuroimaging researchers are interested in cluster-level inference. On the other hand, focusing on cluster-level inference introduces a handful of complications and can make the interpretation a little more difficult. The following three comments expand on this.

First, after reading the manuscript, I still don’t feel like I have a good grasp on how the non-independence baked into leave-one-out ISC analysis can inflate FPRs at the level of a single test. I would love to see whether a simulation for one “voxel” would yield some insights into the circumstances where non-independence does or does not inflate FPRs. For example, does the inflationary effect of non-independence in leave-one-out ISC decrease (or increase) systematically with the number of subjects? Under what basic circumstances does leave-one-out ISC actually inflate FPRs? This is a bit difficult to glean from the cluster-level analyses, but could be fairly straightforward to simulate for a single test. Roughly following Chen et al. ([2016](https://doi.org/10.1016/j.neuroimage.2016.05.023)), you could apply leave-one-out ISC followed by a t-test to random time series of a certain (or varying) duration for varying numbers of subjects (e.g. ranging from the pairwise case of N = 2 to N = 10, 20, 30, 40, 50 subjects). Under the leave-one-out approach there’s no direct translation of Chen et al.’s ρ (“rho”) denoting the correlation between two pairwise ISC values pivoting on a shared subject; however, we can at least assume that the interrelatedness between two subjects should scale with 1/N (i.e. decrease with the number of subjects) due to the averaging step in the leave-one-out computation. (You could also try introducing subgroups of varying size with correlated time series to see how this plays through the averaging step to affect FPRs). My point here isn’t to open a can of worms, and I’m not asking for a detailed statistical treatment; I just think a brief simulation of how the leave-one-out ISC computation affects FPRs for a simple test will leave readers with a better intuition of the problem at hand.

Second, the results seem to heavily depend on arbitrary cluster-size thresholds (e.g. k = 5 or k = 20). Cluster-level inference has a handful of moving parts. For example, typical approaches select a fixed cluster-defining threshold (e.g. p < .001) and then use parametric or nonparametric approaches to determine the size of significant clusters occurring by chance. Here, the authors focus on three arbitrary cluster-size thresholds (k = 0, 5, 20). Although there is some precedent in the field for using an arbitrary minimum cluster size (unfortunately), these simple heuristics may not control FPRs (e.g. Figure 2 in [Eklund et al., 2016](https://doi.org/10.1073/pnas.1602413113)). Furthermore, the degree to which these cluster thresholds control FPRs may also depend on the acquisition parameters (e.g. voxel size) and the intrinsic spatial smoothness of the data. This somewhat limits the generalizability of the current findings to other research. On the other hand, the authors do perform RFT-based cluster-level correction (FWEc); this approach at least seems to perform decently well (for HCP and HBN), although it does yield somewhat more inflated FPRs than we see for the SPM approach with CDT = .001 in [Eklund et al., 2016](https://doi.org/10.1073/pnas.1602413113) (Figure 1, middle). In general, I think the authors should be cautious about encouraging researchers to use arbitrary cluster-size thresholds; a permutation-based approach to cluster extent as advocated by [Eklund et al., 2016](https://doi.org/10.1073/pnas.1602413113), would likely provide the most principled control (but will be computationally intensive).

Third, I’m a bit confused about controlling FWE versus FDR in the context of cluster-level FPRs. Controlling FWE at .05 ensures that there’s only a 5% chance of discovering one or more false positives, while controlling FDR at .05 ensures that among all voxels identified as significant only 5% are false positives ([Benjamini & Hochberg, 1995](https://doi.org/10.1111/j.2517-6161.1995.tb02031.x); [Genovese et al., 2002](https://doi.org/10.1006/nimg.2001.1037)). The logic of controlling FWE guides the logic of the simulation framework where the FPR is defined as the proportion of simulated analyses where one or more significant clusters are discovered under the null hypothesis (as in [Eklund et al., 2016](https://doi.org/10.1006/nimg.2001.1037); note that [Eklund et al., 2016](https://doi.org/10.1006/nimg.2001.1037), do not evaluate FDR, although see [Kessler et al., 2017](https://doi.org/10.1073/pnas.1614502114)). I’m not sure how this logic extends to FDR. When we control FDR at 0.05, aren’t we basically conceding that ~5% of the “significant” tests will be false positives? If this is the case, shouldn’t we expect to find false positives in almost every simulated analysis? (In fact this is what the authors observe in the FDR column with cluster-size threshold set to 0 in Figure 2.) I’m not sure what the statistical interpretation is when we then impose an arbitrary cluster-size threshold after FDR correction, but it seems that in many cases it becomes overly conservative.

At page 7, when introducing the procedures used to correct for multiple comparisons, you say “we used αFWE < 0.05 corrected at the voxel level.” How are you controlling FWE here? Bonferroni correction? I’m not sure it makes sense to then apply a cluster-size threshold after a Bonferroni correction; and the results in Figure 2 demonstrate that this procedure is overly conservative in that it reduces FPRs to zero. On the other hand, the fact that Bonferroni correction with no cluster-size threshold yields FPRs exceeding 50% may be cause for concern; does this result from the violation of independence in leave-one-out ISC? Just to confirm: when the cluster-size threshold is set to 0, does this mean that even a single voxel (over the entire brain image) that registers as significant counts into the FPR? 

How are the authors using a bootstrap for the paired- and independent-samples t-tests? I assume for each iteration, you resample subjects with replacement, then compute the paired or group difference to construct a distribution of differences, then subtract the observed difference to shift the distribution to zero for a hypothesis test—is this correct? I’m not sure this is the most appropriate randomization method for a nonparametric two-sample test. I would recommend using a permutation test for both two-sample cases; i.e. permuting the sign of the subject-wise differences in the paired test, and permuting the group assignments in the independent-sample test.

A couple notes on terminology in the figures/captions: The null cluster-size threshold is variously referred to as 1 (e.g. in Figure 1) or 0 (e.g. in Figure 2). Not sure I’d use the term “activation discovery rate” since I’m not sure ISC is rightfully called “activation”; maybe just “FPR” or “proportion of false positive clusters.” I would probably also (re-)specify in Figure 2 and others that FPRs are the proportion of false positive clusters arising out of 1000 simulations.

### Minor comments:

Page 4: “Healty Brain Network” > “Healthy Brain Network”

Page 4: “needed preprocessing” > “required preprocessing”

Figure 1: (very minor) I would probably change the “View” in “Naturalistic View Dataset” to “Viewing” (or “Movie”)

Figure 1 caption: “skin colour”—whose skin? (use “beige” or “peach” or “pink”)

Page 7: Computing ISC over only 10 or 20 volumes seems a bit unusual, as the low number of samples will tend to yield noisy correlations.

Page 8: For the true positive analysis, why do you use the full sample of 150 HBN participants rather than matched N for the N = 10, 20, 30, 40, 50 subsamples? (just curious)

Page 8: “or50” > “or 50”

Page 9: “when applying k = 5”—I think you mean “while applying k = 5” or “although applying k = 5” (is this really really standard practice?)

Page 14: “the bootstrap method that is currently considered to generate optimal results”—I don’t think Gang Chen would necessarily consider the bootstrap “optimal” for leave-one-out ISC analysis

Figure S2: “1000 independet samples” > “1000 independent samples”

### References:

Benjamini, Y., & Hochberg, Y. (1995). Controlling the false discovery rate: a practical and powerful approach to multiple testing. *Journal of the Royal Statistical Society: Series B (Methodological)*, *57*(1), 289–300. [`DOI`](https://doi.org/10.1111/j.2517-6161.1995.tb02031.x)

Chen, G., Shin, Y. W., Taylor, P. A., Glen, D. R., Reynolds, R. C., Israel, R. B., & Cox, R. W. (2016). Untangling the relatedness among correlations, part I: nonparametric approaches to inter-subject correlation analysis at the group level. *NeuroImage*, *142*, 248–259. [`DOI`](https://doi.org/10.1016/j.neuroimage.2016.05.023)

Eklund, A., Nichols, T. E., & Knutsson, H. (2016). Cluster failure: Why fMRI inferences for spatial extent have inflated false-positive rates. *Proceedings of the National Academy of Sciences*, *113*(28), 7900–7905. [`DOI`](https://doi.org/10.1073/pnas.1602413113)

Genovese, C. R., Lazar, N. A., & Nichols, T. (2002). Thresholding of statistical maps in functional neuroimaging using the false discovery rate. *NeuroImage*, *15*(4), 870–878. [`DOI`](https://doi.org/10.1006/nimg.2001.1037)

Kessler, D., Angstadt, M., & Sripada, C. S. (2017). Reevaluating “cluster failure” in fMRI using nonparametric control of the false discovery rate. *Proceedings of the National Academy of Sciences*, *114*(17), E3372–E3373. [`DOI`](https://doi.org/10.1073/pnas.1614502114)

