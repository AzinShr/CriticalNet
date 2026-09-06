# Emergent Criticality in Adaptive Networks

Detecting phase transitions in coupled oscillator systems on complex networks using deep learning and interpretability methods.

## Overview

This project simulates the Kuramoto model of coupled oscillators on Barabási–Albert scale-free graphs and asks a simple question: can a neural network learn to recognize when a network is near its critical coupling point; the transition between incoherent and synchronized dynamics, directly from oscillator time series?

A 1D convolutional neural network is trained to classify network states as critical or non-critical, and SHAP (SHapley Additive exPlanations) is used to interpret which features of the dynamics drive the classifier's decisions.

This work sits at the intersection of statistical physics, network science, and machine learning interpretability.

## Method

1. **Network generation** — Barabási–Albert scale-free graphs are generated as the underlying topology for oscillator coupling.
2. **Dynamics simulation** — The Kuramoto model is simulated across a range of coupling strengths K to produce oscillator phase time series.
3. **Critical point identification** — The critical coupling constant K_c is identified empirically from order-parameter behavior across the simulated range.
4. **Classification** — A 1D-CNN (PyTorch) is trained to distinguish critical from non-critical regimes from raw or derived time-series features.
5. **Interpretability** — SHAP is applied to the trained classifier to identify which input features contribute most to critical-state detection. (Note: due to MaxPool1d hook conflicts with the standard SHAP DeepExplainer, KernelExplainer was used instead.)

## Key Results

- Empirically determined critical coupling K_c
- Classifier performance: 
- SHAP analysis revealed 


## What This Demonstrates

- Numerical simulation of nonlinear dynamical systems on complex network topologies
- Deep learning applied to physical time-series classification (PyTorch)
- Model interpretability techniques (SHAP) for extracting physical insight from black-box classifiers
- End-to-end pipeline design: simulation → labeling → training → interpretation

