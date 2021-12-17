
> *"NLP neural network analysis folks: can you think of cases where aspects of the input that should have been irrelevant (e.g. capitalization, whitespace, tokenization, etc) affected your qualitative conclusions? E.g. system can do syntactic thing X only with specific tokenization?"*

- [Tal Linzen's tweet question](https://twitter.com/tallinzen/status/1471482772925653002), :arrow_heading_up:
  - many interesting works are attached to report such sensitivity of neural models on input tokenization, for example
    - one researcher said that *Some of my colleagues found that giving GPT-3 A:B::C:D analogies with the colons performance was near perfect, but much worse in plain language (A is to B as C is to D). Probably has seen A:B::C:D analogy datasets during training.*
    - In the paper ["Attribution Analysis of Grammatical Dependencies in LSTMs"](https://arxiv.org/pdf/2005.00062.pdf), the accuracy of PP-type (e.g. *The surgeon in front of the ministers laughs*) agreement is 85% of capitalized input compared to 65% of lower-cased.
  - but I didn't catch Jacob's comment here: *Green lines in Fig 3 of https://arxiv.org/abs/2112.03204 by @belindazli: changing the tokenization scheme completely changes conclusions about whether pretrained LMs exhibit "compositional adaptability" to new tasks.*

> *"The spectral bias of kernel regression towards the top eigenfunctions of the NTK probably deserves the lion’s share of the credit for the “surprising ability of deep learning to generalize.”  So far this inductive bias has been criminally underappreciated  in the ML community."
> *"I think that the implicit bias of the architecture is probably a more significant contributor to generalization than other things like margins and flatness that have received more attention in the literature. In the kernel regime, the implicit bias of the architecture can be formalized using the idea that kernel regression has an inductive bias towards retuning a function with small RKHS norm, ie one that depends mostly on eigenfunctions with large eigenvalue.  For the NTK of fully connected nets, this means low frequency functions. For CNNs, see Lechao’s new paper. Clearly the kernel regression theory doesn’t hold exactly for real neural nets, but it seems like a good place to start explaining the inductive bias of the architecture for real neural nets."*

- [Jeremy Cohen's tweet](https://twitter.com/deepcohen/status/1470839469712584708), :arrow_heading_up:
  - this is a tweet about understanding generalization ability of neural networks, there are several new terminologies to me
  - for examples:
    - `eigenfunctions`
    - `kernel ridge regression`
    - `infinite-width kernel`
  - [Eigenspace Restructuring: a Principle of Space and Frequency in Neural Networks](https://arxiv.org/abs/2112.05611)
  - [What can linearized neural networks actually say about generalization?](https://arxiv.org/abs/2106.06770)
