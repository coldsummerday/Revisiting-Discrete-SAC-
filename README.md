# Revisiting Discrete Soft Actor-Critic (SD-SAC)
[![OpenReview](https://img.shields.io/badge/OpenReview-TMLR-blue.svg)](https://openreview.net/forum?id=EUF2R6VBeU) 
[![Arxiv](https://img.shields.io/badge/arXiv-2209.10081-red)](https://arxiv.org/pdf/2209.10081.pdf)
[![GitHub Stars](https://img.shields.io/github/stars/coldsummerday/SD-SAC?style=social)](https://github.com/coldsummerday/SD-SAC/stargazers)

This repository provides the official PyTorch implementation of the paper:[**Revisiting Discrete Soft Actor-Critic**](https://openreview.net/forum?id=EUF2R6VBeU) 



## Requirements
- python: 3.6+
- gym>=0.23.1
- torch>=1.4.0
- numba>=0.51.0
- tensorboard>=2.5.0
- atari_py
- tqdm

## Installation
The code requires some dependencies as specified in `requirements.txt`. Please follow the relevant libraries to install or run: 

`pip install -r requirements.txt`

## Doc
```
.
├── README.md
├── requirements.txt
└── src
    ├── examples
    │   └── atari
    │       ├── atari_network.py
    │       ├── atari_sac.py ##main program
    │       ├── atari_wrapper.py
    ├── libs ## modify tianshou code for discrete SAC alternative design 
    │    
    └── tianshou ##tianshou  library code,version 0.4.9

```


## Usage

1. run base discrete SAC for Pong  10m steps
```
cd src
python3 examples/atari/atari_sac.py --task PongNoFrameskip-v4 --epoch 200  --step-per-epoch 50000
```

2. run  discrete SAC with entropy-penalty for Pong  10m steps
```shell
cd src
python3 examples/atari/atari_sac.py --entropy-penalty --task PongNoFrameskip-v4 --epoch 200  --step-per-epoch 50000
```
3.run  discrete SAC with double avg q for Pong  10m steps
```shell
cd src
python3 examples/atari/atari_sac.py --avg-q --clip-q  --task PongNoFrameskip-v4  --epoch 200  --step-per-epoch 50000
```

4. run SD-SAC for for Pong  10m steps
```shell
cd src
python3 examples/atari/atari_sac.py --avg-q --clip-q --entropy-penalty --task PongNoFrameskip-v4  --epoch 200  --step-per-epoch 50000
```


## Acknowledgement

This repo is based on the open-source codebase of [tianshou](https://github.com/thu-ml/tianshou). Thanks for their impressive works!

## Citation
If you find this work useful for your research, please cite [our paper](https://openreview.net/forum?id=EUF2R6VBeU):
<pre>
@article{
zhou2024revisiting,
title={Revisiting Discrete Soft Actor-Critic},
author={haibin zhou and Tong Wei and Zichuan Lin and junyou li and Junliang Xing and Yuanchun Shi and Li Shen and Chao Yu and Deheng Ye},
journal={Transactions on Machine Learning Research},
issn={2835-8856},
year={2024},
url={https://openreview.net/forum?id=EUF2R6VBeU},
note={}
}
</pre>
