+++
title = "Setup"
subtitle = "One environment, one kernel, one data file. About twenty minutes, most of it unattended."
+++

Everything in this workshop runs on your own laptop, without a GPU. You install one
environment, register it as one Jupyter kernel, and download one data file. Please do
this before the workshop, because the conference wifi will not handle everyone
downloading at once.

Each step ends with a check you can run.

<!--more-->

You need about 5 GB of free disk space and at least 8 GB of RAM (16 GB is better).

## Step 1: get the workshop materials

The notebooks and the environment files are in the
[materials repository](https://github.com/scverse/202611_workshop_SBI2).

With git:

```
git clone https://github.com/scverse/202611_workshop_SBI2.git
cd 202611_workshop_SBI2
```

Without git, open the [repository](https://github.com/scverse/202611_workshop_SBI2) in
your browser, click the green **Code** button, choose **Download ZIP**, unzip it, and open
a terminal in that folder.

You are in the right place if you can see `environment.yml`, `pixi.toml` and a
`notebooks` folder.

## Step 2: create the environment

Pick one of the two ways.

**With pixi** (recommended, no conda needed). Install pixi from
[pixi.sh](https://pixi.sh), then run:

```
pixi run lab
```

This installs the environment, registers the `scverse-sbi2` kernel and starts
JupyterLab.

**With conda.** If you already have a working conda (Anaconda, Miniconda or Miniforge):

```
conda env create -f environment.yml
conda activate scverse-sbi2
python -m ipykernel install --user --name scverse-sbi2
```

### Check

```
python -c "import anndata, annbatch, mantispy, scanpy, torch; print('setup ok')"
```

With pixi, run it as `pixi run python -c "..."`. If it prints `setup ok`, the software
side is done. If it prints an error, copy the whole message and post it on
[Zulip](https://scverse.zulipchat.com/) with your operating system.

## Step 3: download the data

The notebooks download the data themselves, but please do it in advance on a connection
you trust:

- [workshop_small.h5ad](https://exampledata.scverse.org/sbi2-cytodata/workshop/workshop_small.h5ad), 496 MB

Put it into `notebooks/data/`. The notebooks check the file and skip the download if it
is already there.

The full dataset (98,345 cells, 4.2 GB) and its pre-shuffled annbatch version (4.9 GB)
are optional, for the last part of the workshop and for trying things at home. The
[materials repository](https://github.com/scverse/202611_workshop_SBI2) lists them.

## Starting Jupyter

```
pixi run lab
```

or, with conda:

```
conda activate scverse-sbi2
jupyter lab
```

Open a notebook and check the top right corner. It has to say **scverse-sbi2**. If it
says something else, click it and pick *scverse-sbi2*.

## Troubleshooting

**Jupyter starts but the kernel is missing.** With conda, check that the last command in
step 2 ran while `scverse-sbi2` was active. `jupyter kernelspec list` shows the kernels
Jupyter knows about.

**The download fails with "403 Forbidden".** Download the file with your browser, `curl`
or `wget` and put it into `notebooks/data/`.

**Anything else.** Post it on [Zulip](https://scverse.zulipchat.com/) with your operating
system, what you ran, and the full error text.
