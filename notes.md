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




[source](https://jonathan-hui.medium.com/machine-learning-variational-inference-273d8e6480bb)


 