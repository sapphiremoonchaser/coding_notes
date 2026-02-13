# Poisson Regression

Used when the dependent variable:
* count data
* non-negative numbers
* right-skewed

It models the log of expected counts.  

Assumes Var(Y) = Mean(Y)
  
Better than OLS for count outcomes

### Overdispersion

Occurs when Var(Y) > Mean(Y)

If present:
* Poisson underestimates standard errors
* Results may appear overly significant

Solution:
* Use Negative Binomial Regression


