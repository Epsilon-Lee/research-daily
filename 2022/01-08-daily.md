
# Extrapolation versus Interpolation

At the end of this day, I would like to read some papers about `generalization` of deep neural networks.
And use the concept of _extrapolation_ and _interpolation_ to think about current open-domain qa literature.

---

The first paper is called [Learning in High Dimension Always Amounts to Extrapolation](https://arxiv.org/pdf/2110.09485.pdf) (published at Oct. 29 2021) by scientists from Facebook AI Research and NYU.

> **Interpolation**.
> *Interpolation occurs for a sample x whenever this sample falls inside or on the boundary of the given dataset's convex hull.*

> **Extrapolation**
> *Extrapolation occurs when x falls outside the given dataset's convex hull.*

This paper handles the following two common (mis)conceptions:

- sota algorithm work so well because of their ability to correctly interpolate training data
- interpolation happens throughout tasks and datasets

via their empirical and theretic obersations that: *on any high dimensional (>100) dataset, interpolation almost surely never happens*.
