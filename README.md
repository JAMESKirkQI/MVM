![Python 3.8](https://img.shields.io/badge/python-3.8-green.svg)

# Contrastive Semi-supervised Continual Learning via Graph Diffusion Consistency

---

[//]: # (<font size="10"><b><center>Contrastive Semi-supervised Continual Learning via Graph Diffusion Consistency</center></b></font>)

This repository is the PyTorch source code implementation of 
[Contrastive Semi-supervised Continual Learning via Graph Diffusion Consistency](). This is a demo code to illustrate the basic motivation 
for fast training and evaluating the MVDC model.

<div align="center">
<img src="./img/illustrate.svg" width=85% />
</div>
We propose a View-Individual Description Codebook (VIDC) module for Multi-View Diffusion Codebook (MVDC), a plug-and-play solution to sustain and absorb new information continually. Serving as a memory bank, the VIDC can be tuned by observing the correlations within an expansive pool of unlabeled data, inferred via label propagation, circumventing the need for costly annotations. Considering the VIDC module's intrinsic limitation in ensuring cross-view Graph Diffusion Consistency(GDC), we generate the final consensus graph by diffusing the similarity matrix in all views.

## Usage

---

### Requirements

We use single RTX A6000 48G GPU for training and evaluation. Refer to `hardware.txt` for hardware related parameters.
To install a working environment run:

```
pip install -r requirements.txt
```

Please log in to your own wandb key in advance to record experimental results.

```
wandb.login(key="your wandb key")
```

### Prepare Datasets

You can download the data in
[Google Drive](https://drive.google.com/file/d/1Is9GeVAe9vy1l5xg7Xqwa9lXAYRm3PMu/view?usp=sharing)
and put the downloading file to the root path of the project to evaluate our method.
Organize the file in root dir folder as follows:

```
├── argpaser.py                           # Hyperparameters
├── featureloader.py                      # Dataloader
├── hardware.txt                          
├── learner.py                            # Train and Test
├── loss.py                               # Loss function
├── main.py                               
├── projector.py                          # Neural network architectures
├── requirements.txt                      
├── view_reliability.py                   
└── xy_tensor_uiuc.pt                     # Data
```

### Demo validation

```
python main.py
```

Thanks for your effort and time to review our paper.
