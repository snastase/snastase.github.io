---
layout: archive
title: "Open reviews"
permalink: /reviews/2022-09-23-gwilliams
author_profile: true
---

{% include base_path %}


### September 23, 2022 &mdash; Open review of preprint by Gwilliams and colleagues:
Gwilliams, L., Flick, G., Marantz, A., Pylkkanen, L., Poeppel, D., & King, J.-R. (2022). MEG-MASC: a high-quality magneto-encephalography dataset for evaluating natural speech processing. *arXiv*. [`link`](https://arxiv.org/abs/2208.11488)

---

Gwilliams and colleagues introduce the MEG-MASC dataset comprising MEG data acquired while participants listened to four stories from the Manually Annotated Sub-Corpus (MASC). This is an interesting, high-quality dataset and the manuscript is concise. I think this will be a very useful contribution to the field and I believe the manuscript is deserving of publication. I have some relatively minor clarification questions, and provide a handful of suggestions to ensure the dataset speaks for itself. I split my review into major and minor comments, but most of the “major” comments are not very major.


### Major comments:

I don’t fully understand the structure of the task labels and story stimuli (line 98, line 135). Do you mean “Cable Spool Boy” is “task-0” and so on in the order they’re listed at the beginning of the “Stimuli” section? As far as I can tell from the events.tsv files, task-0 corresponds to “LW1”, task-1 corresponds to “Cable Spool Boy”, task-2 corresponds to “Easy Money”, and task-3 corresponds to “The Black Willow”. This information should be listed out in a very obvious way in both the manuscript and the dataset (e.g. in the README, the scans.tsv / scans.json files). I think this kind of redundancy is justified if it increases chances that people find the answer to a question about the dataset in the first place they look.

You say the presentation order was pseudorandomized across subjects according to a Latin square (line 71). Is this presentation order summarized somewhere (e.g. in the participants.tsv or each subject’s scans.tsv file)? I suppose it’s recoverable from the events.tsv files—is this correct? It may be worth making it more accessible.

At line 145, you describe a minimal preprocessing pipeline. I understand that there is no consensus on how to best preprocess the data, but would you be willing to include MNE code / scripts for preprocessing the data according to this minimal pipeline, or point toward any current tutorial code MNE may have for this pipeline? It would be helpful for folks who aren’t particularly familiar with MNE preprocessing.

At line 159, you describe using linear ridge regression in scikit-learn. Can you add a little bit more detail about the regularization? For example, are you just using linear_model.Ridge with the default alpha = 1.0, or are you using linear_model.RidgeCV with efficient cross-validation across a range of alpha parameters (default alphas = 0.1, 1.0, 10.0). One additional clarifying sentence or parenthetical would be sufficient.

Following on the previous comment, I don’t understand whether you’re framing the voiced vs. unvoiced decoding analysis as a regression problem or a classification problem. It sounds like a classification problem from the description, but you only mention ridge regression and Pearson correlation. Do you use Pearson correlation to evaluate the classification problem of whether a phoneme is voiced or not? E.g. you get model predictions of 1s (voiced) and 0s (unvoiced) and correlate them with actual phonemes coded as 1s (voiced) and 0s (unvoiced)? Maybe I’m misunderstanding something, but I would have expected a metric like accuracy or ROC in a binary classification problem.

As far as I can tell on OSF, the participants.tsv file contains “n/a” for age, sex, and hand across all participants. However the “Data Records” section suggests that age and gender are included. Is this information not available? Or was it accidentally omitted from the participants.tsv file?

For the T1 anatomical scans (line 77), can you provide any additional details about image acquisition? For example, what is the voxel size / spatial resolution of T1 images? The json files accompanying the FLASH scans have very little metadata. If you run dcm2niix (https://github.com/rordenlab/dcm2niix) on one of the original T1 DICOMs from the MRI, it should recover many of the image acquisition parameters that you can include in the json sidecar.

Make sure your directory trees are consistently structured. For example, in sub-04, you have an additional ses-1 directory inside the ses-1 directory; but this is not the case for other subjects. Another example, I noticed during a spot-check: sub-05 has a ses-1 folder but not a ses-0 folder, while most other subjects who only have session have only ses-0; is this correct?

At line 109, you mention a “stimuli/events” directory where I was expecting to find the time-stamped phonemes and words returned by the Gentle forced-aligner. I don’t see this directory on OSF, but I think this information is encoded into each subject’s events.tsv files—can you clarify?

You included intermittent questions to ensure attentiveness/comprehension (line 73). Are the behavioral questions and responses included in the dataset somewhere? As performance is 98%, I suppose there’s not enough variance for any meaningful analysis. But if these questions and responses are not included in the dataset for that reason, this should be stated explicitly.

Any suggestion as to how users might leverage the repetitions of each story? For example, you users might be able to use the repetitions to estimate within-subject reliability. But on the other hand, hearing a story for the second time isn’t the same as hearing it for the first time. Our first experience of a narrative already sets up certain schema and the second listen doesn’t engage the same set of processes; e.g. the second listen may evoke memory process (some references that come to mind are [Aly et al., 2018](https://doi.org/10.1162/jocn_a_01308) and [Michelmann et al., 2021](https://doi.org/10.1038/s41467-021-25376-y)).

### Minor comments:

It could be worth adding an additional sentence or two pointing out how exactly high-temporal-resolution MEG data can support complementary scientific questions to those accessible with other (e.g. fMRI) datasets. Also any further suggestions as to how these dataset might be analyzed could speed up adoption.

I think the recent paper by Rocca and Yarkoni ([2021](https://doi.org/10.1177/25152459211026864)) makes a pretty good case for the importance of benchmark datasets like this for psychologists / linguists / neuroscientists who may not already be convinced; could be worth citing.

I recommend filling out the dataset_description.json file to include e.g. name (required), license (recommended), authors, how-to-acknowledge, and DOI. The current placeholder version will pass the BIDS Validator, but isn’t actually descriptive.

The README only contains references to two other papers. I would include a short blurb to briefly describe the dataset and link it to other important resources, such as the GitHub repo and the preprint.

One of the stories is titled “Cable Pool Boy” in the manuscript, but is called “cable_spool_fort” in the BIDS metadata; just wanted to make sure there isn’t a typo here.

Line 85: You have a “?” here for the Open American National Corpus—maybe a missing reference?

Line 117: “In particular, the, we used:” > “In particular, we used:”

Line 133: “meg” > “MEG”

Figure 3: The figure caption refers to panel labels (A, B, etc), but the figure itself doesn’t contain panel labels

The MNE and Pandas snippet in “Usage Notes” is very nice!

### References:

Aly, M., Chen, J., Turk-Browne, N. B., & Hasson, U. (2018). Learning naturalistic temporal structure in the posterior medial network. *Journal of Cognitive Neuroscience*, *30*(9), 1345-1365. [`DOI`](https://doi.org/10.1162/jocn_a_01308)

Michelmann, S., Price, A. R., Aubrey, B., Strauss, C. K., Doyle, W. K., Friedman, D., Dugan, P. C., Devinsky, O., Devore, S., Flinker, A., Hasson, U., & Norman, K. A. (2021). Moment-by-moment tracking of naturalistic learning and its underlying hippocampo-cortical interactions. *Nature Communications*, *12*, 5394. [`DOI`](https://doi.org/10.1038/s41467-021-25376-y)

Rocca, R., & Yarkoni, T. (2021). Putting psychology to the test: rethinking model evaluation through benchmarking and prediction. *Advances in Methods and Practices in Psychological Science*, *4*(3), 25152459211026864. [`DOI`](https://doi.org/10.1177/25152459211026864)


