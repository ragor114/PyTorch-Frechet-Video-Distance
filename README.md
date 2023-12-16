# Fréchet Video Distance 
This repository contains an easy to use implementation of the [Fréchet Video Distance](https://openreview.net/pdf?id=rylgEULtdN) (FVD) metric, developed by Unterthiner et al., for PyTorch. The implementation is largely based on the [StyleGAN-V repository](https://github.com/universome/stylegan-v) but was modified to work with two Tensors representing sets of videos.

## Usage
To use the FVD metric copy the `fvd_metric` folder to your project. Then, import the metric using `from fvd_metric import compute_fvd`.

Afterwards, you can use the `compute_fvd` function. Here is an example:
```python
fvd = compute_fvd(y_true, y_pred, num_samples, device, batch_size=4)
```

`y_true` and `y_pred` should have the same shape and the shape should be `num_videos x channels x num_frames x width x height`.

As computing the FVD metric for a large number of videos can be expensice, the `num_samples` parameter can be used to calculte the FVD on a subset.

## Citation
If used please cite the original publication and the StyleGAN-V paper
```
@misc{
unterthiner2019fvd,
title={{FVD}: A new Metric for Video Generation},
author={Thomas Unterthiner and Sjoerd van Steenkiste and Karol Kurach and Rapha{\"e}l Marinier and Marcin Michalski and Sylvain Gelly},
year={2019},
url={https://openreview.net/forum?id=rylgEULtdN}
}

@misc{stylegan_v,
    title={StyleGAN-V: A Continuous Video Generator with the Price, Image Quality and Perks of StyleGAN2},
    author={Ivan Skorokhodov and Sergey Tulyakov and Mohamed Elhoseiny},
    journal={arXiv preprint arXiv:2112.14683},
    year={2021}
}

@inproceedings{digan,
    title={Generating Videos with Dynamics-aware Implicit Generative Adversarial Networks},
    author={Sihyun Yu and Jihoon Tack and Sangwoo Mo and Hyunsu Kim and Junho Kim and Jung-Woo Ha and Jinwoo Shin},
    booktitle={International Conference on Learning Representations},
    year={2022},
    url={https://openreview.net/forum?id=Czsdv-S4-w9}
}
```
