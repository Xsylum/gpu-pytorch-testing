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

With the environment active, the pip packages will now install to the conda packages directory, which [can be changed](https://docs.conda.io/projects/conda/en/latest/user-guide/configuration/custom-env-and-pkg-locations.html) much more easily.
```
pip3 install torch torchvision
```


