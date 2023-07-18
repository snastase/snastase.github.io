---
layout: archive
title: "Open reviews"
permalink: /reviews/2023-05-05-fitzpatrick
author_profile: true
---

{% include base_path %}


### May 5, 2023 &mdash; Open review of preprint by Fitzpatrick and colleagues:
Fitzpatrick, P. C., Heusser, A. C., & Manning, J. R. (2023). Text embedding models yield high-resolution insights into conceptual knowledge from short multiple-choice quizzes. *PsyArXiv*. [`DOI`](https://doi.org/10.31234/osf.io/dh3q2)

---

Fitzpatrick and colleagues present a neat method for quantifying the content of real-world educational lecture videos and show that the resulting embedding space can be used to better understand and visualize quiz results assessing what knowledge students have learned. This manuscript is well-written and the figures are well-designed; I’m enthusiastic about the approach and the results are compelling. I have a couple clarifying questions about the methods, but my main concerns revolve around making sure the interpretations match the scope of the present data.

### Major comments:

1\. I have two related high-level comments, both of which I’m having hard time articulating. First, I think the authors should be careful about the interpretative language they use throughout. Sometimes the language feels a bit lofty or overreaching. Let me try to provide an example: I’m not sure I fully buy the rhetorical parallel between “memorization” and “understanding.” I don’t think anyone in educational contexts really thinks of rote memorization as memorizing character strings the way a language model might. On the other hand, I don’t really see how the topic model used in the present study (or even much more sophisticated language models) are doing anything above and beyond memorizing statistical (i.e. co-occurrence) structure (albeit at multiple scales). Sure, the model is not a simple, discrete lookup table, but I’m not sure we want to make any strong claim that the model captures “understanding” of physics either. If I understand correctly, the main advance from “memorization” toward “understanding” is made by embedding words in a continuous vector space, granting Shepard- ([1987](https://doi.org/10.1126/science.3629243)) style(?) generalization (i.e. the authors commitment that knowledge is fundamentally “smooth”). But the analyses simply demonstrate that the embeddings for a test set of words (i.e. quiz questions) can be interpolated from the embedding space learned from a training set of words (i.e. the video transcripts). Is this kind of interpolation fundamentally different from “memorization”? (A more radical claim here might be that much of what is seemingly “understanding” can be reduced to this kind of interpolation—which I generally agree with, cf. our [Hasson et al., 2020](https://doi.org/10.1016/j.neuron.2019.12.002) paper—but I doubt the authors really want to make that claim either.)

2a. Second, I think the authors should be very clear about the limits/scope of their approach, particularly based on the dataset used herein. For instance, in the Introduction, you use aspirational language about “the sum total of a person’s knowledge” and “the nearly infinite set of possible things a person could know”—but the actual data/model used here is relatively small-scale (and there’s no explicit evidence for scalability). I can’t imagine that the co-occurrence statistics across only <20 minutes of video lectures are particularly dense or rich. Just to confirm, the model is not pretrained in any way and does not incorporate any conceptual information from outside the lecture videos, right? For example, the authors say (line 492) “Conceptually, each topic is intended to give larger weights to words that are semantically related *or* tend to co-occur in the same documents” (my emphasis on “or”). Does the model know that words are semantically related above and beyond the co-occurrence statistics? My understanding was that “semantically related” is derived entirely from the co-occurrences statistics. In another example, you say “Knowledge estimates need not be limited to the content of the lectures.” But the embedding space is strictly limited to the co-occurrence structure extracted from these particular lectures—right?

2b. Put another way, there’s a tension in the writing between the potential generality of the method and the targeted nature of the embedding space (i.e. tuned to the content of the two lectures) used herein. Here’s a specific example: In my understanding, the negative correlations between mismatching lecture and video topic weights (line 176) are an indicator that the embedding space reflects an “either this or that” structure specific to the two lectures. I have the intuition that near-zero correlation here would provide stronger evidence for “specificity” (line 179) than anticorrelation (as we see with the general physics questions). I wonder if this trivializes the dimensionality reduction results in Figure 7—i.e. could it be any other way? (Maybe this is fine!)

2c. Another specific example: The authors want to make a strong claim that the model doesn’t rely on surface-level similarity and that the “specific words” used in the quiz questions have “very little overlap” with the lectures? But there must be some overlap (i.e. co-occurrence), right? In my understanding, a completely disjoint set of words, none of which occurred in these video transcripts, would not map onto this embedding space in any meaningful way. To be clear, I don’t think this is really a problem or a weakness of the method!—I’m just trying to articulate some discomfort when reading.

3\. How exactly were the questions constructed for each lecture? For example, Figure 2 suggests that the questions follow the trajectories of the lectures, at least to some extent; obviously this is sensible and “by design.” It’s great that the authors provide the full set of questions/answers (Table S1)! However, I think it’s important that the authors describe their thought process in designing the questions a bit more explicitly. For example, how exactly did they minimize “surface-level” similarity while ensuring enough conceptual overlap that the questions map onto the embedding space in a meaningful way?

4\. The authors correlated the topic weights for each question with the topic weights at each time point in the lecture, and in Figure 4 show that “each question appeared to be temporally specific” (line 208). Intuitively, this seems reasonable… But couldn’t this result also be interpreted as creating tension with the idea that the questions aren’t simply keying into “surface-level” similarities? Put another way, if I thought this approach captured some kind of holistic “understanding”, I might hypothesize that good questions would integrate multiple concepts introduced across different parts of the lecture. (I might be conflating the overall validity of the approach for capturing “understanding” with the quality of the questions here.)

5\. The authors used windows comprising 30 lines(?) of the transcript to define documents for input to the topic model. This seems like an important parameter as it impacts the co-occurrence structure observed by the topic model, right? How was this number 30 chosen? I assume it represents some happy medium between providing a wide enough window to yield rich co-occurrence structure while retaining some temporal specificity. Transcript “lines” seems like a somewhat arbitrary unit; I assume it relates to how YouTube renders the transcript? How many words tend to occur in each of these windows? What’s the average duration of these windows in seconds? 

6\. I don’t fully understand the motivation for choosing 15 topics for most of the analyses, or why you increase to 100 topics for Figure 7. I don’t think there’s anything wrong with picking a somewhat arbitrary round number in these cases; just curious if there’s any particular reasoning behind the present choices.

### Minor comments:

Regarding my previous comments on scalability, do the authors think this kind of approach could be extended from topic models to the contextual embeddings learned by large language models? Could be worth mentioning if this is a valid future direction, given the current popularity of these models. My guess is that if we want a method that can capture “the sum total of a person’s knowledge” and “the nearly infinite set of possible things a person could know,” large language models are currently the best approach.

In Figures 2 and 7, you use PCA to visualize two- and three-dimensional projections of the embedding space. What proportion of cumulative variance do these first two and three PCs account for?

All participants saw the Four Fundamental Forces video first, followed by the Birth of a Star video, right? Should we be worried about some order effect?

Line 283: These t-values have 600+ degrees of freedom; I assume this is determined by the total number of questions across all participants. Should we be worried that this kind of statistical test doesn’t take into account subject-level variability? 

Line 492: Do you use a specific set of stop words? (e.g. the NLTK package has a standard list of stop words)

Line 557: “insure” > “ensure”

### References:

Hasson, U., Nastase, S. A., & Goldstein, A. (2020). Direct fit to nature: an evolutionary perspective on biological and artificial neural networks. *Neuron*, *105*(3), 416–434. [`DOI`](https://doi.org/10.1016/j.neuron.2019.12.002)

Shepard, R. N. (1987). Toward a universal law of generalization for psychological science. *Science*, *237*(4820), 1317–1323. [`DOI`](https://doi.org/10.1126/science.3629243)

