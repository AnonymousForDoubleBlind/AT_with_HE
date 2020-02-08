## Description

Our experiments on ImageNet implement the FreeAT and FreeAT frameworks, where the codes are mainly forked from the [free adversarial training repository](https://github.com/mahyarnajibi/FreeAdversarialTraining), with the corresponding modifications with HE.

## Training codes

### FreeAT

Following the [FreeAT paper](https://arxiv.org/abs/1904.12843) by Shafahi et al. (2019), the command for training models with the FreeAT is
```shell
python main_free.py /data/ImageNet
```
The default training settings are included in the `configs.yml` file, where the model is `resnet50`, initial learning rate of momentum SGD is `0.1`, the maximal perturbation is `4/255` with step size of `1/255`, the batch size is `256`.

### FreeAT + HE

The training command for FreeAT + HE (our method) is
```shell
python main_free.py /data/ImageNet --FN True --WN True --s_HE 10.0 --angular_margin_HE 0.2
```
Here we activate the `FN` and `WN` operations, and set the scale `s=10.0` and margin `m=0.2`. These flags can be changed to perform, e.g., ablations studies on the effect of each component in HE.

## Evaluation codes
