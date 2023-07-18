---
layout: archive
title: "Open reviews"
permalink: /reviews/2023-07-18-zimmerman
author_profile: true
---

{% include base_path %}


### July 18, 2023 &mdash; Open review of preprint by Zimmerman and colleagues:
Zimmermann, M., Cusack, R., Bedny, M., Szwed, M. (2023) Auditory areas are recruited for naturalistic visual meaning in early deaf people. *Research Square*. [`DOI`](https://doi.org/10.21203/rs.3.rs-2683286/v1)

---

Zimmerman and colleagues use a naturalistic paradigm to show that secondary auditory cortex in the congenitally deaf is repurposed to process higher-level visual meaning. The authors use an intact silent movie as well as three scrambled versions to isolate brain areas that are synchronized by higher-level narrative content not present in the scrambled narrative. They show that superior temporal cortex in deaf individuals is recruited (more so than in hearing individuals) for the visual narrative, i.e. particularly for the more intact stimuli. They corroborate these findings using HMMs to quantify the granularity at which different regions segment the intact movie into events. This is an interesting naturalistic paradigm in a special population; the analyses are thorough and I believe the results. There’s a good bit of important information relegated to the Methods section that can make it a bit hard to follow and interpret the Results section. Most of my comments are technical questions and clarifications.

### Major comments:

In the second paragraph of your Results section you describe the experimental design (i.e. order and duration of movie segments) in brief. However, there seem to be some important choices implicit in the design that could benefit from another couple sentences of explanation. For example, you present the most scrambled variants first followed by the intact movie in the same order across participants (i.e. no counterbalancing); what’s the motivation for this? Should readers be worried about order effects? (You address this in the Methods, but it might be worth pointing to this more explicitly.) You also mention differences in duration: the scrambled segments are 10 minutes long and you use the final 10 minutes of the movie to match durations. But you also show a full 25 minutes of the movie leading up to the intact 10-minute: presumably the goal here is to build up some larger-scale narrative structure for the intact segment? Do the scrambled versions correspond to that same final 10-minute chunk of the movie? If so, they won’t have the full context as the intact 10-minute segment following the initial 25 minutes of the movie. Overall, I think this is a pretty clever design, but I’m worried readers won’t fully appreciate that if you don’t explain the motivation a little more clearly early on in Results (i.e. not hidden away in Methods).

In the Results texts (line 181), you say the “HMM models were well fitted bilaterally” for the deaf group, but not for the hearing group. I feel like we need to know in more detail what “well-fitted” means quantitatively in order to interpret this as a result. In the following paragraph, you report the numbers of events identified by the HMM (30 in left hemisphere, 70 in right hemisphere); can you also provide an average duration of these events in the text?

In Figure 4 panel D, you report how closely event boundaries in right and left auditory areas match event boundaries from visual and other brain areas. We need a little more information to be able to interpret these results; for example, I can’t figure out what the units are on these numbers in the Figure 4D matrices based on either the figure caption of the Results text. Why are some of the cells highlighted green and not others? Is the color highlighted meaningful (i.e. why is the 4.4 for Te3 / higher-visual not more yellow)? Is it worth comparing event boundaries across deaf and hearing populations? We could also use a bit more precise definition of what you mean by “higher visual” ROIs.

Figure 3 shows “regions with significantly higher synchronization in the deaf versus hearing coloured with temporal window.” Which set of significant regions are these exactly? The union of regions showing significant group differences across all four types of stimuli from Figure S3?

At line 485 in the Methods, you state that “a null distribution was created by permuting the original data using the bootstrapping method.” How exactly was this done? In my understanding, bootstrapping (e.g. resampling subjects with replacement) is usually performed to estimate a distribution centered around your test statistic (i.e. for computing confidence intervals) and does not yield a null distribution; unless you deliberately shift the bootstrap distribution to serve as a null distribution (Smith & Wilson, 1991). In a permutation test, on the other hand, you’re shuffling some experimental assignment to construct a null distribution around zero. It’s not clear what approach you’re using here. In our BrainIAK software (Kumar et al., 2021), we provide software for computing both types of tests on ISCs.

Do you trim some number of TRs off the beginning of the scan (and potentially off the end) prior to computing the ISC? The first few TRs may contain the sudden onset of the visual stimulus, which will likely drive wholesale nonspecific activity across the brain. In our work, we find that trimming off these initial onset/offset transients can yield more content-sensitive ISCs (Nastase et al., 2019).

You calculate the TRW index using the formula *z-ISC intact \*3 + z-ISC scrambled long - z-ISC scrambled short - z-ISC diffeomorphic \*3* presumably to create a linear 3, 1, -1, -3 step-down contrast. I think this makes sense, but is there a precedent for defining an index like this in the field? Readers might benefit from another sentence explaining what exactly a strong effect like this means. For example, you say STS “showed the highest temporal receptive windows index”; does this translate to a steeper slope?

For readers who are not used to thinking about ISC analyses like this, I think it can be helpful to make the logic of the scrambling manipulation as explicit as possible: ISC analysis isolates stimulus-driven neural activity, but is agnostic to the content/features of the stimulus driving the synchrony; showing higher ISC for the intact vs scrambled stimuli indicates that a given brain region is driven by whatever higher-level meaning or narrative features are present in the intact stimulus and not in the scrambled stimulus.

It would be very interesting to see whether an intersubject functional connectivity (ISFC) analysis (Simony et al., 2016) might reveal functional homologous regions between deaf and hearing participants. For example, the authors could correlate the time series from STS in deaf individuals with all voxels in the hearing brains; we might expect that high-level “auditory” areas in the deaf individuals have strong ISFCs with high-level visual areas in hearing individuals. This would suggest that both regions encode some overlapping set of stimulus features. Mantini and colleagues (2012) used a similar method with naturalistic movies to localize functionally homologous brain regions between humans and macaques. This comment reiterates an insightful question from Luca Cecchetti I overheard in response to a conference presentation of this work. I don’t think the authors strictly need to do this analysis to support their findings in the current manuscript, but I think it could lead to some novel insights.


### Minor comments:

Data acquisition: Was simultaneous multislice (SMS) acceleration used to obtain 1.4 s TR with 2.5 mm voxels?

Line 65: “cognitive processes levels” > “cognitive processes across levels”?

Line 74: “removed scrambling” > “removed by scrambling”?

Line 76: “off” > “of” or “off of”?

Line 87: missing a period here?

Line 203: “adopted” > “adapted”

Line 219: “auditory areas early deaf” > “auditory areas in early deaf” or some other missing word?

Line 227: “stimuli, compliments” > “stimuli complement”

Line 241: You say “~.20 second events”; do you really mean .2 seconds (200 ms)? or 20 seconds, or .2 minutes?

Line 264: “watching an visual film” > “watching a visual film”

Line 890: “witch” > “which”

I think some of the references are missing, for example I didn’t find Fine et al., 2005, or the Sadato et al. references.

### References:

Hall, P., & Wilson, S. R. (1991). Two guidelines for bootstrap hypothesis testing. *Biometrics*, 757-762. [`DOI`](https://doi.org/10.2307/2532163)

Kumar, M., Anderson, M. J., Antony, J. W., Baldassano, C., Brooks, P. P., Cai, M. B., Chen, P.-H. C., Ellis, C. T., Henselman-Petrusek, G., Huberdeau, D., Hutchinson, J. B., Li, P. Y., Lu, Q., Manning, J. R., Mennen, A. C., Nastase, S. A., Richard, H., Schapiro, A. C., Schuck, N. W., Shvartsman, M., Sundaraman, N., Suo, D., Turek, J. S., Turner, D. M., Vo, V. A., Wallace, G., Wang, Y., Williams, J. A., Zhang, H., Zhu, X., Capota, M., Cohen, J. D., Hasson, U., Li, K., Ramadge, P. J., Turk-Browne, N. B., Willke, T. L., & Norman, K. A. (2021). BrainIAK: The Brain Imaging Analysis Kit. *Aperture Neuro*, *1*(4). [`DOI`](https://doi.org/10.52294/31bb5b68-2184-411b-8c00-a1dacb61e1da)

Mantini, D., Hasson, U., Betti, V., Perrucci, M. G., Romani, G. L., Corbetta, M., Orban, G. A., & Vanduffel, W. (2012). Interspecies activity correlations reveal functional correspondence between monkey and human brain areas. *Nature Methods*, *9*(3), 277-282. [`DOI`](https://doi.org/10.1038/nmeth.1868)

Nastase, S. A., Gazzola, V., Hasson, U., & Keysers, C. (2019). Measuring shared responses across subjects using intersubject correlation. *Social Cognitive and Affective Neuroscience*, *14*(6), 667-685. [`DOI`](https://doi.org/10.1093/scan/nsz037)

Simony, E., Honey, C. J., Chen, J., Lositsky, O., Yeshurun, Y., Wiesel, A., & Hasson, U. (2016). Dynamic reconfiguration of the default mode network during narrative comprehension. *Nature Communications*, *7*(1), 12141. [`DOI`](https://doi.org/10.1038/ncomms12141)

