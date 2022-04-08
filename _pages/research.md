---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

Broadly, I am interested in questions of trust in a machine learning (ML) analysis. I work on both tools to detect lack-of-robustness in ML analysis and methods for "robustifying" ML analysis through carefully designed models, algorithms that produce well-calibrated uncertainties, and are robust to poor optima.

### Robustness to perturbations in data or modeling assumptions
Will the inferences drawn from a particular analysis or predictions made by a model change substantially under perturbations to training data, minor variations of modeling assumptions, or upon using alternate learning and inference algorithms? In this line of research, we develop tools for answering these questions.

A naive approach to understanding the effect of data perturbations involves refitting the model of interest to many perturbations of the data. This is infeasible for large datasets and structured latent variable models, which involve expensive marginalization over latent variables. We develop efficient but accurate approximations which involve a single fit to the dataset and allow one to perturb data by dropping time-steps from within a time series or sites from a spatial extent. As a bonus, the same machinery can be used to approximate cross-validation in hidden Markov models and Markov random fields.
* Soumya Ghosh<sup>\*</sup>, Will Stephenson<sup>\*</sup>, Tin D. Nguyen, Sameer Deshpande, Tamara Broderick. [ Approximate Cross-Validation for Structured Models](https://papers.nips.cc/paper/2020/hash/636efd4f9aeb5781e9ea815cdd633e52-Abstract.html) NeurIPS 2020. <sup>\*</sup>equal conributions.
  - Here is a [talk](https://www.youtube.com/watch?v=z0fXHnAvm9E) I gave at ISBA describing this work.
  - Code is availble [here](https://github.com/SoumyaTGhosh/structured-infinitesimal-jackknife) and also as part of the [UQ360 toolbox](https://github.com/IBM/UQ360).

We can also consider the effect of modeling assumptions on inferences drawn from an ML analysis. We look at this question in the context of Gaussian processes and develop a methodology for measuring sensitivity to the choice of the kernel choice. Somewhat surprisingly, we find that in many cases, minor perturbations to the kernel function result in substantially different predictions, calling into question the robustness of the underlying analysis.
- William T. Stephenson, Soumya Ghosh, Tin D. Nguyen, Mikhail Yurochkin, Sameer K. Deshpande, Tamara Broderick. [Measuring the robustness of Gaussian processes to kernel choice](https://arxiv.org/abs/2106.06510). AISTATS 2022.
    <!-- - Here is a [talk](https://www.youtube.com/watch?v=z0fXHnAvm9E) Will Stephenson gave at ISBA describing this work.  -->

### Uncertainty quantification in neural networks
Quantifying the uncertainty of a prediction made by a modern neural network remains challenging. Yet well-calibrated predictive uncertainties are essential for deciding when to abstain from a prediction in safety-critical applications, for producing diverse outputs from generative models, and for effectively traversing the exploration-exploitation tradeoff. Bayesian neural networks (BNN) hold the promise of retaining their point-estimated counterparts' predictive performance while providing well-calibrated uncertainties and principled approaches for model selection. These potential advantages have motivated my research into BNNs. My work has explored the effects of commonly used priors and approximate inference algorithms on the quality of posterior uncertainties in BNNs, and developed algorithms for inference and efficient decision making in BNNs.

- Soumya Ghosh, Francesco Maria Delle Fave, Jonathan Yedidia. [ Assumed density filtering methods for learning bayesian neural networks](https://ojs.aaai.org/index.php/AAAI/article/view/10296). AAAI 2016.
- Soumya Ghosh, Jiayu Yao, Finale Doshi-Velez.[ Structured Variational Learning of Bayesian Neural Networks with Horseshoe Priors](http://proceedings.mlr.press/v80/ghosh18a.html). ICML 2018.
- Soumya Ghosh, Jiayu Yao, Fianle Doshi-Velez. [ Model Selection in Bayesian Neural Networks via Horseshoe Priors](https://jmlr.org/papers/v20/19-236.html). JMLR 2019.
- Jiayu Yao, Weiwei Pan, Soumya Ghosh, Finale Doshi-Velez. [ Quality of Uncertainty Quantification for Bayesian Neural Network Inference](https://arxiv.org/abs/1906.09686). ICML Workshop on uncertainty in deep learning 2019.
- Meet P Vadera, Soumya Ghosh, Kenney Ng, Benjamin M Marlin.
[ Post-hoc loss-calibration for Bayesian neural networks](https://arxiv.org/abs/2106.06997). UAI 2021.

I am also interested in uncertainty quantification more broadly. I am a core contributor to the Uncertainty quantification [UQ360](https://github.com/IBM/UQ360) --- an open source toolbox that provides a number of approaches to quantifying, measuring the qualtiy, and communicating uncertainties. A white paper describing the toolbox:
- Soumya Ghosh<sup>\*</sup> and Q. Vera Liao and Karthikeyan Natesan Ramamurthy and Jiri Navratil and Prasanna Sattigeri and Kush R. Varshney and Yunfeng Zhang.
[ Uncertainty Quantification 360: A Holistic Toolkit for Quantifying
and Communicating the Uncertainty of AI](https://arxiv.org/abs/2106.01410). arXiv 2021. <sup>\*</sup>All authors contributed equally.


### Statistical models for healthcare: Hypothesis generation and disease progression Models

Data-driven hypothesis generation can be an effective tool for scientists studying phenomena that are as yet poorly understood. For instance, researchers interested in using data-driven analysis to understand neurodegenerative diseases' progression better. The unique challenges faced in these scenarios have guided my research. Latent variable models can be useful tools for representation learning from clinical registries with noisy data with missing values and more broadly for analyzing case-control studies.    

- Soumya Ghosh, Zhaonan Sun, Ying Li, Yu Cheng, Amrita Mohan, Cristina Sampaio, Jianying Hu. [An exploration of latent structure in observational Huntington’s disease studies](https://www.ncbi.nlm.nih.gov/pmc/articles/pmc5543350/). AMIA CRI 2017.
- Kristen A Severson, Soumya Ghosh, Kenney Ng. [Unsupervised learning with contrastive latent variable models](https://ojs.aaai.org//index.php/AAAI/article/view/4414). AAAI 2019.

These representations are useful for characterizing the progression of diseases from longitudinal follow up of patients. Variants of hidden Markov models are effective for characterizing disease progression as a sequence of jumps between interpretable disease states.

- Zhaonan Sun, Soumya Ghosh, Ying Li, Yu Cheng, Amrita Mohan, Cristina Sampaio, Jianying Hu. [A probabilistic disease progression modeling approach and its application to integrated Huntington’s disease observational data](https://academic.oup.com/jamiaopen/article/2/1/123/5280216). JAMIA Open 2019.
- Kristen A Severson, Lana M Chahine, Luba A Smolensky, Murtaza Dhuliawala, Mark Frasier, Kenney Ng, Soumya Ghosh<sup>\*</sup>, Jianying Hu<sup>\*</sup>. [Discovery of Parkinson's disease states and disease progression modelling: a longitudinal data study using machine learning](https://www.sciencedirect.com/science/article/pii/S2589750021001011). Lancet Digital Health 2021.  <sup>\*</sup>Equal contributions.

Tools for visualizing the results from such progression models are necessary for researchers to glean insights from such progression models.
- Bum Chul Kwon, Vibha Anand, Kristen A Severson, Soumya Ghosh, Zhaonan Sun, Brigitte I Frohnert, Markus Lundgren, Kenney Ng. [DPVis: Visual analytics with hidden markov models for disease progression pathways](https://arxiv.org/pdf/1904.11652). IEEE Transactions on Visualization and Computer Graphics 2020.

### Applied Bayesian non-parametrics for computer vision and model fusion

Bayesian nonparametrics (BNP) provides powerful tools for designing ﬂexible Bayesian models whose complexity is allowed to grow with the amount of data. Observed data thus automatically regularizes the model’s complexity and provides an elegant solution to the model selection conundrum. I have worked on developing spatial BNP (and BNP inspired) priors and robust inference schemes for automatically segmenting images and videos.
- Soumya Ghosh, Andrei Ungureanu, Erik Sudderth, David Blei. [Spatial distance dependent Chinese restaurant processes for image segmentation](https://proceedings.neurips.cc/paper/2011/hash/3d8e28caf901313a554cebc7d32e67e5-Abstract.html). NeurIPS 2011.
- Soumya Ghosh, Erik Sudderth. [Nonparametric learning for layered segmentation of natural images](https://ieeexplore.ieee.org/document/6247937). CVPR 2012.
- Soumya Ghosh, Michalis Raptis, Leonid Sigal, Erik B Sudderth. [Nonparametric Clustering with Distance Dependent Hierarchies](https://www.ics.uci.edu/~sudderth/papers/uai14hddcrp.pdf). UAI 2014.

Methods for discovering parts of 3D object representations.
- Soumya Ghosh, Matthew Loper, Erik Sudderth, Michael Black. [From deformations to parts: Motion-based segmentation of 3D objects](https://papers.nips.cc/paper/2012/hash/a1140a3d0df1c81e24ae954d935e8926-Abstract.html). NeurIPS 2012.

BNP based Methods for federated learning and model fusion.
- Mikhail Yurochkin, Mayank Agarwal, Soumya Ghosh, Kristjan Greenewald, Nghia Hoang, Yasaman Khazaeni. [Bayesian nonparametric federated learning of neural networks](https://arxiv.org/abs/1905.12022). ICML 2019.
- Mikhail Yurochkin, Mayank Agarwal, Soumya Ghosh, Kristjan Greenewald, Nghia Hoang. [Statistical model aggregation via parameter matching](https://arxiv.org/abs/1911.00218). NeurIPS 2019.

See [here](https://scholar.google.com/citations?user=GEYQenQAAAAJ&hl=en) for an up to date list of publications.
