# Calibrated Heston-type LSV Model - Strong Propagation of Chaos Experiments

This repository contains Python code that simulates a **calibrated Heston-type Local Stochastic Volatility (LSV) model** and studies the **strong propagation of chaos** phenomenon.

## Overview

The code simulates a **calibrated Heston-type Local Stochastic Volatility (LSV) model**, where the squared volatility process follows **Cox–Ingersoll–Ross (CIR) dynamics**. To approximate the conditional expectation, it uses the **Nadaraya–Watson kernel estimator**.

Instead of relying on real market data, the code generates a synthetic **market implied volatility surface** using **already calibrated Heston parameters** obtained from an FX market. From this, a **Dupire local volatility surface** is generated and extended via **bicubic interpolation and extrapolation**.

The implementation uses **QuantLib**, an open-source library for quantitative finance, for model construction (Heston), curve setup, pricing engines, path generation, and building both implied and local volatility surfaces.

The main goal is to investigate **strong propagation of chaos** by simulating large interacting particle systems and analysing convergence rates under different sets of model parameters.


## Features

- Artificial market surface from calibrated Heston parameters
- Dupire local volatility surface generation
- Euler-Maruyama scheme for stock price process
- Full truncation Euler scheme for variance positivity
- Nadaraya-Watson kernel regression to approximate conditional expectation
- Strong propagation of chaos experiments

## Requirements

- Python 3.9+
- numpy
- pandas
- matplotlib
- scipy
- seaborn
- scikit-learn
- QuantLib

Install dependencies with:
pip install -r requirements.txt

## Usage

Run the simulation:
python strong_propagation_of_chaos.py

You can also import the functions into another Python script:
from strong_propagation_of_chaos import run_experiment
results = run_experiment(do_plot=True)

## Output

- Local volatility surface plots
- Implied volatility surface plots
- Plots of "market prices" over strikes for fixed maturity
- Plots illustrating the strong propagation of chaos (i.e. convergence of the particle system as the number of particles increases)

## License

This project is licensed under the MIT License – see the LICENSE file for details.
