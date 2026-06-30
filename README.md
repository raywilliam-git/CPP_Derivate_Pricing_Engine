# Option Pricing Engine

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

- Comment : As time to maturity decreases, the Black-Scholes price progressively converges toward the option payoff at expiration.
### Delta

![Delta](plots/european_options/call_delta_vs_spot.png)

Sensitivity of option price with respect to spot price variations.

- Comment : The call price is strictly increasing with the underlying price. As maturity decreases, Delta approaches 1 for ITM options, 0 for OTM options, and changes more abruptly around the strike price.


### Monte Carlo Convergence

![Monte Carlo Convergence](plots/european_options/mc_convergence_full.png)

Monte Carlo estimator convergence toward the analytical Black-Scholes price as the number of simulations increases.

- Comment : As the number of simulations increases, the confidence interval narrows and the Monte Carlo estimator converges more accurately toward the Black-Scholes price.

### European vs Asian Option Pricing

![European vs Asian](plots/asian_options/asian_vs_european.png)

Comparison between European and Asian option prices for identical market parameters.

- Comment : Asian options are cheaper than European options as averaging smooths the payoff distribution and reduces exposure to extreme market movements.

### Monitoring Frequency Effect on Asian Options

![Asian Monitoring](plots/asian_options/asian_monitoring_dates.png)

Impact of monitoring frequency on arithmetic Asian option valuation.

- Comment : Although the absolute confidence interval remains relatively small, the relative pricing error can still be significant, motivating the use of variance reduction methods.

## Models Implemented

### Black-Scholes Analytical Pricing

Analytical pricing formula for European options under the Black-Scholes framework.

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


## Build

```bash
mkdir build
cd build
cmake ..
cmake --build .


## Running Examples

After building the project, executables are generated inside the `build/Debug/` directory.

Example:

```bash
./Debug/main_test.exe
```

Available executables:

```text
main_test.exe
bs_price_greeks_vs_spot.exe
mc_convergence.exe
mc_repeated_estimates.exe
asian_arithmetic_vs_geometric.exe
asian_monitoring_dates.exe
asian_vs_european.exe
```