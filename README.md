# Seoul Weather Prediction Using Markov Chains

A stochastic-processes project that models day-to-day weather transitions in Seoul, South Korea as a discrete-time Markov chain, then analyzes its long-run behavior — stationary distribution, irreducibility, periodicity, and mean return times.

## Description

This project treats daily weather conditions (clear-day, partly-cloudy-day, rain, snow, cloudy) as the states of a Markov chain, using two years of historical Seoul weather data (Jan 1, 2022 – Jan 1, 2024) from Kaggle's *Seoul Historical Weather Data (2024)* dataset.

The notebook walks through:

- **Data preparation** — loading and cleaning the dataset, encoding weather conditions as discrete states.
- **Transition matrix estimation** — building the empirical one-step transition probability matrix `P` from observed day-to-day transitions, and verifying it is a valid stochastic matrix.
- **Visualization** — daily weather sequences over time, a transition probability heatmap, and a directed transition graph.
- **Multi-step behavior** — computing `P²`, `P¹⁰`, and `P¹⁰⁰` to see how transition probabilities evolve over multiple days.
- **Chain properties** — checking for absorbing states, equivalence (communication) classes, irreducibility, and aperiodicity.
- **Long-run analysis** — computing the stationary/limiting distribution, the limiting matrix, simulating long trajectories to confirm convergence, and calculating the mean return time (in days) for each weather state.

The result is a simple but complete probabilistic model of Seoul's weather dynamics, along with an interpretation of what the long-term weather "steady state" looks like.

## Contents

- `Weather_Prediction_Using_Markov_Chain.ipynb` — main Jupyter notebook with all analysis, code, and explanations.
- `seoul 2022-01-01 to 2024-01-01.csv` — historical weather dataset (from Kaggle).



## Key Results

- The chain is **irreducible** and **aperiodic**, so it converges to a unique stationary distribution.
- Long-run weather probabilities: **partly-cloudy-day ≈ 42.7%**, **rain ≈ 34.7%**, **clear-day ≈ 16.0%**, **snow ≈ 5.5%**, **cloudy ≈ 1.1%**.
- Mean return times range from about **2.3 days** (partly-cloudy-day) to about **91 days** (cloudy).
