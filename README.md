[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/simultaneous-classification-and-novelty/out-of-distribution-detection-on-cifar-10)](https://paperswithcode.com/sota/out-of-distribution-detection-on-cifar-10?p=simultaneous-classification-and-novelty)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/simultaneous-classification-and-novelty/out-of-distribution-detection-on-cifar-100)](https://paperswithcode.com/sota/out-of-distribution-detection-on-cifar-100?p=simultaneous-classification-and-novelty)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/simultaneous-classification-and-novelty/out-of-distribution-detection-on-cifar-100-vs)](https://paperswithcode.com/sota/out-of-distribution-detection-on-cifar-100-vs?p=simultaneous-classification-and-novelty)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/simultaneous-classification-and-novelty/out-of-distribution-detection-on-20)](https://paperswithcode.com/sota/out-of-distribution-detection-on-20?p=simultaneous-classification-and-novelty)

# OOD-detection-using-OECC

This repository contains the essential code for the paper [_Outlier Exposure with Confidence Control for Out-of-Distribution Detection_](https://arxiv.org/abs/1906.03509). Accepted as a Journal article in Neurocomputing, 2021.


## 1. What is Outlier Exposure with Confidence Control (OECC)?
[_Outlier Exposure with Confidence Control (OECC)_](https://arxiv.org/abs/1906.03509) is a technique that helps a Deep Neural Network (DNN) learn how to distinguish in- and out-of-distribution (OOD) data <b>without requiring access to OOD samples</b>. This technique has been shown that it can generalize to new distibutions. To learn how to distinguish in- and out-of-distribution samples, OECC makes a DNN to be highly uncertain <b>for OOD samples</b> by producing <b>a uniform distribution at the output of the softmax layer</b>. At the same time, it also makes it to make predictions <b>for in-distribution samples</b> with <b>an average confidence close to its training accuracy</b>, i.e. it controls its confidence. 

<b>The overall OECC loss function outperforms the previous SOTA results in OOD detection with OE both in image and text classification tasks</b>. Additionally, we experimentally show in the [paper](https://arxiv.org/abs/1906.03509) that by combining OECC with SOTA post-training methods for OOD detection like the [_Mahalanobis Detector_](https://github.com/pokaxpoka/deep_Mahalanobis_detector) or the [_Gramian Matrices_](https://arxiv.org/abs/1912.12510), one <b>can achieve SOTA results in the OOD detection task</b>. 


## 2. Visualize the idea behind OECC

<p float="left">
  <img src="/baseline_cifar10_places365_distribution.png" width="410" /> 
  <img src="/OECC_cifar10_places365_distribution.png" width="410" />
</p>
<b>Figure.</b> Histogram of softmax probabilities with CIFAR-10 as in-distribution data D<sub>in</sub> and Places365 as Out-of-Distribution (OOD) data D<sub>out</sub>. Note that D<sub>in</sub> and D<sub>out</sub> are disjoint. <b>Left:</b> Standard maximum softmax probability detector. <b>Right:</b> Maximum softmax probability detector using OECC.  
    

## 3. Download Datasets

Some of the less common datasets can be downloaded by the following links: [80 Million Tiny Images](http://horatio.cs.nyu.edu/mit/tiny/data/tiny_images.bin), [Icons-50](https://github.com/hendrycks/robustness),
[Textures](https://www.robots.ox.ac.uk/~vgg/data/dtd/), [Chars74K](http://www.ee.surrey.ac.uk/CVSSP/demos/chars74k/EnglishImg.tgz), and [Places365](http://places2.csail.mit.edu/download.html). Please also try this link in case the previous link is not working [80 Million Tiny Images](http://www.archive.org/download/80-million-tiny-images-2-of-2/tiny_images.bin).


## 4. How to Run

Each folder has its own separate README file with full details describing how to run the provided code.


## 5. Citation

If you find this useful in your research, please consider citing:

    @article{PAPADOPOULOS2021138,
        title = {Outlier exposure with confidence control for out-of-distribution detection},
        journal = {Neurocomputing},
        volume = {441},
        pages = {138-150},
        year = {2021},
        issn = {0925-2312},
        doi = {https://doi.org/10.1016/j.neucom.2021.02.007},
        url = {https://www.sciencedirect.com/science/article/pii/S0925231221002393},
        author = {Aristotelis-Angelos Papadopoulos and Mohammad Reza Rajati and Nazim Shaikh and Jiamian Wang},
        keywords = {Out-of-distribution detection, Regularization, Anomaly detection, Deep neural networks, Outlier exposure, Calibration}
    }

## 6. Code References

A part of the code has been based on the publicly available codes of [_Outlier Exposure_](https://github.com/hendrycks/outlier-exposure) and [_Mahalanobis_](https://github.com/pokaxpoka/deep_Mahalanobis_detector).
