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
# Methods in Cognitive Neuroscience
NEU 502B &emdash; Neuroscience: From Molecules to Systems to Behavior
Princeton University, Spring 2024<br>
**Time:** M/W 1:00–4:00 pm<br>
**Location:** PNI A03<br>
**Instructor:** Sam Nastase ([snastase@princeton.edu](snastase@princeton.edu))<br>
**AI:** Declan Campbell ([idcampbell@princeton.edu](idcampbell@princeton.edu))<br>
**Syllabus:** [`Syllabus`](https://docs.google.com/document/d/16RAUEHIpq1X_S3GnfHbpQrVCqEunOiURF73KJy7xCv0/edit?usp=sharing)<br>
**GitHub:** [`GitHub`](https://github.com/NEU502B/neu502b-2024)<br>
**Scratch:** [`Scratch`](https://docs.google.com/document/d/1S9JRnUrNKRSGqgRRz1QnZIP2LKOsgmJvn4EjkYvs_ek/edit?usp=sharing)

{% include base_path %}

---

This lab course covers the methodological landscape of human cognitive neuroscience research. Students will learn the fundamentals of experimental design, data collection, preprocessing, and statistical analysis for fMRI, EEG/MEG, and ECoG, with an emphasis on best practices in reproducible neuroscience. Lectures will set the conceptual foundation for interactive, hands-on lab work using Jupyter notebooks. Advanced topics include multivariate pattern analysis (MVPA), representational similarity analysis (RSA), functional connectivity, intersubject correlation (ISC) analysis, and regularized encoding models. Students will be expected to design, analyze, and write up an fMRI experiment as a final project.

---
### Lecture schedule

| Date | Topic | Slides/code | Homework | Optional reading |
| --- | --- | --- | --- | --- |
| M 1/29 | Introduction and computing tools; MR physics | [`Slides`](https://docs.google.com/presentation/d/1-z-MqUW27vwozxMoEQ8TCV6yht_TK1Bpu-JTmsORBoA/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/fmri-00) | | [`Logothetis et al., 2001`](https://doi.org/10.1038/35084005) [`Buxton, 2013`](https://doi.org/10.1088/0034-4885/76/9/096601) |
| W 1/31 | Biological basis of BOLD | [`Slides`](https://docs.google.com/presentation/d/16vDMc79pclwT4rrTZZYsL904xbFy9BovE_Jvr0b6mwk/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/fmri-01) | | [`Ogawa et al., 1992`](https://doi.org/10.1073/pnas.89.13.5951) [`Bandettini et al., 1992`](https://doi.org/10.1002/mrm.1910250220) [`Kwong et al., 1992`](https://doi.org/10.1073/pnas.89.12.5675) |
| M 2/5 | fMRI experimental design and confounds<br>_Homework 1 (due 2/14)_ | [`Slides`](https://docs.google.com/presentation/d/1ezBwjRqTgxPCW60dQ6ZmTRDKlkIOWbuI_iO-FmB5e34/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/fmri-02) | [`Homework 1`](https://github.com/NEU502B/neu502b-2024/blob/master/homework/homework-1.ipynb) | [`Boynton et al., 1996`](https://doi.org/10.1523/JNEUROSCI.16-13-04207.1996) [`Dale & Buckner, 1997`](https://doi.org/10.1002/%28SICI%291097-0193%281997%295:5%3C329::AID-HBM1%3E3.0.CO;2-5) [`Power et al., 2012`](https://doi.org/10.1016/j.neuroimage.2011.10.018) |
| W 2/7 | fMRI preprocessing and subject-level modeling (GLM) | [`Slides`](https://docs.google.com/presentation/d/1lus5IWj93BsuVC7YQ-zBQPRB_c3rZzTeKA08kXNbYW8/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/fmri-03) | | [`Friston et al., 1994`](https://doi.org/10.1002/hbm.460020402) [`Lindquist, 2008`](https://doi.org/10.1214/09-STS282) [`Esteban et al., 2019`](https://doi.org/10.1038/s41592-018-0235-4) |
| M 2/12 | Group-level analysis and correction for multiple tests | [`Slides`](https://docs.google.com/presentation/d/1j8FfJ9nYZdqNgPujfvPQSJd49AsZaGGv1-xgGIm8ai0/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/fmri-04) | | [`Nichols & Holmes, 2002`](https://doi.org/10.1002/hbm.1058) [`Eklund et al., 2016`](https://doi.org/10.1073/pnas.1602413113) |
| W 2/14 | Best practices in reproducible neuroimaging<br>_Homework 2 (due 2/26)_ | [`Slides`](https://docs.google.com/presentation/d/1twohz2ASBGAHiL6Gm40QCpmIqwwc-Sv3WxUccvQCv5Q/edit?usp=sharing) [`Code`](https://docs.google.com/document/d/1e2EOzLgoWBtczbPj2GmIhWViEHTuIXAyvK-1LsPb-D4/edit?usp=sharing) | [`Homework 2`](https://github.com/NEU502B/neu502b-2024/blob/master/homework/homework-2.ipynb) | [`Carp, 2012`](https://doi.org/10.1016/j.neuroimage.2012.07.004) [`Nichols et al., 2017`](https://doi.org/10.1038/nn.4500) [`Poldrack et al., 2019`](https://doi.org/10.1038/nrn.2016.167) |
| M 2/19 | Multivariate pattern analysis (MVPA) | [`Slides`](https://docs.google.com/presentation/d/1_BjJRgrtiWmdYMjb57YusPXah2q6aMb4lVp2m70tAzQ/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/comp-00) | | [`Haxby et al., 2001`](https://doi.org/10.1126/science.1063736) [`Norman et al., 2006`](https://doi.org/10.1016/j.tics.2006.07.005) [`Tong & Pratte, 2012`](https://doi.org/10.1146/annurev-psych-120710-100412) |
| W 2/21 | Representational similarity analysis (RSA) and searchlights | [`Slides`](https://docs.google.com/presentation/d/1ks_cn-s1qK-nw6_LTxBo3M3azdcdealQG9ofoeMNI68/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/comp-01) | | [`Edelman, 1998`](https://doi.org/10.1017/S0140525X98001253) [`Kriegeskorte et al., 2006`](https://doi.org/10.1073/pnas.0600244103) [`Kriegeskorte et al., 2008`](https://doi.org/10.3389/neuro.06.004.2008) |
| M 2/26 | ~~Voxelwise encoding models~~<br>_~~Homework 3 (due 3/6)~~_<br>_Class canceled_ | | | |
| W 2/28 | _Class canceled_ | | | |
| M 3/4 | Voxelwise encoding models<br>_Homework 3 (due 3/20)_ | [`Slides`](https://docs.google.com/presentation/d/1hb0XHSGrb2RvTLw_59TLU-RQwZFzZ6DarjSl9NJQKfw/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/comp-02) | [`Homework 3`](https://github.com/NEU502B/neu502b-2024/blob/master/homework/homework-3.ipynb) | [`Mitchell et al., 2008`](https://doi.org/10.1126/science.1152876) [`Naselaris et al., 2011`](https://doi.org/10.1016/j.neuroimage.2010.07.073) [`Huth et al., 2016`](https://doi.org/10.1038/nature17637) |
| M 3/6 | Naturalistic design, intersubject correlation, hyperalignment;<br>Structural and functional connectivity | [`Slides`](https://docs.google.com/presentation/d/1txJgErGvC0rmkeCPJIBmOHHsRuAmIeap58-a4ruV3Z0/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/comp-03) | | [`Hasson et al., 2004`](https://doi.org/10.1126/science.1089506) [`Nastase et al., 2019`](https://doi.org/10.1093/scan/nsz037) [`Nastase et al., 2020`](https://doi.org/10.1016/j.neuroimage.2020.117254) [`Haxby et al., 2020`](https://doi.org/10.7554/eLife.56601)<br>[`Bullmore & Sporns, 2009`](https://doi.org/10.1038/nrn2575) [`Biswal et al., 2010`](https://doi.org/10.1073/pnas.0911855107) [`Yeo et al., 2011`](https://doi.org/10.1152/jn.00338.2011) |
| M 3/11 | _No class (spring recess)_ | | | |
| W 3/13 | _No class (spring recess)_ | | | |
| M 3/18 | EEG preprocessing<br>_Homework 4 (due 3/27)_ | [`Slides`](https://docs.google.com/presentation/d/1wZOcnEH2wveMO--kIeRwv0Z05kQaLfNHjG7xDbSaDP0/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/elec-00) | [`Homework 4`](https://github.com/NEU502B/neu502b-2024/blob/master/homework/homework-4.ipynb) | [`Buzsáki et al., 2012`](https://doi.org/10.1038/nrn3241) [`Gramfort et al., 2013`](https://doi.org/10.3389/fnins.2013.00267) |
| W 3/20 | EEG ERP and time-frequency analysis;<br>Project proposal presentations | [`Slides`](https://docs.google.com/presentation/d/1GnkggLjvGLTJxtiF6ZOW435Lbtq9pyq8n9QDvuHhJb0/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/elec-01) | | [`Hillyard & Kutas, 1983`](https://doi.org/10.1146/annurev.ps.34.020183.000341) [`Kutas & Federmeier, 2010`](https://doi.org/10.1146/annurev.psych.093008.131123) [`Fries, 2015`](https://doi.org/10.1016/j.neuron.2015.09.034) [`Cohen, 2017`](https://doi.org/10.1016/j.tins.2017.02.004) |
| M 3/25 | Experimental design in PsychoPy | | | [`Peirce et al., 2019`](https://doi.org/10.3758/s13428-018-01193-y) |
| W 3/27 | fMRI data collection | | | |
| M 4/1 | fMRI data collection | | | |
| W 4/3 | fMRI data collection<br>_Homework 5 (due 4/15)_ | | [`Homework 5`](https://github.com/NEU502B/neu502b-2024/blob/master/homework/homework-5.ipynb) | |
| M 4/8 | EEG facility demonstration | | | |
| W 4/10  | ECoG preprocessing and analysis | [`Slides`](https://docs.google.com/presentation/d/1EUHqt7_IOJU1rLtHWF1ggq9gneOXE1aOr4eUZ0jsjH4/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/elec-02) | | [`Mukamel et al., 2012`](https://doi.org/10.1146/annurev-psych-120709-145401) [`Parvizi & Kastner, 2018`](https://doi.org/10.1038/s41593-018-0108-2) |
| M 4/15 | Parallel distributed processing<br>~~_Homework 6 (due 4/24)_~~ | [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/anns-00) | | [`Rumelhart et al., 1986`](https://doi.org/10.1038/323533a0) [`McClelland et al., 2010`](https://doi.org/10.1016/j.tics.2010.06.002) [`Richards et al., 2019`](https://doi.org/10.1038/s41593-019-0520-2) [`Hasson et al., 2020`](https://doi.org/10.1016/j.neuron.2019.12.002) |
| W 4/17 | Deep learning: vision | [`Slides`](https://docs.google.com/presentation/d/1vi3fxUd2BEdvjk8aeby_r9E2XTl9w9UzukAl0n6jTUM/edit?usp=sharing) [`Code`](https://github.com/NEU502B/neu502b-2024/tree/master/anns-01) | | [`Kriegeskorte et al., 2015`](https://doi.org/10.1146/annurev-vision-082114-035447) [`Yamins & DiCarlo, 2016`](https://doi.org/10.1038/nn.4244) [`Lindsay, 2021`](https://doi.org/10.1162/jocn_a_01544) |
| M 4/22 | Progress report presentations | | | |
| W 4/24 | Deep learning: language | [`Slides`](https://docs.google.com/presentation/d/1O5KXNJCuJyg15fNNZ02jeFrGI5qrO-FXKj2nD0e8mXw/edit?usp=sharing) [`Code`](https://github.com/snastase/encling-tutorial) | | [`Manning et al., 2020`](https://doi.org/10.1073/pnas.1907367117) [`Schrimpf et al., 2021`](https://doi.org/10.1073/pnas.2105646118) [`Goldstein et al., 2022`](https://doi.org/10.1038/s41593-022-01026-4) |
| M 5/6 | _No class (final written report due)_

---

The content of this course is inspired by related courses designed by Leigh Nystrom, Jonathan Cohen, Jody Culham, and Jim Haxby.

---

### Supplementary reading

Rokem, A., & Yarkoni, T. (2024). _Data Science for Neuroimaging: An Introduction_. Princeton University Press. [`link`](https://press.princeton.edu/books/hardcover/9780691222738/data-science-for-neuroimaging)

Huettel, S. A., Song, A. W., & McCarthy, G. (2014). _Functional Magnetic Resonance Imaging_ (3rd Ed.). Sinauer Associates. [`link`](https://global.oup.com/academic/product/functional-magnetic-resonance-imaging-9780878936274)

Poldrack, R. A., Mumford, J. A., & Nichols, T. E. (2011). _Handbook of Functional MRI Data Analysis_. Cambridge University Press. [`DOI`](https://doi.org/10.1017/CBO9780511895029)

Bandettini, P. A. (2020). _fMRI_. MIT Press. [`link`](https://mitpress.mit.edu/9780262538039/fmri/)

Luck, S. J. (2014). _An Introduction to the Event-Related Potential Technique_ (2nd ed.). MIT Press. [`link`](https://mitpress.mit.edu/9780262621960/an-introduction-to-the-event-related-potential-technique/)

McClelland, J. L. (2015). _Explorations in Parallel Distributed Processing: A Handbook of Models, Programs, and Exercises_ (2nd ed.). MIT Press. [`PDF`](https://web.stanford.edu/group/pdplab/pdphandbook/handbook.pdf)

Duvernoy, H. M. (1999). _The Human Brain: Surface, Three-Dimensional Sectional Anatomy with MRI, and Blood Supply_ (2nd ed.). Springer. [`DOI`](https://doi.org/10.1007/978-3-7091-6792-2)

