---
layout: archive
title: "Open reviews"
permalink: /reviews/2017-01-02-gorgolewski
author_profile: true
---

{% include base_path %}

## January 2, 2017 &mdash; Open review of preprint by Gorgolewski and colleagues: [`review`](https://snastase.github.io/reviews/2017-01-02-gorgolewski)
Gorgolewski, K. J., Alfaro-Almagro, F., Auer, T., Bellec, P., Capota, M., Chakravarty, M. M., Churchill, N. W., Cohen, A. L., Craddock, R. C., Devenyi, G. A., Eklund, A., Esteban, O., Flandin, G., Ghosh, S. S., Guntupalli, J. S., Jenkinson, M., Keshavan, A., Kiar, G., Liem, F., Raamana, P. R., Raffelt, D., Steel, C. J., Quirion, P.-O., Smith, R. E., Strother, S. C., Varoquaux, G., Yarkoni, T., Wang, Y., Poldrack, R. A. (2017). BIDS Apps: improving ease of use, accessibility, and reproducibility of neuroimaging data analysis methods. *bioRxiv*, 079145. [`DOI`](https://doi.org/10.1101/079145)

---

Gorgolewski and colleagues provide a description of their BIDS Apps software. BIDS Apps are lightweight, portable software suites for analyzing neuroimaging data. BIDS Apps seem like a critical and very much needed step forward in standardizing neuroimaging data analysis. Furthermore, BIDS Apps will increase standards for testing and versioning in analysis software, a pivotal component of reproducible neuroscience. As of yet, I’m not a BIDS Apps user (but am enthusiastic about them), so I can only really provide the perspective of an informed outsider / future user. I’ve provided a couple suggestions in terms of framing and examples, as well as a handful of trivial language suggestions. Punctuation (e.g., hyphenation, trailing periods) should be made consistent throughout.

### Major comments:

You make a brief mention of the versatility or modifiability of particular BIDS Apps, but I think emphasizing this might make them more generally appealing from the potential user’s perspective. I understand that part of the appeal is that researchers can use standardized, plug-and-play tools. But most researchers I know like to exercise some control over little parameters here and there (for better or worse). For example, can I easily adjust the width of a spatial smoothing kernel in a preprocessing pipeline? How easily can I adjust the searchlight size or feature selection in hyperalignment? And so on. This is at least partly why so many groups have their own idiosyncratic homebrewed pipeline. It seems that if people don’t feel they’re able to modify parameters to their own (potentially arbitrary) standards, the system won’t be as widely adopted. I don’t think this concern is at all a problem with BIDS Apps per se, and I think they provide for this sort of modifiability (i.e., line 581), but I think the authors might do well to emphasize this a bit more explicitly (perhaps with an additional example).

I’m not very familiar with Docker’s (or Singularity’s) standards for code quality and validation, but I’m curious what the overhead is from the potential developer’s perspective. For example, if I’d like to create or modify a BIDS App and share it with the community, am I required to create unit-tests to ensure my code actually works? Seems like a good community standard to have. I may have glossed over this, but it wasn’t completely clear to me at what stage these standards are enforced (if they are enforced at all).

I understand that BIDS Apps are largely geared toward the cognitive neuroscience and psychology communities, but I’m curious as to whether the “participant-level” and “group-level” stratification terminology is adequately extensible (disclaimer: I’m not overly familiar with the MapReduce model). This framework seems to be derived from psychology’s inclination toward statistical testing for generalization to the human population. The authors express that they’d like to see BIDS Apps (or at least the conceptual framework of BIDS Apps) extend into other domains of neuroscience and biology. However, I’m not sure that this particular participant-/group-level stratification is very appropriate for many of the potential applications outside psychology and cognitive neuroscience. For example, what if I’m doing histology or counting cells, measuring behavior in rats, doing electrophysiology in (usually one or two) macaques, or modeling neuronal populations? These are just toy examples of neuroscientific applications that don’t fit the stratification terminology well. Once again, I don’t think this stratification terminology is problematic, just that it might pay to provide an additional sentence of motivation or more explictly state some caveat as to how the stratification can be adjusted or abandoned for particular applications.

### Minor comments:

Line 64: Is “hundreds” really accurate here? Seems like it could be considerably more.

Line 70: The term “understand” with reference to analysis tools and data seems strange, maybe just say “existing analysis tools to interface with data”.

Line 88: “without that option”... not sure what the option is. Maybe “Windows users are often excluded” or “cannot run software natively”.

Line 102: Might include a reference to reproducibility issues in neuroscience/imaging here.

Line 125, 169: “cost effective” > “cost–effective”.

Line 151: You want “image” here, not “mage”.

Line 181: Hyphenate “command-line” consistently throughout.

Line 196: “organization” is a little confusing here, maybe use “format”.

Line 206: Capitalize “Dockerfile”.

Line 220: “runs first level analysis” > “runs a first-level analysis”.

Line 223: “--particiapant_label” > “--participant_label”.

Table 1: some descriptions have periods, others do not.

Line 409: “saved to an Singularity­-compatible” > “saved to a Singularity-compatible”.

Line 434: “deploy their tools as BIDS Apps to further grow the library.

Line 437: The sentence starting with “For example," is confusingly worded.

Line 458: “of of”

Line 473: “than then”

Line 531: “Thanks to Docker-to-Singularity conversion…” hyphenate Docker-to-Singularity to make this more readable.

Line 535: “arrange” > “arranged”

