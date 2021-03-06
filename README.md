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

## [New] Hierarchical Multi-label classification

Refer to `hierarchical_classification.ipynb`.

It makes use of the NeuralNLP-NeuralClassifier framework (see reference section below).


## Further Reads

Please look into the powerpoint presentation I have at `resources/`.

## Reference
- [How to train a multi-label classifer](https://github.com/keras-team/keras/issues/741)
- [Using `BCEWithLogisLoss` for multi-label classification](https://discuss.pytorch.org/t/using-bcewithlogisloss-for-multi-label-classification/67011)
- [PyData: Jurgen Van Gael - Hierarchical Text Classification using Python](https://www.youtube.com/watch?v=Xg8UtTgziZE&t=1979s)
- [Label Embedding using Hierarchical Structure of Labels for Twitter Classification](https://aclanthology.org/D19-1660.pdf)
- [NeuralNLP-NeuralClassifier](https://github.com/Tencent/NeuralNLP-NeuralClassifier) :  An Open-source Neural Hierarchical Multi-label Text Classification Toolkit
- [NeuralClassifier: An Open-source Neural Hierarchical Multi-label Text Classification Toolkit](https://aclanthology.org/P19-3015/)
