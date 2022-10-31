# [Moreh] Running clear-diffusion-keras on Moreh AI Framework
![](https://badgen.net/badge/Nvidia-A100/passed/green)

## Prepare

### Data
Dataset is automatically downloaded during running by `tensorflow_datasets` library.
Downloaded datasets are stored at `~/tensorflow_datasets`.

> Note: currently, the CelebA dataset is unavailabel for download

### Code
```bash
git clone https://github.com/loctxmoreh/clear-diffusion-keras
cd clear-diffusion-keras
```

### Environment
On A100 machine, use `a100env.yml` file to create a conda environment:
```bash
conda env create -f a100env.yml
conda activate clear-diffusion
```

## Run
First, edit `train.py` and change the following variables:
- `dataset_name`: dataset used for training. Take one of these four values:
  `caltech_birds2011`, `oxford_flowers102`, `celeb_a`, `cifar10`.
- `epochs`: number of training epochs for each dataset.
- `uncropped_image_size` & `image_size`: set to `32` for `cifar10`, `64` for the rest

Then, on A100 machine, run the training script:
```bash
./a100-train
```
