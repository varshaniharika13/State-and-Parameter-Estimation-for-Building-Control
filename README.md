# Bayesian State and Parameter Estimation for Building Thermal Models

##  Overview

This project explores **state and parameter estimation** techniques for building thermal dynamics using a combination of **Bayesian filters/smoothers** and **optimization methods**. We focus on grey-box modeling of a residential building’s thermal behavior via RC-network ODE models and develop a modular Python package to support Model Predictive Control (MPC).

The implementation includes:
- Kalman Filter-Smoother (KFS)
- Extended Kalman Filter-Smoother (EKFS)
- Unscented Kalman Filter-Smoother (UKFS)
- Gaussian Filter-Smoother (GFS)

Parameter estimation techniques:
- State Augmentation via Bayesian Filtering
- Least Squares Estimation (LSE)
- Batch Estimation (MAP-based)
- Maximum Likelihood Estimation (MLE)

>  The package is designed to be modular and extensible for use with both simulated and real building data.

---

##  Motivation

According to the US Energy Information Administration (EIA), buildings account for ~40% of total electricity consumption. There is a growing need to:
- Reduce energy use
- Improve occupant comfort
- Provide grid support via ancillary services

To achieve these, we rely on advanced control strategies like **Model Predictive Control (MPC)**, which depend heavily on accurate **state** and **parameter estimation**. This project addresses this need by developing robust estimation techniques for thermal models.

---

##  Project Structure

### Models
- **1-State, 2-State, and 4-State RC Thermal Models** for a single-family house.
- Models are based on differential equations (ODEs) and discretized using the Euler method.

### Algorithms
- **Bayesian State Estimation:** via Kalman and Nonlinear Bayesian filters with state augmentation.
- **Parameter Estimation Techniques:**
  - **Bayesian Filtering (with artificial process noise)**
  - **Nonlinear Least Squares Optimization**
  - **Batch Estimation (MAP Formulation)**
  - **Maximum Likelihood Estimation (MLE)**

### Visualization
- Code includes plotting tools to compare estimated vs true values of state and parameters for systems such as:
  - Simple pendulum (used as benchmark)
  - Building temperature dynamics (planned)

---
##  Files Included

- **Report**: Detailed documentation of the methodology, equations, thermal models (1-, 2-, and 4-state), parameter estimation techniques, and results from simulation tests.
- **Code**: Python implementations of:
  - Bayesian Filters and Smoothers (KFS, EKF, UKF, GFS)
  - Parameter Estimation Techniques (State Augmentation, LS, Batch Estimation, MLE)
  - Building Thermal Models and Pendulum Benchmark System
- **Figures/Results**: Includes plots for state and parameter estimations across different methods (available in `results/` folder).
- **Models**: Modular ODE-based RC network models for single-family homes.

---

## 🔍 Key Insights

- **Grey-box modeling** using RC networks effectively captures thermal dynamics while remaining interpretable and simulation-efficient.
- **State Augmentation with Bayesian Filters** enables joint state-parameter estimation in nonlinear systems with limited data.
- **UKF and EKF** show robustness in estimating both dynamic and static parameters in benchmark systems like the pendulum.
- **MLE and Batch Estimation** provide optimization-based formulations that improve parameter accuracy using measurement uncertainty.
- The **accuracy of thermal model-based MPC** heavily depends on the correctness of the parameter estimation process.
- Euler discretization, while simple, provides sufficiently accurate results for control applications when using small time steps.

---

## 💡 Future Work

-  Implement and validate algorithms on **EnergyPlus/Modelica-generated** or real-world building datasets.
-  Explore **Particle Filters and Expectation Maximization** for improved non-Gaussian or multimodal estimation.
-  Extend framework to **online learning** of parameters in time-varying environments (e.g., weather changes, occupancy shifts).
-  Incorporate **multi-zone thermal models** for more complex buildings.
-  Develop **adaptive control-ready versions** of estimation pipelines for direct MPC integration.
-  Perform **robustness testing under sensor noise, missing data**, and model mismatches.
