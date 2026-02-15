---

layout: splash
title: "Computational Language Neuroscience"
permalink: /teaching/psyc599
author_profile: true
redirect from:
  - /teaching/psyc_599
  - /courses/psyc599
  - /courses/psyc_599

---

# Computational Language Neuroscience
PSYC 599<br>
University of Southern California, Spring 2026<br>
**Time:** M/F 12:00–1:50 pm<br>
**Location:** DMC 210<br>
**Instructor:** Sam Nastase ([snastase@usc.edu](snastase@usc.edu))<br>
**Syllabus:** [`Syllabus`](https://docs.google.com/document/d/17H-8ThrU89yJt2NS8-QaRjVV-hABaa6TSh7tkmDWrW8/edit?usp=sharing)<br>
**GitHub:** [`GitHub`](https://github.com/snastase/psyc599)<br>
**Presentations:** [`Sign-up`](https://docs.google.com/spreadsheets/d/15AJUuHAlwxfI7AYNehZykvKmhrjKUVvazW6IiLkqJoo/edit?usp=sharing)<br>
**Scratch:** [`Scratch`](https://docs.google.com/document/d/1NOeg1BmQQTmW6PodCq2RZPcZUHugRVAQlffDSbiblzI/edit?usp=sharing)

{% include base_path %}

---

This course explores the computational parallels between deep learning models for language and the human brain. Classes will primarily comprise student-led presentations of the weekly readings and active discussions of different viewpoints in the literature. Early readings are rooted in historical debates surrounding symbolic computation, statistical learning, and connectionism; later readings focus on current developments in the computational neuroscience of language and communication, with a focus on large language models (LLMs). Programming exercises will provide a hands-on introduction to state-of-the-art methods used in computational language neuroscience. The second half of the course will culminate in group projects where students design, implement, and write up novel experiments combining language models (e.g., LLMs) and open neuroscience datasets (e.g., fMRI, ECoG). The intended audience for this course is PhD students in psychology, neuroscience, linguistics, or computer science.

---

### Final project milestones

**M 3/2:** form group and develop a general research question (e.g., data, method)

**M 3/9:** in-class project proposal presentation (a few slides) to workshop question/methods

**M 4/6:** in-class progress report presentations comprising preliminary results

**F 5/1:** in-class final project presentation comprising core results and outstanding questions

**F 5/8:** deadline for final written report comprising introduction, methods, results, and discussion with accompanying figures and code

---

### Course schedule

| Week | Topic | Readings | Notes |
| --- | --- | --- | --- |
| Week 1 | Introduction to the neurobiology of language | [`Geschwind, 1970`](https://doi.org/10.1126/science.170.3961.940) [`Tremblay & Dick, 2016`](https://doi.org/10.1016/j.bandl.2016.08.004) [`Friederici et al., 2017`](https://doi.org/10.1038/s41562-017-0184-4) [`Hagoort, 2019`](https://doi.org/10.1126/science.aax0289) [`Fedorenko et al., 2024`](https://doi.org/10.1038/s41586-024-07522-w) | [`Slides`](https://docs.google.com/presentation/d/1avI2CIf_UhG56zpKmqun2sNcrMZiiFNzC7r1LFK_nXw/edit?usp=sharing) |
| Week 2 | Mapping the cortical language network | [`Hickok & Poeppel, 2007`](https://doi.org/10.1038/nrn2113) [`Friederici, 2011`](https://doi.org/10.1152/physrev.00006.2011) [`Lerner et al., 2011`](https://doi.org/10.1523/JNEUROSCI.3684-10.2011) [`Price, 2012`](https://doi.org/10.1016/j.neuroimage.2012.04.062) [`Fedorenko et al., 2024`](https://doi.org/10.1038/s41583-024-00802-4) | [`Lab 1`](https://github.com/snastase/psyc599/blob/main/labs/lab-1-localizer.ipynb) |
| Week 3 | Connectionist models of linguistic structure | [`McClelland & Rumelhart, 1981`](https://psycnet.apa.org/doi/10.1037/0033-295X.88.5.375) [`Rumelhart & McClelland, 1986`](https://doi.org/10.7551/mitpress/5237.003.0008) [`Pinker & Prince, 1988`](https://doi.org/10.1016/0010-0277(88)90032-7) [`Fodor & Pylyshyn, 1988`](https://doi.org/10.1016/0010-0277(88)90031-5) [`Smolensky, 1988`](https://doi.org/10.1017/S0140525X00052432) [`McClelland & Patterson, 2002`](https://doi.org/10.1016/S1364-6613(02)01993-9) | [`Slides`](https://docs.google.com/presentation/d/1nn1nwrRvjv363kioUsusfPxOiI2skPRrjyFIRxd1BOI/edit?usp=sharing) |
| Week 4 | Statistical learning for language acquisition | [`Saffran et al., 1996`](https://doi.org/10.1126/science.274.5294.1926) [`Marcus et al., 1999`](https://doi.org/10.1126/science.283.5398.77) [`McClelland & Plaut, 1999`](https://doi.org/10.1016/S1364-6613(99)01320-0) [`Elman, 2004`](https://doi.org/10.1016/j.tics.2004.05.003) [`Contreras Kallens et al., 2023`](https://doi.org/10.1111/cogs.13256) | [`Lab 2`](https://github.com/snastase/psyc599/blob/main/labs/lab-2-isc.ipynb) |
| Week 5 | Representational geometry (with a detour into vision) | [`Rumelhart & Abrahamson, 1973`](https://doi.org/10.1016/0010-0285(73)90023-6) [`Shepard, 1987`](https://doi.org/10.1126/science.3629243) [`Edelman, 1998`](https://doi.org/10.1017/S0140525X98001253) [`Kriegeskorte & Kievit, 2013`](https://doi.org/10.1016/j.tics.2013.06.007) [`Mikolov et al., 2013`](https://aclanthology.org/N13-1090/) [`Kriegeskorte et al., 2015`](https://doi.org/10.1146/annurev-vision-082114-035447) | |
| Week 6 | Encoding models (with a detour into vision) | Yamins & DiCarlo, *Nat. Neurosci.*, 2016 [`DOI`](https://doi.org/10.1038/nn.4244) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-6/Yamins_NatNeurosci_2016.pdf)<br> Huth et al., *Nature*, 2016 [`DOI`](https://doi.org/10.1038/nature17637) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-6/Huth_Nature_2016.pdf)<br> de Heer et al., *J. Neurosci.*, 2017 [`DOI`](https://doi.org/10.1523/JNEUROSCI.3267-16.2017) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-6/deHeer_JNeurosci_2017.pdf)
