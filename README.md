# clamm_submission
This repository contains my submission for the ICFHR2016 COMPETITION ON THE CLASSIFICATION OF MEDIEVAL HANDWRITINGS IN LATIN SCRIPT.

The basic approach is subwindow classification with Deep Convolutional Networks that employ Residual Learning and Batch Normalization.  Networks are trained to classify 227x227 subwindows into one of twelve script classes.  At test time, the large grayscale manuscript image is cut up into overlapping 227x227 subwindows and each is classified.  The resulting classification is then the average prediction of each subwindow.  Caffe is the underlying library used to train/test the CNNs.

To improve accuracy, an ensemble of models may be used, which may be configured in a network config file.  In the network config file, each line specifies the training scale (as a percentage, e.g 100 is orignal size, 50% is half size), the network file, and the weights file (all whitespace separated).   The default network config file 'networks_fast.txt' uses 4 networks, while 'networks_accurate.txt' uses 8 networks.  All provided networks are shown in 'networks_all.txt'.

Note that the provided models assumes the following class ordering and associated integer labels:
1 - Caroline
2 - Cursiva
3 - Humanistic
4 - Humanistic_Cursiva
5 - Hybrida
6 - Uncial
7 - Praegothica
8 - Southern_Textualis
9 - Half_uncial
10 - Semihybrida
11 - Semitextualis
12 - Textualis

