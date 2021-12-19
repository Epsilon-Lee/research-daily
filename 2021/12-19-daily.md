
> *"There's been a lot of talk recently about dataset-focused ML research. What are some good examples of recent papers exploring the role and effect of datasets? Not sure how to best say this, but looking for papers focusing on broad methodology rather than specific applications"*

- [Gautam Kamath's tweet](https://twitter.com/thegautamkamath/status/1471892297780400134), about works on data-centric machine learning.
  - In the comment, Daniel Hsu (a great researcher of machine learning) has commented on *"perhaps you've heard of Imagenet Cifar Mnist Learning?"*, he might intend that the current so-called real-world data-centric challenges are tested and resolved on unrealistic datasets. And in fact, we are always under-estimating the difficulties in real-world situations.
  - This year's [data-centric AI workshop](https://datacentricai.org/) at NeurIPS.
  - [DataCLUE: A Benchmark Suite for Data-centric NLP](https://arxiv.org/pdf/2111.08647.pdf), to be more engaged in this campaign, I think this paper with our Chinese NL understanding benchmark CLUE would be a nice starting point for trying several ideas upon.
  - The most relevant info I got from this tweet is a talk by Alex Madry, the abstract is:
    - > *Machine learning models tend to rely on an abundance of training data. Yet, understanding the underlying structure of this data—and models’ exact dependence on it—remains a challenge. In this talk, we will present a framework for directly modeling predictions as functions of training data. This framework, given a dataset and a learning algorithm, pinpoints—at varying levels of granularity—the relationships between train and test point pairs through the lens of the corresponding model class. Even in its most basic version, our framework enables many applications, including discovering subpopulations, quantifying model brittleness via counterfactuals, and identifying train-test leakage.*
    - I am particularly interested in the concept of data certificate for guarantee instance-wise generalization for models in real-world applications like image/text classifier and neural machine translation.
    - Madry's talk can be watched [here](https://www.ideal.northwestern.edu/events/mini-workshop-on-new-directions-on-robustness-in-ml/).

---

A nice paper from several great research groups.

- [Quantifying and Understanding Adversarial Examples in Discrete Input Spaces](https://arxiv.org/pdf/2112.06276.pdf), Dec. 12 2021.
  - > *"we formalize a notion of **synonymous adversarial examples** that applies in any discrete setting and describe a simple domain-agnostic algorithm to construct such examples [...] We seek to understand their prevalence theoretically and we attribute their existence to spurious token correlations, a statistical phenomenon that is specific to discrete spaces."*
  - **Meta-speaking**, This paper is a nice research project that connects real-world empirical observations to theory-grounded guarantees
  - > *We seek to understand the prevalence of adversarial examples theoretically, and we attribute their existence to spurious token correlations, a statistical phenomenon that is specific to discrete spaces and that is caused by an imbalance between the dimensionality of a problem (e.g., the size of a natural language vocabulary) and the size of the dataset. In brief, if the vocabulary of possible discrete tokens is very large, many tokens will accidentally correlate with a label given a finite dataset. These can be used to replace valid tokens to induce the correct class prediction to flip. We provide a theoretical analysis of this phenomenon, including bounds on the prevalence of spuriously correlated tokens.*
  - I am quite interested on how they formalize the notion of dimensionality mismatch between vocab. size and number of dataset as well as the identification of the spurious token correlation phenomenon.
