---
layout: splash
title: "Neuroscience: From Molecules to Systems to Behavior"
permalink: /teaching/neu502b
author_profile: true
redirect from:
  - /teaching/neu_502b
  - /courses/neu502b
  - /courses/neu_502b

---
# Neuroscience: From Molecules to Systems to Behavior
Princeton University, NEU 502B, Spring 2023<br>
**Time:** M/W 1:00–4:00 pm<br>
**Location:** PNI A03<br>
**Instructor:** Sam Nastase ([snastase@princeton.edu](snastase@princeton.edu))<br>
**AI:** Gili Karni ([gili@princeton.edu](gili@princeton.edu))<br>
**Syllabus:** [`Syllabus`](https://docs.google.com/document/d/1JRjKDrGgjRPv-Fzc43NnibtK02tIoXBdEJIqEYeyLN0/edit?usp=sharing)<br>
**GitHub:** [`GitHub`](https://github.com/2023-NEU502b)<br>
**Scratch:** [`Scratch`](https://docs.google.com/document/d/1M1lTMpmpQ3u8yGUHTuNSHkBbMV1smjHTDjb3NFVkLew/edit?usp=sharing)

{% include base_path %}

---

This lab course covers the methodological landscape of human cognitive neuroscience research. Students will learn the fundamentals of experimental design, data collection, preprocessing, and statistical analysis for fMRI, EEG/MEG, and ECoG, with an emphasis on best practices in reproducible neuroscience. Lectures will set the conceptual foundation for interactive, hands-on lab work using Jupyter notebooks. Advanced topics include multivariate pattern analysis (MVPA), representational similarity analysis (RSA), functional connectivity, intersubject correlation (ISC) analysis, and regularized encoding models. Students will be expected to design, analyze, and write up an fMRI experiment as a final project.

---
### Lecture schedule

| Date | Topic | Slides/code | Homework | Optional reading |
| --- | --- | --- | --- | --- |
| M 1/30 | Introduction and computing tools; MR physics | [`Slides`](https://docs.google.com/presentation/d/1-z-MqUW27vwozxMoEQ8TCV6yht_TK1Bpu-JTmsORBoA/edit?usp=sharing) [`Code`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/fmri-00/fmri-00-introduction.ipynb) | | [`Logothetis et al., 2001`](https://doi.org/10.1038/35084005) [`Buxton, 2013`](https://doi.org/10.1088/0034-4885/76/9/096601) |
| W 2/1 | Biological basis of BOLD | [`Slides`](https://docs.google.com/presentation/d/16vDMc79pclwT4rrTZZYsL904xbFy9BovE_Jvr0b6mwk/edit?usp=sharing) [`Code`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/fmri-01/fmri-01-visualization.ipynb) | | [`Ogawa et al., 1992`](https://doi.org/10.1073/pnas.89.13.5951) [`Bandettini et al., 1992`](https://doi.org/10.1002/mrm.1910250220) [`Kwong et al., 1992`](https://doi.org/10.1073/pnas.89.12.5675) |
| M 2/6 | fMRI experimental design | [`Slides`](https://docs.google.com/presentation/d/1ezBwjRqTgxPCW60dQ6ZmTRDKlkIOWbuI_iO-FmB5e34/edit?usp=sharing) [`Code`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/fmri-02/fmri-02-design.ipynb) | | [`Boynton et al., 1996`](https://doi.org/10.1523/JNEUROSCI.16-13-04207.1996) [`Dale & Buckner, 1997`](https://doi.org/10.1002/(SICI)1097-0193(1997)5:5%3C329::AID-HBM1%3E3.0.CO;2-5) |
| W 2/8 | fMRI confounds and preprocessing | [`Slides`](https://docs.google.com/presentation/d/1UrtcxPKfP_MyUkQFCcBmRHH2H4RyRoS5FjGCgszGS2k/edit?usp=sharing) [`Code`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/fmri-03/fmri-03-preprocessing.ipynb) | | [`Esteban et al., 2019`](https://doi.org/10.1038/s41592-018-0235-4) [`Power et al., 2012`](https://doi.org/10.1016/j.neuroimage.2011.10.018) |
| M 2/13 | Subject-level modeling (GLM)<br>_Homework 1 (due 2/22)_ | [`Slides`](https://docs.google.com/presentation/d/1202a-QWDFQ6LSnYsVLykpJ2O16A4LwnNoAs9nAWzTTM/edit?usp=sharing) [`Code`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/fmri-04/fmri-04-glm.ipynb) | [`Homework 1`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/homework/homework-1.ipynb) | [`Friston et al., 1994`](https://doi.org/10.1002/hbm.460020402) [`Lindquist, 2008`](https://doi.org/10.1214/09-STS282) |
| W 2/15 | Group-level analysis and correction for multiple tests | [`Slides`](https://docs.google.com/presentation/d/1j8FfJ9nYZdqNgPujfvPQSJd49AsZaGGv1-xgGIm8ai0/edit?usp=sharing) [`Code`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/fmri-05/fmri-05-group.ipynb) | | [`Nichols & Holmes, 2002`](https://doi.org/10.1002/hbm.1058) [`Eklund et al., 2016`](https://doi.org/10.1073/pnas.1602413113) |
| M 2/20 | Best practices in reproducible neuroimaging | [`Slides`](https://docs.google.com/presentation/d/1twohz2ASBGAHiL6Gm40QCpmIqwwc-Sv3WxUccvQCv5Q/edit?usp=sharing) [`Code`](https://docs.google.com/document/d/1e2EOzLgoWBtczbPj2GmIhWViEHTuIXAyvK-1LsPb-D4/edit?usp=sharing) | | [`Carp, 2012`](https://doi.org/10.1016/j.neuroimage.2012.07.004) [`Nichols et al., 2017`](https://doi.org/10.1038/nn.4500) [`Poldrack et al., 2019`](https://doi.org/10.1038/nrn.2016.167) |
| W 2/22 | Multivariate pattern analysis (MVPA) | [`Slides`](https://docs.google.com/presentation/d/1_BjJRgrtiWmdYMjb57YusPXah2q6aMb4lVp2m70tAzQ/edit?usp=sharing) [`Code`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/fmri-06/fmri-06-mvpa.ipynb) | | [`Haxby et al., 2001`](https://doi.org/10.1126/science.1063736) [`Norman et al., 2006`](https://doi.org/10.1016/j.tics.2006.07.005) [`Tong & Pratte, 2012`](https://doi.org/10.1146/annurev-psych-120710-100412) |
| M 2/27 | Representational similarity analysis<br>_Homework 2 (due 3/8)_ | [`Slides`](https://docs.google.com/presentation/d/1ks_cn-s1qK-nw6_LTxBo3M3azdcdealQG9ofoeMNI68/edit?usp=sharing) [`Code`](https://github.com/2023-NEU502B/neu502b-lab/blob/master/comp-01/comp-01-rsa.ipynb) | | [`Edelman, 1998`](https://doi.org/10.1017/S0140525X98001253) [`Kriegeskorte et al., 2008`](https://doi.org/10.3389/neuro.06.004.2008) |
| W 3/1 | Searchlight analysis | | | [`Kriegeskorte et al., 2006`](https://doi.org/10.1073/pnas.0600244103) |
| M 3/6 | Naturalistic design, intersubject correlation, hyperalignment | | | [`Hasson et al., 2004`](https://doi.org/10.1126/science.1089506) [`Nastase et al., 2019`](https://doi.org/10.1093/scan/nsz037) [`Haxby et al., 2020`](https://doi.org/10.7554/eLife.56601) |
| W 3/8 | Voxelwise encoding models | | | [`Mitchell et al., 2008`](https://doi.org/10.1126/science.1152876) [`Naselaris et al., 2011`](https://doi.org/10.1016/j.neuroimage.2010.07.073) [`Huth et al., 2016`](https://doi.org/10.1038/nature17637) |
| M 3/13 | _No class (spring recess)_ | | | |
| W 3/15 | _No class (spring recess)_ | | | |
| M 3/20 | Structural and functional connectivity | | | [`Bullmore & Sporns`](https://doi.org/10.1038/nrn2575) [`Biswal et al., 2010`](https://doi.org/10.1073/pnas.0911855107) [`Yeo et al., 2011`](https://doi.org/10.1152/jn.00338.2011) |
| W 3/22 | EEG preprocessing; project proposal presentations | | | [`Buzsáki et al., 2012`](https://doi.org/10.1038/nrn3241) [`Gramfort et al., 2013`](https://doi.org/10.3389/fnins.2013.00267) |
| M 3/27 | Experimental design in PsychoPy | | | [`Peirce et al., 2019`](https://doi.org/10.3758/s13428-018-01193-y) |
| W 3/29 | EEG facility demonstration | | | |
| M 4/3 | fMRI data collection | | | |
| M 4/5 | fMRI data collection | | | |
| M 4/10 | EEG ERP analysis | | | [`Hillyard & Kutas, 1983`](https://doi.org/10.1146/annurev.ps.34.020183.000341) [`Kutas & Federmeier, 2010`](https://doi.org/10.1146/annurev.psych.093008.131123) |
| W 4/12  | EEG time-frequency analysis | | | [`Fries, 2015`](https://doi.org/10.1016/j.neuron.2015.09.034) [`Cohen, 2017`](https://doi.org/10.1016/j.tins.2017.02.004) |
| M 4/17 | ECoG preprocessing and analysis | | | [`Engel et al., 2005`](https://doi.org/10.1038/nrn1585) [`Mukamel et al., 2012`](https://doi.org/10.1146/annurev-psych-120709-145401) [`Parvizi & Kastner, 2018`](https://doi.org/10.1038/s41593-018-0108-2) |
| W 4/19 | Progress report presentations | | | |
| M 4/24 | Convolutional neural networks | | | [`Krizhevsky et al., 2012`](https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf) [`Yamins & DiCarlo, 2016`](https://doi.org/10.1038/nn.4244) |
| W 4/26 | Recurrent neural networks, transformers | | | [`Vaswani et al., 2017`](https://proceedings.neurips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf) [`Goldstein et al., 2022`](https://doi.org/10.1038/s41593-022-01026-4) |
| M 5/8 | _No class (final written report due)_

---

The content of this course is inspired by related courses designed by Leigh Nystrom, Jody Culham, and Jim Haxby.

---

### Supplementary reading

Huettel, S. A., Song, A. W., & McCarthy, G. (2014). _Functional Magnetic Resonance Imaging_ (3rd Ed.). Sinauer Associates. [`link`](https://global.oup.com/academic/product/functional-magnetic-resonance-imaging-9780878936274)

Poldrack, R. A., Mumford, J. A., & Nichols, T. E. (2011). _Handbook of Functional MRI Data Analysis_. Cambridge University Press. [`DOI`](https://doi.org/10.1017/CBO9780511895029)

Bandettini, P. A. (2020). _fMRI_. MIT Press. [`link`](https://mitpress.mit.edu/9780262538039/fmri/)

Luck, S. J. (2014). _An Introduction to the Event-Related Potential Technique_ (2nd ed.). MIT Press. [`link`](https://mitpress.mit.edu/9780262621960/an-introduction-to-the-event-related-potential-technique/)

McClelland, J. L. (2015). _Explorations in Parallel Distributed Processing: A Handbook of Models, Programs, and Exercises_ (2nd ed.). MIT Press. [`PDF`](https://web.stanford.edu/group/pdplab/pdphandbook/handbook.pdf)

Duvernoy, H. M. (1999). _The Human Brain: Surface, Three-Dimensional Sectional Anatomy with MRI, and Blood Supply_ (2nd ed.). Springer. [`DOI`](https://doi.org/10.1007/978-3-7091-6792-2)
