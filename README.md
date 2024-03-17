# TARNet / Counterfactual Regression Model for Causal Inference
![GitHub last commit](https://img.shields.io/github/last-commit/elliothha/causal-inference-tarnet) ![GitHub repo size](https://img.shields.io/github/repo-size/elliothha/causal-inference-tarnet)

*[3/16/24 Update] Uploaded notebook for TARNet*

This repo contains a PyTorch implementation of a TARNet / Counterfactual Regression model for causal inference on Causal Forge's "Infant Health and Development Program (IHDP)" dataset.

I wrote all of my thoughts on the whole workflow/architecture inside comment blocks in the Notebook file. If interested, please see `models/tarnet.ipynb`.

by **Elliot H Ha**. Duke University

[elliothha.tech](https://elliothha.tech/) | [elliot.ha@duke.edu](mailto:elliot.ha@duke.edu)

---

## Dependencies
- Jupyter Notebook
- PyTorch

## Project Structure
`models/` is the main folder containing the Jupyter Notebook file implementing the TARNet model for the IHDP dataset. It also contains the training and testing dataset files used.

## Hyperparameters & Architecture
```
lr = 1e-3
num_epochs = 30
batch_size = 32

input_dim = 25
hidden_dim = 100

alpha = 1
```

I use [Adam](https://pytorch.org/docs/stable/generated/torch.optim.Adam.html) as my optimizer with a learning rate, `lr = 1e-3`, default betas and epsilon, and 0 weight decay. 

The `input_dim` hyperparameter represents the feature dimension for the covariates. In the case of the IHDP dataset, we have 25 covariates.

The `hidden_dim` hyperparameter represents the dimensionality of hidden layers used in the representation and hypothesis networks.

Training is run for `num_epochs = 30` epochs with a `batch_size = 200`.

## Results
![Inferences](/examples/inferences.png)

---

## References
1. *Estimating individual treatment effect: generalization bounds and algorithms*, Shalit et al. 2016 | [1606.03976](https://arxiv.org/abs/1606.03976)
2. Dr. Fredrik D. Johansson's website | [link](https://www.fredjo.com/)
3. Causal Forge's documentation | [link](https://causalforge.readthedocs.io/en/latest/user_guide/Loading_Causal_RW_Benchmarking_Datasets.html)
4. Causal Forge's GitHub | [link](https://github.com/anthem-ai/causalforge/tree/main)

The research paper is genuinely really well-written and digestible even with no prior knowledge on causal inference. Highly recommend! 
