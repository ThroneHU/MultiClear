# MultiClear
# [MultiClear: Multimodal Soft Exoskeletal Glove for Transparent Object Grasping Assistance](https://github.com/ThroneHU/MultiClear)
---
## C. Hu, T. Neate, L. Gionfrida 
---
This project is an oral presentation at BioRob2024. <br>

[(Project Page)](https://sites.google.com/view/tyronehu/research/multiclear) [(PDF)](https://sites.google.com/view/tyronehu/research/multiclear) [(Slides)](https://sites.google.com/view/tyronehu/research/multiclear) [(Video)](https://sites.google.com/view/tyronehu/research/multiclear)

![image](https://github.com/ThroneHU/MultiClear/tree/main/figs/fig_overview.svg)

### Abstract

Grasping is a fundamental skill for interacting with and manipulating objects in the environment. However, this ability can be difficult for some (e.g. due to disability). Wearable robotic systems that support grasping can enhance or restore essential hand functions, but grasping transparent objects remains a significant challenge. This paper introduces MultiClear, a multimodal framework proposed to improve the accuracy, stability, and efficiency of grasping transparent objects by fusing visual, tactile, and auditory modalities. We design an actuator that integrates a soft exoskeletal glove with an RGB-D camera, force-sensitive resistors, and a microphone. Through the implementation of a Middle Layer, the framework enables precise and adaptive low-level proportional-integral-derivative control, guided by high-level contextual awareness. To address the difficulty of segmenting transparent objects, we leverage a vision foundation model for zero-shot segmentation. The proposed exoskeletal glove achieves a state-of-the-art Grasping Ability Score (GAS) of 70.37±14\% and has received positive feedback from users.

### Installation

1. Install requirements:
```python
pip3 install -r requirements.txt
```

2. Clone the repository using the command:
```python
git clone https://github.com/ehsanik/touchTorch
cd touchTorch
```

### PointNet++

1. Download the PointNet++ from [here](https://github.com/charlesq34/pointnet2).

2. Move the train and Inference scripts to the solver directory.

### Data Preparation

1. Annotate point cloud data using *semantic-segmentation-editor* and collect **.pcd* labels.

2. Generate **.npy* data for `train/val/` by modifying mode.
```python
cd utils
python collect_biorob_3data.py --mode train
```

Processed data will be saved in `datasets/sub_ycb/train`.

### Run
```python
python train_complex.py
python test_e2e.py
```

### Reference By
[yanx27/Pointnet_Pointnet2_pytorch](https://github.com/yanx27/Pointnet_Pointnet2_pytorch)

### Citation

If you find this project useful in your research, please consider citing:
```
@article{hu2024pointgrasp,
  title={PointGrasp: Point Cloud-based Grasping for Tendon-driven Soft Robotic Glove Applications},
  author={Hu, Chen and Lyu, Shirui and Rho, Eojin and Kim, Daekyum and Luo, Shan and Gionfrida, Letizia},
  journal={arXiv preprint arXiv:2403.12631},
  year={2024}
}
```
