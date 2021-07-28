# earth-science-text-classification
An empirical approach to solve mutli-label text classification problem. Part of UAH RA coding task.

> DISCLAIMER: I don't like to use jupyter notebooks much except for prototyping. I have only added noteboks, as it's more convenient given the time constraint! But I have tried my best to document the notebook.

## Few Notes

- My approach is very naive. Can be improved with other algo which I mention in my presentation
- I like pytorch than tf for research. [pytorch lightning](https://github.com/PyTorchLightning/pytorch-lightning) is used for convenience!
- I could have written py scripts, but then notebook could work for approaching the problem space.
- Python environment is `3.8.10`


## Tag Analysis

The notebook `tags-analysis.ipynb` is where I analyze the tags/keywords at different hierarichies of the tree.

I have found that at `level=1`, we get the keywords (N=29) classes with good distribution.
So, the rest of the solution assumes only 29 classes (actually it's 22, see below!).

## Data Analysis

Since, we're fine-tuning BERT, it requres a text of `max len = 512`.
So, I had to truncate the data accordingly. This puts us to only 2K data points, with **N=22** classes.
This is a simple assumption that has worked.

## Training

Refer to `naive-training-bert.ipynb`


## Further Reads

Please look into the powerpoint presentation I have at `resources/`.
