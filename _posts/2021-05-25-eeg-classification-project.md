---
layout: post
title: "EEG Classification for Motor Imagery Tasks"
date: 2021-05-25 11:14:10 -0400
categories: deep-learning brain-computer-interfaces
---

As a final project for Deep Learning and Neural Networks at UCLA, my group
implemented various neural network models to perform motor imagery
classification of EEG data from the BCI competition IV (dataset 2a)[^2a]. This
competition took place in 2008 and its goal was to validate signal processing
and classification methods for brain-computer interfaces (BCIs). BCIs are
systems that allow severely disabled people, who are totally paralyzed or
'locked in' by neurological neuromuscular disorders, to control external devices
directly from brain signals[^bci]. Most BCI methods record electrical signals
using electrodes placed on the surface of the scap (i.e. electroencephalography,
EEG), or on the surface of the cerebral cortex. EEG-based motor imagery (EEG MI)
is one of the most popular techniques in BCI due to its non-invasiness, high
temporal resolution, and portability[^eeg].

# EEG Decoding
Decoding of raw EEG signals can be realized through a variety of methods. These
methods can be classified roughly into five main categories[^decode]:
1. Linear classifiers (e.g. Support Vector Machines, SVMs)
2. Non-linear Bayesian classifiers (e.g. Hidden Markov Models, HMMs)
3. Nearest neighbor classifiers (_k_-Nearest Neighbors)
4. Neural networks (e.g. multi-layer perceptron)
5. Combination of different methods using boosting or voting.

These methods generally require pre-processing of the data to overcome low
signal-to-noise (SNR) ratios typical of these recordings. A variety of
pre-processing techniques exist to extract useful features from the data.
Popular techniques include cropping, trial averaging, normalization, band-pass
filtering, and spatial transforms such as common spatial patterns (CSPs). 

# Dataset 2a
The dataset 2a was provided by the Institute for Knowledge and Technology from
the Graz University of Technology.

<!-- Footnote references -->
# References
[^2a]: C. Brunner, R.  Leeb, G.  Muller-Putz, A. Schlogl, and G.
    Pfurtscheller.  BCI competition 2008---Graz data set 2a. _Institute for
    Knowledge Discovery (Laboratory of Brain-Computer Interfaces)_, Graz
    University of Technology, 16:1–6, 2008.

[^bci]: Nicolas-Alonso LF, Gomez-Gil J. Brain computer interfaces, a review.
    Sensors (Basel). 2012;12(2):1211-79. doi: 10.3390/s120201211.
    Epub 2012 Jan 31. PMID: 22438708; PMCID: PMC3304110.

[^eeg]: G. Schalk and  B. Z. Allison. Chapter 26 - Non-invasive brain computer
    interfaces. In E. S. Krames, P. H. Peckham, and A. R. Rezai, editors, 
    _Neuromodulation_ (Second Edition), pages 357–377. Academic Press, second
    edition, 2018. 

[^decode]: P. Wang, A. Jiang, X. Liu, J. Shang, and L. Zhang. LSTM-based
    EEG classification in motor imagery tasks. _IEEE Transactions on Neural
    Systems and Rehabilitation Engineering_, 26(11):2086–2095, 2018.
