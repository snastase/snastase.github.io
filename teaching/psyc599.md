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
| Week 1 | Introduction to the neurobiology of language | Geschwind, *Science*, 1970 [`DOI`](https://doi.org/10.1126/science.170.3961.940) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-1/Geschwind_Science_1970.pdf)<br> Tremblay & Dick, *Brain and Language*, 2016 [`DOI`](https://doi.org/10.1016/j.bandl.2016.08.004) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-1/Tremblay_BrainLang_2016.pdf)<br> Friederici et al., *Nat. Hum. Behav.*, 2017 [`DOI`](https://doi.org/10.1038/s41562-017-0184-4) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-1/Friederici_NatHumBehav_2017.pdf)<br> Hagoort, *Science*, 2019 [`DOI`](https://doi.org/10.1126/science.aax0289) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-1/Hagoort_Science_2019.pdf)<br> Fedorenko et al., *Nature*, 2024 [`DOI`](https://doi.org/10.1038/s41586-024-07522-w) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-1/Fedorenko_Nature_2024.pdf) | [`Slides`](https://docs.google.com/presentation/d/1avI2CIf_UhG56zpKmqun2sNcrMZiiFNzC7r1LFK_nXw/edit?usp=sharing) |
| Week 2 | Mapping the cortical language network | Hickok & Poeppel, *Nat. Rev. Neurosci.*, 2007 [`DOI`](https://doi.org/10.1038/nrn2113) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-2/Hickok_NatRevNeurosci_2007.pdf)<br> Friederici, *Physiol. Rev.*, 2011 [`DOI`](https://doi.org/10.1152/physrev.00006.2011) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-2/Friederici_PhysiolRev_2011.pdf)<br> Lerner et al., *J. Neurosci.*, 2011 [`DOI`](https://doi.org/10.1523/JNEUROSCI.3684-10.2011) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-2/Lerner_JNeurosci_2011.pdf)<br> Price, *NeuroImage*, 2012 [`DOI`](https://doi.org/10.1016/j.neuroimage.2012.04.062) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-2/Price_NeuroImage_2012.pdf)<br> Fedorenko et al., *Nat. Rev. Neurosci.*, 2024 [`DOI`](https://doi.org/10.1038/s41583-024-00802-4) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-2/Fedorenko_NatRevNeurosci_2024.pdf) | [`Lab 1`](https://github.com/snastase/psyc599/blob/main/labs/lab-1-localizer.ipynb) |
| Week 3 | Connectionist models of linguistic structure | McClelland & Rumelhart, *Psychol. Rev.*, 1981 [`DOI`](https://doi.org/10.1037/0033-295X.88.5.375) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-3/McClelland_PsycholRev_1981.pdf)<br> Rumelhart & McClelland, *PDP Ch. 18*, 1986 [`DOI`](https://doi.org/10.7551/mitpress/5237.003.0008) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-3/Rumelhart_Ch18_1986.pdf)<br> Fodor & Pylyshyn, *Cognition*, 1988 [`DOI`](https://doi.org/10.1016/0010-0277(88)90031-5) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-3/Fodor_Cognition_1988.pdf)<br> Pinker & Prince, *Cognition*, 1988 [`DOI`](https://doi.org/10.1016/0010-0277(88)90032-7) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-3/Pinker_Cognition_1988.pdf)<br> Smolensky, *Behav. Brain Sci.*, 1988 [`DOI`](https://doi.org/10.1017/S0140525X00052432) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-3/Smolensky_BehavBrainSci_1988.pdf)<br> McClelland & Patterson, *Trends Cogn. Sci.*,  2002 [`DOI`](https://doi.org/10.1016/S1364-6613(02)01993-9) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-3/McClelland_TICS_2002.pdf) | [`Slides`](https://docs.google.com/presentation/d/1nn1nwrRvjv363kioUsusfPxOiI2skPRrjyFIRxd1BOI/edit?usp=sharing) |
| Week 4 | Statistical learning for language acquisition | Saffran et al., *Science*, 1996 [`DOI`](https://doi.org/10.1126/science.274.5294.1926) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-4/Saffran_Science_1996.pdf)<br> Marcus et al., *Science*, 1999 [`DOI`](https://doi.org/10.1126/science.283.5398.77) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-4/Marcus_Science_1999.pdf)<br> McClelland & Plaut, *Trends Cogn. Sci.*, 1999 [`DOI`](https://doi.org/10.1016/S1364-6613(99)01320-0) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-4/McClelland_TrendsCognSci_1999.pdf)<br> Elman, *Trends Cogn. Sci*, 2004 [`DOI`](https://doi.org/10.1016/j.tics.2004.05.003) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-4/Elman_TrendsCognSci_2004.pdf)<br> Contreras Kallens et al., *Cogn. Sci.*, 2023 [`DOI`](https://doi.org/10.1111/cogs.13256) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-4/Contreras_CognSci_2023) | [`Lab 2`](https://github.com/snastase/psyc599/blob/main/labs/lab-2-isc.ipynb) |
| Week 5 | Representational geometry (with a detour into vision) | Rumelhart & Abrahamson, *Cogn. Neuropsychol.*, 1973 [`DOI`](https://doi.org/10.1016/0010-0285(73)90023-6) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-5/Rumelhart_CognPsychol_1973.pdf)<br> Shepard, *Science*, 1987 [`DOI`](https://doi.org/10.1126/science.3629243) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-5/Shepard_Science_1987.pdf)<br> Edelman, *Behav. Brain Sci.*, 1998 [`DOI`](https://doi.org/10.1017/S0140525X98001253) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-5/Edelman_BBS_1998.pdf)<br> Kriegeskorte & Kievit, *Trends Cogn. Sci.*, 2013 [`DOI`](https://doi.org/10.1016/j.tics.2013.06.007) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-5/Kriegeskorte_TICS_2013.pdf)<br> Mikolov et al., *NAACL*, 2013 [`DOI`](https://aclanthology.org/N13-1090/) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-5/Mikolov_NAACL_2013.pdf)<br> Kriegeskorte et al., *Annu. Rev. Vis. Sci.*, 2015 [`DOI`](https://doi.org/10.1146/annurev-vision-082114-035447) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-5/Kriegeskorte_AnnuRevVisSci_2015.pdf) | [`Slides`](https://docs.google.com/presentation/d/1shuPkLb1Mb7eB7i-ZXbqCBhWZoiu_RLZH4794YHvd9U/edit?usp=sharing) |
| Week 6 | Encoding models (with a detour into vision) | Yamins & DiCarlo, *Nat. Neurosci.*, 2016 [`DOI`](https://doi.org/10.1038/nn.4244) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-6/Yamins_NatNeurosci_2016.pdf)<br> Huth et al., *Nature*, 2016 [`DOI`](https://doi.org/10.1038/nature17637) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-6/Huth_Nature_2016.pdf)<br> de Heer et al., *J. Neurosci.*, 2017 [`DOI`](https://doi.org/10.1523/JNEUROSCI.3267-16.2017) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-6/deHeer_JNeurosci_2017.pdf)<br> Dupré la Tour et al., *Imag. Neurosci.*, 2025 [`DOI`](https://doi.org/10.1162/imag_a_00575) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-6/DuprelaTour_ImagNeurosci_2025.pdf) | |
| Week 7 | Emergent linguistic structure in large language models (LLMs) | Vaswani et al., *NeurIPS*, 2017 [`link`](https://papers.nips.cc/paper_files/paper/2017/hash/3f5ee243547dee91fbd053c1c4a845aa-Abstract.html) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-7/Vaswani_NeurIPS_2017.pdf)<br> Manning et al., *PNAS*, 2020 [`DOI`](https://doi.org/10.1073/pnas.1907367117) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-7/Manning_PNAS_2020.pdf)<br> Elhage et al., *Anthropic*, 2021 [`link`](https://transformer-circuits.pub/2021/framework)<br> Linzen & Baroni, *Annu. Rev. Linguist.*, 2021 [`DOI`](https://doi.org/10.1146/annurev-linguistics-032020-051035) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-7/Linzen_AnnuRevLing_2021.pdf)<br> Pavlick, *Annu. Rev. Linguist.*, 2022 [`DOI`](https://doi.org/10.1146/annurev-linguistics-031120-122924) [`PDF`](https://github.com/snastase/psyc599/blob/main/readings/week-7/Pavlick_AnnuRevLing_2022.pdf) | |
