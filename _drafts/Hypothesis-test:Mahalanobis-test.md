---
layout: post
title: "Hypothesis testing: introducing the Mahalanobis test for normality"
categories: Machine-Learning Statistics
tags: hypothesis_test 
math: true
---

## Motivation

## Definition

### Multivariate gaussian distribution

$$
f(x)=\frac{1}{\sqrt{(2 \pi)^{k} \operatorname{det} \Sigma}} \exp \left(-\frac{1}{2}(x-\mu)^{T} \Sigma^{-1}(x-\mu)\right)
$$

```python
import scipy
def multivariate_normal(mu, sigma, num_samples, *args, **kwargs):
    return scipy.stats.multivariate_normal(mu, sigma, num_samples, *args, **kwargs)
```

### Moments estimation

```python
import numpy as np
def sample_mean(sample):
    # Empirical mean estimator
    return np.mean(sample, 0)

def sample_covariance_matrix(sample):
    # Empirical covariance matrix estimator
    return np.cov(sample.T)
```
## Mahalanobis distance

$$
M(\mathbf{x},\mathbf{\mu}) = \sqrt{(\mathbf{x}-\mathbf{\mu})\Sigma^{-1}(\mathbf{x}-\mathbf{\mu})^T}
$$

```python
```

## Performance

## Parallel computation

## Further reading

## References
