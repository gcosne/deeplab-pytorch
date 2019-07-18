# DeepLab with PyTorch <!-- omit in toc --> 

This is an unofficial **PyTorch** modification of **DeepLab v2** [[1](##references)] with a **ResNet-101** backbone.

We use a model trained on **COCO-Stuff 164K** dataset [[2](##references)]. 

## Performance

Pretrained model is provided here: 

## Setup

### Requirements

* Python 2.7+/3.6+
* Anaconda environement

Then setup from `conda_env.yaml`. Please modify cuda option as needed (default: `cudatoolkit=10.0`)

```console
$ conda env create -f configs/conda_env.yaml
$ conda activate deeplab-pytorch
```

### Datasets

Setup instruction is provided in each link.

* [COCO-Stuff 10k/164k](data/datasets/cocostuff/README.md)


### Single image

```
Usage: demo.py single [OPTIONS]

  Inference from a single image

Options:
  -c, --config-path FILENAME  Dataset configuration file in YAML  [required]
  -m, --model-path PATH       PyTorch model to be loaded  [required]
  -i, --image-path PATH       Image to be processed  [required]
  --cuda / --cpu              Enable CUDA if available [default: --cuda]
  --crf                       CRF post-processing  [default: False]
  --help                      Show this message and exit.
```

### Several images

```
Usage: demo.py test [OPTIONS]

  Inference from a single folder

Options:
  -c, --config-path FILENAME  Dataset configuration file in YAML  [required]
  -m, --model-path PATH       PyTorch model to be loaded  [required]
  -i, --folder-path PATH      Folder of images to be processed  [required]
  -o, --output-path PATH      Folder to store results [required]
  --cuda / --cpu              Enable CUDA if available [default: --cuda]
  --crf                       CRF post-processing  [default: False]
  --help                      Show this message and exit.
```


## References

1. L.-C. Chen, G. Papandreou, I. Kokkinos, K. Murphy, A. L. Yuille. DeepLab: Semantic Image
Segmentation with Deep Convolutional Nets, Atrous Convolution, and Fully Connected CRFs. *IEEE TPAMI*,
2018.<br>
[Project](http://liangchiehchen.com/projects/DeepLab.html) /
[Code](https://bitbucket.org/aquariusjay/deeplab-public-ver2) / [arXiv
paper](https://arxiv.org/abs/1606.00915)

2. H. Caesar, J. Uijlings, V. Ferrari. COCO-Stuff: Thing and Stuff Classes in Context. In *CVPR*, 2018.<br>
[Project](https://github.com/nightrome/cocostuff) / [arXiv paper](https://arxiv.org/abs/1612.03716)

1. M. Everingham, L. Van Gool, C. K. I. Williams, J. Winn, A. Zisserman. The PASCAL Visual Object
Classes (VOC) Challenge. *IJCV*, 2010.<br>
[Project](http://host.robots.ox.ac.uk/pascal/VOC) /
[Paper](http://host.robots.ox.ac.uk/pascal/VOC/pubs/everingham10.pdf)
