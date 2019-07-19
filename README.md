## Introduction

**PC-DARTS** is a new developed memory-efficient differentiable architecture method based on **DARTS**. It mainly focuses on the large memory cost of the super-net in one-shot NAS method, which means that it can also be combined with other one-shot NAS method e.g. **ENAS**. Different from previous methods that sampling operations, PC-DARTS samples channel of the constructed super-net. For a detailed description of technical details and experimental results, please refer to our paper:

[Partial Channel Connections for Memory-Efficient Differentiable Architecture Search](https://arxiv.org/pdf/1907.05737.pdf)

[Yuhui Xu](http://yuhuixu1993.github.io), [Lingxi Xie](http://lingxixie.com/), [Xiaopeng Zhang](https://sites.google.com/site/zxphistory/), Xin Chen, [Gu-Jun Qi](http://www.eecs.ucf.edu/~gqi/), [Qi Tian](https://scholar.google.com/citations?user=61b6eYkAAAAJ&hl=zh-CN) and Hongkai Xiong.

**This code is based on the implementation of  [DARTS](https://github.com/quark0/darts).**

**Searched on ImageNet, we achieved currently one of, if not only, the best performance on ImageNet (24.2%/7.3%) under the mobile setting!**

**The search process in CIFAR10 only requires 0.1 GPU-days, *i.e.*, ~3 hours on one Nvidia 1080ti.(1.5 hours on one Tesla V100)**

## Usage

To run our code, you only need one Nvidia 1080ti , and equip it with PyTorch 0.3.1 (python2). (Tesla V100 will be faster).
```
python train_search.py \\
```
You can search on ImageNet by using model_search_imagenet.py! The training file for search on ImageNet will be uploaded after it is cleaned or you can generate it according to the train_search file on CIFAR10 and the evluate file on ImageNet. Hyperparameters are reported in our paper!

#### The evaluation process simply follows that of DARTS.

###### Here is the evaluation on CIFAR10/100:

```
python train_cifar.py \\
       --auxiliary \\
       --cutout \\
```

###### Here is the evaluation on ImageNet (mobile setting):
```
python train_imagenet.py \\
       --tmp_data_dir /path/to/your/data \\
       --save log_path \\
       --auxiliary \\
       --note note_of_this_run
```
We will provide pre-trained models of the discovered architecture on CIFAR10 and ImageNet soon!.

## Results
#### Results on CIFAR10

#### Results on ImageNet

## Reference

If you use our code in your research, please cite our paper accordingly.
```Latex
@article{xu2019pcdarts,
  title={Partial Channel Connections for Memory-Efficient Differentiable Architecture Search},
  author={Xu, Yuhui and Xie, Lingxi and Zhang, Xiaopeng and Chen, Xin and Qi, Guo-Jun and Tian, Qi and Xiong, Hongkai},
  journal={arXiv preprint arXiv:1907.05737},
  year={2019}
}
