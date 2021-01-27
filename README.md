# super-bassoon
Mathematica-based efficient optimization of an inventory replenishment scenario with only two replenishment opportunities. Continuous time, Poisson demand process, classical and Bayesian settings.

![Notebook Screenshot](/readmeFiles/screenShotManipulate.png)

## Problem Overview and Models
This notebook calculates a dual-replenishment-order extension of the Newsvendor problem. In a continuous time setting, with time horizon spanning from 0 to 1, two replenishment orders of sizes x and y are to be received at times 0 and tau, respectively. The goal is to choose x and y so as to minimize cost/maximize profit for given shortage, holding, and purchasing costs, and sale price. The demand is modeled as a Poisson process with parameter lam. Inventory has no salvage value and lead time is zero. 

Three optimization models are considered:

**Model 1**: Select the optimal order quantity x at time 0 assuming that the optimal order quantity y will be selected at time tau. Classical and Bayesian settings are considered.

**Model 2**: Select the optimal order quantities, x and y, at time 0. Classical and Bayesian settings are considered.

**Model 3**: Select the optimal timing tau when the second order should be placed and received. Extension of the classical Model 1.

## Notebook Details
This notebook uses Mathematica's Manipulate function for interactive modeling. As the screenshot below illustrates, user can set cost parameters, price, expected demand for classical setting, prior on demand process for Bayesian setting, replenishment time for Models 1 and 2, and leftover inventory at tau and observed demand up to tau for model 2.

Model calculates a grid of possible solutions, which may take up to few minutes. In order to modify cost or price parameters, choose new vales and click "Update Parameters." This function takes up to few minutes to run. Other parameters do not require clicking this button. In order to calculate the Bayesian models, select parameters (Bayesian prior and Model 3 params) and click "Calculate Bayesian Model."

### Second Interim Formulas in Bayesian Setting
It can be shown that the second interim inventory follows Negative Binomial distribution with properly formulated parameters. When time allows, I will add derivation here.

### Optimization Details
Using efficient formulations for Poisson distribution but also the posterior of Poisson which is a Binomial, precalculate probability tables. Next, a grid search is performed to find the optimal quantities as well as second order time, tau. 
