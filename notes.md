# Notes on Probabilitic Learning 
> caution many typos, inaccuracies, oversimplification



## MAP and EM
```
L(θ∣X)=p(X∣θ)
```
To find the best fitting θ you have to look for such value that maximizes the conditional probability of θ given X.

expectation-maximalization (EM), it is an algorithm that can be used in maximum likelihood approach for estimating certain kind of models (e.g. involving latent variables, or in missing data scenarios).

[Read more here](https://stats.stackexchange.com/questions/235070/relation-between-map-em-and-mle)

## MCMC

this is just a brute force way of finding a unknown probabilty distribution by taking a shit ton of samples. 
somes ways to do this are 
* Gibbs sampling 
* Metropolis-Hastings  (also a way to sample)
* Hamiltonian Monte Carlo
  * The No U-Turn Sampler (NUTS)


## Variational inference
Even if can model the prior and likelihood with known families of distribution, the posterior p(z|x) remains intractable in general - it cannot be solved analytically
In variational inferencing, we model the posterior directly. Given the observation X, we build a probability model q for latent variables z, i.e. q ≈p(z|X).
* We define an objective to minimize the difference between p and q. This can be done by **maximizing ELBO** (Evidence Lower Bound), which is maximized when p and q are the same. 
  * the joint probability q(θ, z) is still too hard to model. We will break it up and approximate it as q(θ, z) ≈ q(θ) q(z).

[source](https://jonathan-hui.medium.com/machine-learning-variational-inference-273d8e6480bb)

> Variational inference approximates the true posterior by searching the space of variational distributions to find one that is most similar to the true posterior (the yellow star in the figure below) according to some measure of distance or divergence (the black arrow in the figure below).
>
>  However, there are many different ways to measure distance or divergence between probability distributions. Which one should we choose? As indicated by the figure, a theoretically appealing choice is the Kullback-Leibler divergence , but computing this directly requires knowing the true posterior ahead of time, which would defeat the purpose.
> 
> What’s more, we are interested in optimizing this divergence, which might sound even harder, but in fact it is possible to use Bayes’ theorem to rewrite the definition of  as the difference between an intractable constant that does not depend on $\q_{phi}$ and a tractable term called the evidence lower bound (ELBO), defined below. Maximizing this tractable term will therefore produce the same solution as minimizing the original KL-divergence.
 