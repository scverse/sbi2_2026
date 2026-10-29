+++
title = "scverse x SBI2 2026"
description = "A two-hour hands-on workshop on deep learning on single-cell morphology data with the scverse ecosystem. SBI2 2026, Boston, Monday 2 November, 13:00 to 15:00, Salon F."
images = ["img/hero/scverse_symbol.png"]
+++

This workshop shows how to work with single-cell morphology data from Cell Painting
screens in the [scverse](https://scverse.org) ecosystem, and how to train and use deep
learning models on it. We use single cells from the JUMP Cell Painting TARGET2 plates,
with features measured by cp_measure and image crops of every cell, all stored together
in one AnnData object.

The workshop pairs short introductions with hands-on notebooks. Models that take hours to
train were trained in advance, so every step runs on a laptop in a few minutes.

### What you will take away

- How to store per-cell features, images and embeddings of a screen in AnnData, and why a
  single-cell table is the starting point for deep learning.
- How to train a model on AnnData with annbatch, in memory on a laptop and streamed from
  disk for millions of cells.
- How to run a pretrained image model (OpenPhenom) on single-cell crops, and how a
  fine-tuned model compares.
- How to judge a representation by how well it separates compounds from controls, and
  why too few controls make hand-designed features call inactive compounds active.

**Bring your own laptop.** Everything runs locally. Please follow the
[setup instructions](setup/) before the workshop, including the data download.
