---
layout: archive
title: "Open reviews"
permalink: /reviews/2026-01-04-katlowitz
author_profile: true
---

{% include base_path %}


### January 4, 2026 &mdash; Open review of Katlowitz and colleagues:
Katlowitz, K. A., Belanger, J. L., Ismail, T., Chavez, A. G., Chericoni, A., Franch, M., ... & Hayden, B. Y. (2025). Attention is all you need (in the brain): semantic contextualization in human hippocampus. *bioRxiv*. [`DOI`](https://doi.org/10.1101/2025.06.23.661103)

---

Katlowitz and colleagues show that human hippocampal neurons encode the position of preceding words and that the activity vector for any given word is inflected by the preceding words. Critically, they also show that the degree to which prior words impact the current word corresponds to the attention weights of a large language (LLM). I think this is a neat collection of findings: the analyses are comprehensive and detailed, the framing and references are solid, and they take advantage of a very rare and exciting dataset of invasive single-neuron recordings in human hippocampus (!) while subjects listened to naturalistic spoken narratives. Over the course of the review, I found myself reading a paragraph, starting to write down a question, then realizing the authors neatly answer that question in the next paragraph—this is great. I also appreciate that these results provide some compelling pushback against a dominant narrative in the current literature delineating a “core” language network (that does not include the hippocampus): evidently hippocampal neurons do track some syntactic and semantic features of natural language. This is a remarkable (and potentially controversial) result that I think will have important ramifications for the field. My main thought after reading this was: “Convince me this isn’t just temporal autocorrelation.” I generally believe the results, but I have some comments and clarification questions that I hope can help the authors make their case even more convincing.

### Major comments:

The main question I found myself asking while reading was: How can we be sure these seemingly interesting contextual relationships between the current activity vectors and past activity vectors aren’t just driven by temporal autocorrelation? This is a tricky issue because temporal autocorrelation is presumably a critical part of the computations supporting natural language processing, not just some kind of confound. (I’m less concerned about autocorrelation in the neural activity itself; e.g., as assessed during the rest period.) Tokens in natural language are *meaningfully* autocorrelated over time (and presumably so is the corresponding neural activity). The importance of positional encoding is directly related to this temporal autocorrelation. My main concern here is whether the observed effects in Figs. 2–4 could be partly explained by temporal autocorrelation. For example, one result from the abstract—“neural responses to specific words also reflected a weighted sum of embeddings of preceding words”—could result solely from autocorrelation (although the follow-up analysis showing that the relative weighting of these words corresponds to the LLM attention weights makes the story more interesting). Another example (line 363): “We first found that word-evoked neural responses are related to the non-contextualized semantic embeddings of upcoming words just as they are by past words”—this also sounds like autocorrelation. Is there a way to more explicitly control for or regress out autocorrelation in the core analysis? Or directly measure the autocorrelation in each neuron? (Maybe the authors are already doing this somehow and I’m missing something.) The following two comments point to analytic choice-points where perhaps the authors could more aggressively rule out temporal autocorrelation.

First, I’m a little worried about the word-level randomization procedure used to generate null distributions in the Poisson regression analyses (line 656). Randomizing words will disrupt any temporal autocorrelation in the stimulus-based model features, potentially making the null distribution overly permissive; i.e., the actual data will have matching temporal autocorrelation between model and target, whereas the samples of the null distribution will not, making it difficult to claim that a statistically significant effect is not driven by autocorrelation. The authors could generate null distributions in a way that doesn’t fully disrupt temporal autocorrelation, e.g., block permutation (e.g., [LeBel et al., 2023](https://doi.org/10.1038/s41597-023-02437-z)) or circular time-shift randomization (e.g., [Nastase et al., 2019](https://doi.org/10.1093/scan/nsz037)), to strengthen their claims.

Second, I worry that the cross-validation procedure (or lack thereof) used in the regression analysis could allow for autocorrelation to sneak into the results. First off, I’m wondering about this procedure of using cross-validation to find an optimal hyperparameter, but then refitting an “explanatory model” (with the optimal hyperparameter) on the entire dataset (without cross-validation). I think I understand that you want to do this because you want to be able to more easily extract certain statistical metrics (e.g., LL, AIC), but this model will necessarily be overfit ([Yarkoni & Westfall, 2017](https://doi.org/10.1177/1745691617693393)). For any encoding-style analysis, I would really like to see (in addition to the current “explanatory” results) a performance metric that is fully cross-validated (e.g., correlation between model-predicted and actual neural activity in a left-out test set), consistent with the way ridge-based encoding models have been used by folks in fMRI for the past decade (e.g., [Huth et al., 2016](https://doi.org/10.1038/nature17637); [Dupré la Tour et al., 2024](https://doi.org/10.1162/imag_a_00575)). Second, I’m wondering if the cross-validation procedure is holding out random subsets of words rather than temporally contiguous segments of data. Use randomized cross-validation spits can allow temporal autocorrelation between training and test sets to drive model performance; this can be a real problem for interpretation, as pointed out recently by Hadidi, Feghhi and colleagues ([2025](https://doi.org/10.1101/2025.03.09.642245)). I would ensure that your cross-validation procedure uses temporally contiguous chunks (or, e.g., train on N – 1 stories and test on the left-out story); this kind of cross-validation scheme should be used for both the inner cross-validation loop for hyperparameter optimization and the outer cross-validation loop for model evaluation.

Some of the effect sizes reported here are pretty small. I’m worried that a reader might think “Okay, these linguistic features are vaguely correlated with the activity in hippocampal neurons, but surely these cells are doing something else that just happens to coincide with language now and then.” (...I realize this is an annoying point and applies to just about any result, but it’s easier to fend off when the effect sizes are big :) Anything else the authors can do to mitigate this concern? For example, maybe these effect sizes are not out of the ordinary for naturalistic stimuli? Or maybe other well-established hippocampal results ride on similar effect sizes?

Brief follow-up on the previous point: I’m confused about some of the numbers in the statistical reporting. For example, at line 227 you report a significant effect as “z = 0.65 +/- 1.5, p = 0.004.” What is the “+/- 1.5” here? This variance estimate is twice the size of the effect itself, but still the effect is highly significant? (e.g., if this were a 95% CI, these numbers would be fishy)

Can you give us a little bit more intuition as to what’s going on when you run the community detection algorithm on the APG grids? I’m trying to understand what the clusters correspond to and am still a little bit uncertain after reading the result at 274 and method at 628. Do the clusters correspond to different positions in the context window? Any additional help in understanding/interpreting this cluster analysis would be appreciated.

I’m not sure how to interpret the analysis where you show that the hippocampal activity is associated with the LLM’s top three most likely words. Won’t this necessarily be the case, because the top three most likely words are typically going to be highly similar (and have highly correlated embeddings)? (As a sidenote, my guess is that to generate reasonable language outputs, high enough temperatures are often used that the model will be sampling next tokens from well beyond the top three most probably tokens.)

There some places where the terminology surrounding LLMs leaks a bit too much into discussion of the brain. One example from line 104: I would be careful and maybe use scare quotes around the word “attention” when referring directly to the hippocampus and not specifically attention heads in an LLM. Another example: At line 484, you say “There is no doubt that the human brain operates at the token level as well.” I’m not sure what this is supposed to mean. Different LLMs work with different token vocabularies, and speech or multimodal LLMs (e.g., Whisper) also operate on continuous-time acoustic inputs. My understanding is that tokenization is one of the more fiddly and arbitrary components of modern LLMs. I would argue that the brain does *not* do anything very closely resembling LLM tokenization. In listening, the brain takes in a continuous stream of audio and has to (learn how to) process or chunk the signal into useful segments and structures. It might do some sort of soft, multi-level “tokenization” internally (e.g., syllables, words, phrases, events), but it certainly doesn’t receive speech inputs as a sequence of discrete tokens from big vocabulary. (Even for reading, I would assume that eye-tracking data doesn’t align particularly well with the kinds of sub-word tokens an LLM uses.) Anyway, my point here is just that any leakage or overgeneralization of LLM ideas/terminology into the brain will likely irritate the neuroscientists and may undermine the impact of the paper.

### Minor comments:

Figure 1: “Z scored r values”—do you mean you z-scored the correlation values in a particular sample? Or Fisher z-transformed the correlation values?

Figure 1, panel I: “is a Z scored fitted PSDs”—awkward wording; also make sure to expand the “PSD” acronym the first time you report it.

Line 85: “specifical” > “specific”

Line 116: “not our understanding” > “our understanding”

Line 135: “No matter the mechanism for semantic contextualization, all algorithms must track the ordinal relationships between words.”—This is phrased very confidently and seems obvious, but is this strictly true? The words themselves arrive sequentially and I’m not convinced you couldn’t somehow brute-force that temporal structure immediately into a “spatial” pattern of representation without explicitly tracking the positions. Do vanilla RNNs, for example, have positional encoding? No, but they could still generate two different sequences of representations for the two example sentences.

Line 137: I would consider adjusting this example so that the second word order is also plausible (e.g., “the man chased the dog” vs “the dog chased the man”).

Line 177: It wasn’t obvious to me at first how this Kruskal-Wallis test is used to statisically test position coding; could be worth expanding briefly in the methods.

Line 211: “Viswani” > “Vaswani”

Line 280: “that is, the neural data are not the result of regression against LLM weightings”—you mean “neural results”?

Line 288: “What features predict stronger matches?”—I initially had a hard time understanding what this question was asking.

Line 290: “that that” > “that”

Line 313: “To test this idea, we next compared model fits for contextual and non-contextual embedders”—can you add a brief parenthetical here to tell us which non-contextual embeddings you’re using for this analysis?

Line 340: “the GPT-2’s empiric APG”—awkward wording

Line 526: Maybe I just missed this, but how were sentence boundaries determined? Did your transcription process automagically assign punctuation / sentence boundaries? Just checking, because, unlike written text, sentence boundaries are not completely trivial to recover from natural narrative speech. I can imagine that some analyses, like the ramp coding analysis, could depend pretty heavily on the sentence boundaries.

Line 614: “empiric” > “empirical”

Line 711: I would add +1 to the numerator and denominator of this equation to include the observed test statistic and ensure that your p-values are never zero ([Phipson & Smyth, 2010](https://doi.org/10.2202/1544-6115.1585)).

Nit-picky question about the title: Are the effects of contextualization observed here really (or exclusively) semantic? For example, coding for word position is not very semantic. Surely, syntactic operations are also taking part in the observed effects (e.g., the last sentence of the abstract highlights “the hippocampus’s role in syntactic integration”). Linguists like to pick these different classes of linguistic structure apart, but LLMs do not (and I suspect the human brain does not either). I wonder if a more general / noncommittal word like “Linguistic contextualization” might be more fitting. (Happy to defer to the authors preference, just wanted to raise this point.)

### References:

Dupré la Tour, T., Visconti di Oleggio Castello, M., & Gallant, J. L. (2025). The voxelwise encoding model framework: a tutorial introduction to fitting encoding models to fMRI data. *Imaging Neuroscience*, *3*, imag_a_00575. [`DOI`](https://doi.org/10.1162/imag_a_00575)

Hadidi, N., Feghhi, E., Song, B. H., Blank, I. A., & Kao, J. C. (2025). Illusions of alignment between large language models and brains emerge from fragile methods and overlooked confounds. *bioRxiv*. [`DOI`](https://doi.org/10.1101/2025.03.09.642245)

Huth, A. G., De Heer, W. A., Griffiths, T. L., Theunissen, F. E., & Gallant, J. L. (2016). Natural speech reveals the semantic maps that tile human cerebral cortex. *Nature*, *532*(7600), 453–458. [`DOI`](https://doi.org/10.1038/nature17637)

LeBel, A., Wagner, L., Jain, S., Adhikari-Desai, A., Gupta, B., Morgenthal, A., ... & Huth, A. G. (2023). A natural language fMRI dataset for voxelwise encoding models. *Scientific Data*, *10*, 555. [`DOI`](https://doi.org/10.1038/s41597-023-02437-z)

Nastase, S. A., Gazzola, V., Hasson, U., & Keysers, C. (2019). Measuring shared responses across subjects using intersubject correlation. *Social Cognitive and Affective Neuroscience*, *14*(6), 667–685. [`DOI`](https://doi.org/10.1093/scan/nsz037)

Phipson, B., & Smyth, G. K. (2010). Permutation p-values should never be zero: calculating exact p-values when permutations are randomly drawn. *Statistical Applications in Genetics and Molecular Biology*, *9*, 1. [`DOI`](https://doi.org/10.2202/1544-6115.1585)

Yarkoni, T., & Westfall, J. (2017). Choosing prediction over explanation in psychology: lessons from machine learning. *Perspectives on Psychological Science*, *12*(6), 1100–1122. [`DOI`](https://doi.org/10.1177/1745691617693393)

