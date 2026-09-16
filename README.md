# PINN for frictional pressure drop in two-phase non-Newtonian liquid-gas flow

## Overview
This project develops a Physics-Informed Neural Network (PINN) to predict frictional 
pressure drop and flow regime(slug, stratified,annular) in non-Newtonian liquid(power law fluid)-gas two-phase flow. The model 
combines the Lockhart-Martinelli correlation with deep learning to improve prediction 
accuracy over purely empirical or purely data-driven approaches.

## Motivation
Accurate prediction of pressure drop in two-phase flow is critical for designing and 
operating industrial pipelines, especially when working with non-Newtonian fluids where 
conventional correlations often fall short. This project explores whether embedding 
physical laws (via a PINN) into a neural network improves prediction accuracy and 
generalizability compared to a standard data-driven model.

## Methodology
- **Base model:** Lockhart-Martinelli correlation for two-phase pressure drop
- **Approach:** Physics-Informed Neural Network (PINN) built in Python using PyTorch
- **Comparison model:** Standard Artificial Neural Network (ANN), trained on the same 
  dataset without physics-based constraints
- **Data:** Experimental pressure drop data compiled from published literature on 
  non-Newtonian liquid-gas two-phase flow for CMC, Xantham gum,etc

  ## What This Notebook Contains
- PINN architecture and training pipeline (PyTorch)
- ANN baseline model for comparison
- Model validation against experimental data
- Performance comparison between PINN and ANN approaches

  ## Results
- PINN performed better than ANN in overall metrics (i.e., average mean+-std(taken across all regimes and 5 seeds)
logRMSE for frictional multiplier, logRMSE two phase flow, classification accuracy)
- In regime-wise comparison, PINN performed better than ANN in slug flow, while they were comparable for stratified 
and for annular flow, both models showed high errors
- Conclusion is that including physics constraints in neural networks for pressure drop prediction is better,
  however, lack of momentum balances for gas and liquid phases resulted in errors in annular flow specifically

## Tools & Libraries
- Python
- PyTorch, Numpy, Pandas, Matplotlib, Sklearn

## Author
Preethi V — B.Tech Chemical Engineering, Rajalakshmi Engineering College
