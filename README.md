<p align="center">
  <img src="assets/icon.png" alt="SyncHuman" width="60%>
</p>

<div align="center">

# Synchronizing 2D and 3D Generative Models for Single-view Human Reconstruction

</div>

<div align="center">

[Wenyue Chen](#)<sup>1</sup>, [Peng Li](https://penghtyx.github.io/yuki-lipeng/)<sup>2</sup>, [Wangguandong Zheng](https://wangguandongzheng.github.io/)<sup>3</sup>, [Chengfeng Zhao](https://afterjourney00.github.io/)<sup>2</sup>, [Mengfei Li](#)<sup>2</sup>, [Yaolong Zhu](#)<sup>1</sup>, [Zhiyang Dou](https://frank-zy-dou.github.io/)<sup>4</sup>, [Ronggang Wang](https://scholar.google.com/citations?user=CEEvb64AAAAJ&hl)<sup>1</sup>, [Yuan Liu](https://liuyuan-pal.github.io/)<sup>2</sup>

<sup>1</sup> Peking University
<sup>2</sup> The Hong Kong University of Science and Technology 
<sup>3</sup> Southeast University
<sup>4</sup> The University of Hong Kong

</div>

>  **Official code of SyncHuman: Synchronizing 2D and 3D Generative Models for Single-view Human Reconstruction**

<div align="center">
<a href='https://arxiv.org/pdf/2510.07723'><img src='https://img.shields.io/badge/arXiv-2510.07723-b31b1b.svg'></a> &nbsp;&nbsp;&nbsp;&nbsp;
<a href='https://xishuxishu.github.io/SyncHuman.github.io/'><img src='https://img.shields.io/badge/Project-Page-Green'></a> &nbsp;&nbsp;&nbsp;&nbsp;
<a href="https://huggingface.co/xishushu/SyncHuman"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20Weights-HF-orange"></a> &nbsp;&nbsp;&nbsp;&nbsp;
</div>


## Environment Setup

We tested on H800 with CUDA 12.1. Follow the steps below to set up the environment.

### 1) Create Conda env and install PyTorch (CUDA 12.1)
```bash
conda create -n SyncHuman python=3.10
conda activate SyncHuman

# PyTorch 2.1.1 + CUDA 12.1
conda install pytorch==2.1.1 torchvision==0.16.1 torchaudio==2.1.1 pytorch-cuda=12.1 -c pytorch -c nvidia

```

### 2) Follow [trellis](https://github.com/microsoft/TRELLIS) to setup the env


### 3) Install remaining Python packages
```bash
pip install accelerate safetensors==0.4.5 diffusers==0.29.1 transformers==4.36.0
```

## Inference
```
git clone https://github.com/xishuxishu/SyncHuman.git
```
### 1) download ckpts
```
cd SyncHuman
python download.py
```
The file organization structure is shown below：


```
SyncHuman
├── ckpts
│   ├── OneStage
│   └── SecondStage
├── SyncHuman
├── examples
├── inference_OneStage.py
├── inference_SecondStage.py
└── download.py
```



### 2) run the inference code
```
python inference_OneStage.py

python inference_SecondStage.py
```

If you want to change the example image used for inference, please modify the `image_path` in `inference_OneStage.py`.

Then you will get the final generated result at `outputs/SecondStage/output.glb`.


## Ack
Our code is based on these wonderful works:
* **[TRELLIS](https://github.com/microsoft/TRELLIS)**
* **[PSHuman](https://github.com/pengHTYX/PSHuman)**



## 📚 Citation

If you find this work useful, please cite our paper:

```bibtex
@article{chen2025synchuman,
  title={SyncHuman: Synchronizing 2D and 3D Generative Models for Single-view Human Reconstruction},
  author={Chen, Wenyue and Li, Peng and Zheng, Wangguandong and Zhao, Chengfeng and Li, Mengfei and Zhu, Yaolong and Dou, Zhiyang and Wang, Ronggang and Liu, Yuan},
  journal={arXiv preprint arXiv:2510.07723},
  year={2025}
}
```
