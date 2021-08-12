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
Decoding of raw EEG signals can be realized through a variety of methods that
can be classified into five main categories[^decode]:
1. Linear classifiers (e.g. Support Vector Machines, SVMs)
2. Non-linear Bayesian classifiers (e.g. Hidden Markov Models, HMMs)
3. Nearest neighbor classifiers (_k_-Nearest Neighbors)
4. Neural networks (e.g. multi-layer perceptron)
5. Combination of different methods using boosting or voting.

These methods generally require pre-processing of the data to overcome the low
signal-to-noise (SNR) ratios that are typical of these recordings. A variety of
pre-processing techniques exist to extract useful features from the data.
Popular techniques include cropping, trial averaging, normalization, band-pass
filtering, and spatial transforms such as common spatial patterns (CSPs). One
shortcoming of these approaches, however, is that they require expert knowledge
which can introduce bias and reinforce underlying assumptionss about the data.
In contrast, neural networks have the ability to learn representations of the
raw data without pre-processing steps and can potentially consider unknown
correlations in the data [^kostas].

# Dataset
The dataset 2a from the BCI Competition IV consists of EEG data from 9 subjects.
There are four classes in the dataset, each corresponding to imagined movements
of the left hand (class 1), right hand (class 2), both feet (class 3), and
tongue (class 4). Two sessions were recorded for each subject on different days.
Each session is comprised of 6 runs separated by short breaks. One run consists
of 48 trials (12 for each class), giving a total of 288 trials per session.
22 electrodes were placed on the surface of the scalp of the 9 subjects. The
signals were sampled at 250Hz, band-pass filtered between 0.5 and 100Hz, and
notch filtered at 50Hz for line noise supression. In addition to the 22 EEG
channels, 3 monopolar EOG channels were recorded. A more detailed description of
the data and how the trials were conducted and recorded can be found Brunner et
al[^2a].

<!-- Footnote references -->
# References
[^2a]: C. Brunner, R.  Leeb, G.  Muller-Putz, A. Schlogl, and G.
    Pfurtscheller.  BCI competition 2008---Graz data set 2a. _Institute for
    Knowledge Discovery (Laboratory of Brain-Computer Interfaces)_, Graz
    University of Technology, 16:1–6, 2008.

[^kostas]: D. Kostas, E. W. Pang, and F. Rudzicz. Machine learning for
    MEG during speech tasks. Scientific reports, 9(1):1–13, 2019.

[^bci]: L.F. Nicolas-Alonso, J. Gomez-Gil. Brain computer interfaces, a review.
    Sensors (Basel). 2012; 12(2):1211-79. doi: 10.3390/s120201211.
    Epub 2012 Jan 31. PMID: 22438708; PMCID: PMC3304110.

[^eeg]: G. Schalk and  B. Z. Allison. Chapter 26 - Non-invasive brain computer
    interfaces. In E. S. Krames, P. H. Peckham, and A. R. Rezai, editors, 
    _Neuromodulation_ (Second Edition), pages 357–377. Academic Press, second
    edition, 2018. 

[^decode]: P. Wang, A. Jiang, X. Liu, J. Shang, and L. Zhang. LSTM-based
    EEG classification in motor imagery tasks. _IEEE Transactions on Neural
    Systems and Rehabilitation Engineering_, 26(11):2086–2095, 2018.