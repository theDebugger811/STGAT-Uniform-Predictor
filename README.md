# STGAT v/s Uniform Predictor

A significant amount of the recent forecasting method evaluate their performance using only the Top-20 metric. This can be highly misleading due to a variety of reasons. First, this metric only measures model diversity: the ability of the model to cover all modes. It does not measure whether all modes are socially plausible (low collision rate for all modes). Second, it is also difficult to objectively compare methods using Top-20 because approaches that produce wildly different output samples may yield similar Top-20 values. In this repository, we show a simple uniform predictor that outputs uniformly-spaced samples (see table below) performs similar to a state-of-the-art STGAT method.

| Method | ETH | Hotel | Univ | Zara1 | Zara2 |
| ------ | ------ | ------ | ------ | ------ | ------ |
| STGAT | 0.65 / 1.12 | 0.35 / 0.66 | 0.52 / 1.10 | 0.34 / 0.60 | 0.29 / 0.60 |
| SUP | 0.64 / 1.14 | 0.25 / 0.45 | 0.51 / 1.09 | 0.40 / 0.86 | 0.29 / 0.62 |

We believe it is of utmost importance to not rely on the Top-20 metric only. We need additional multimodal metrics that measure social acceptability (like average collisions) and the likelihood of the ground truth (like negative log-likelihood) to obtain a more holistic view. Check out the [TrajNet++ challenge](https://www.aicrowd.com/challenges/trajnet-a-trajectory-forecasting-challenge) as it incorporates these new metrics for an objective evaluation.



## Requirements
* Python 3
* PyTorch (1.2)
* Matplotlib

## Datasets
All the data comes from the [SGAN](https://github.com/agrimgupta92/sgan) model without any further processing.

## How to Run
* First `cd STGAT`
* To train the model run `python train.py` (see the code to understand all the arguments that can be given to the command)
* To evaluate the STGAT model run `python evaluate_model.py`
* To evaluate the Uniform Predictor model run `python evaluate_uniform_predictor.py`

## Acknowledgments
All data and part of the code comes from the [SGAN](https://github.com/agrimgupta92/sgan) model.
