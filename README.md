# gpu-pytorch-testing
This repo was created for personal use in following [pytorch's quickstart tutorial](https://pytorch.org/tutorials/beginner/basics/quickstart_tutorial.html).

## Downloading the PyTorch (and related) Packages
I ran my tests on a Linux-based machine, but Mac and Windows instructions are also available on PyTorch's [Start Locally page](https://pytorch.org/get-started/locally/).

For my machine, the CUDA 12.4 build was ideal, and I installed it using Pip (to download pip see [here](pip3 install torch torchvision torchaudio)).

On my machine, I was running into issues with lack of storage space for the pip packages. To get around this, I created a [Conda](https://github.com/conda-forge/miniforge) environment to run pip within using:
```
conda create -p ./pytorch_environment
```

Then, after pressing `y` or Enter through the prompts, activate the environment using
```
conda activate ./pytorch_environment
```
To deactivate the environment you can use `conda deactivate`, but bear in mind the environment will need to be active when installing/using packages (it will need to be activated again if your terminal closes!)

I was having issues installing the packages via Pip due to storage space, even with conda managing the downloads. While PyTorch no longer maintains an [Anaconda channel](https://github.com/pytorch/pytorch/issues/138506), but thankfully they do maintain a conda-forge package available [here](https://anaconda.org/conda-forge/pytorch). Pulling from the conda forge package can be done (while your conda environment is active):
```
conda install conda-forge::pytorch conda-forge::torchvision
```

Again, press `y` and Enter to any prompts during installation. Once the packages are installed, you are ready to run the scripts!

## Running PyTorch offline
If you are using an offline-computing platform for training/testing the AI (like a segmented HPC for instance), you'll need to pull the dataset ([FashionMNIST](https://pytorch.org/vision/stable/generated/torchvision.datasets.FashionMNIST.html)) from an internet-connected node first.

In the top directory of the repo, run the provided download script for the dataset using:
```
python3 scripts/DownloadFashionTrainingData.py
```
After this, a new directory called "data" will have appeared in the top directory of the repo, which will house all the data we'll be using for testing/training

## Executing PyTorch Testing/Training

You'll want to run `mkdir models` so that the scripts below have a place to save the newly-trained model
