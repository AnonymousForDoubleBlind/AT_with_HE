# Boosting Adversarial Training with Hypersphere Embedding (submitted to ICML 2020)

This repository contains the code for *Boosting Adversarial Training with Hypersphere Embedding*.

## Introduction
To ensure that our experiments perform fair comparison with previous work, we adopt the public codes and make minimal modifications on them to run the trials.

### CIFAR-10
We refer to the codes of [TRADES](https://github.com/yaodongyu/TRADES).

### Adversarial Training 

* Train PGD-AT:
```
python train_trades_cifar10.py --loss=pgd
```

### Adversarial Training with Hypersphere-Embedding
* Train PGD-AT-HE:
```
python train_adv_cifar10.py --loss=pgd_he --s=15.0 --m=0.2
```

* Train TRADES-HE:
```
python train_adv_cifar10.py --loss=trades_he --beta=6.0 --s=15.0 --m=0.2
```

* Train ALP-HE:
```
python train_adv_cifar10.py --loss=alp_he --beta=0.5 --s=20.0 --m=0.3
```

### Robustness Evaluation:

* Evaluate the model on CIFAR10 by PGD-20 attack
```
  $ python pgd_attack_cifar10.py
```

* Evaluate the model on CIFAR-10-C by general attack

  Download the dataset [CIFAR-10-C](https://zenodo.org/record/2535967).
```
  $ python general_attack_cifar10.py
```