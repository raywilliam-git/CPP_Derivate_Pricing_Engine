# Derivative Pricing Engine

C++ quantitative finance project implementing option pricing models and numerical experiments.

## Features

- European call/put payoff
- Black-Scholes analytical pricing
- Greeks computation: Delta, Gamma, Vega
- Monte Carlo pricing with confidence intervals
- Convergence analysis
- Arithmetic Asian option pricing
- Geometric Asian option pricing
- CSV generation and Python visualization

## Project Structure

```text
include/     Header files
src/         C++ implementation files
examples/    Numerical experiments
scripts/     Python plotting scripts
results/     Generated CSV files
plots/       Generated figures
main.cpp     Testing Pricers

```

## Project Structure

```text
include/     Header files and class definitions
src/         C++ Core pricing engine implementation
examples/    Numerical experiments and simulations
scripts/     Python plotting and data visualization
results/     CSV output files
plots/       Generated result figures

```
## Methodology

The project implements several pricing methods for derivative products under the assumption of geometric Brownian motion.

- Comparison between analytical Black-Scholes price and Monte Carlo estimator
- Monte Carlo convergence with increasing number of simulations
- Confidence interval width analysis
- Distribution of Monte Carlo estimators
- European versus Arithmetic Asian option pricing
- Impact of monitoring dates on Asian option pricing


## Sample Results

### Black-Scholes Price Evolution

![Black-Scholes Price](plots/european_options/call_price_vs_spot.png)

European option price evolution as a function of underlying spot price.
### Delta

![Delta](plots/european_options/call_delta_vs_spot.png)

Sensitivity of option price with respect to spot price variations.


### Monte Carlo Convergence

![Monte Carlo Convergence](plots/european_options/mc_convergence_full.png)

### European vs Asian Option Pricing

Impact of monitoring frequency on arithmetic Asian option valuation.

![European vs Asian](plots/asian_options/asian_vs_european.png)

### Monitoring Frequency Effect on Asian Options

![Asian Monitoring](plots/asian_options/asian_monitoring_dates.png)

## Models Implemented

### Black-Scholes Analytical Pricing

Closed-form pricing formula for European options under the Black-Scholes framework.

### Monte Carlo Pricing

Simulation of asset trajectories under geometric Brownian motion with confidence interval estimation.

### Asian Options

Pricing of path-dependent arithmetic and geometric Asian options using Monte Carlo path simulation.

## Further Extensions

Advanced quantitative finance models currently being explored in Python separately in another repository focused on stochastic calculus and derivative pricing theory.

Potential additions include:

- Barrier option pricing
- Variance reduction methods
- Control variate techniques
- PDE-based pricing solvers
- Implied volatility calibration