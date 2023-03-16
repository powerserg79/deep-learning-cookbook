# Setup on mac silicon

## Create conda environment

```bash
CONDA_SUBDIR=osx-arm64 conda create -n deep-learning-cookbook python=3.9
conda activate deep-learning-cookbook
conda env config vars set CONDA_SUBDIR=osx-arm64

# reactivate the environment after setting the CONDA_SUBDIR
conda deactivate
conda activate deep-learning-cookbook

```
## Install dependencies

Install rust for transformers

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
````

now install the dependencies

```bash
brew install cmake
brew install pkgconfig
brew install gdal
brew install postgresql@14
# pip install --no-cache-dir sentencepiece
```

## Install Tensorflow

```bash
conda install -c apple tensorflow-deps
pip install tensorflow-macos
pip install tensorflow-metal
```

## Install pytorch

[visit pytorch website](https://pytorch.org/get-started/locally/) and get the right command for your system.

eg. for macos at the time of writing

```bash
conda install pytorch torchvision torchaudio -c pytorch
```

## Finally install requirements

```bash
pip install -r requirements.txt
```

## Setup Jupiter notebook support

```bash"
conda install ipykernel
python -m ipykernel install --user --name deep-learning-cookbook --display-name "deep-learning-cookbook"
```
