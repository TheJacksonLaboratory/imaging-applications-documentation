# Workshop Materials

This page is meant to act as a collection of the latest Imaging Applications team workshop materials.

## OMERO-related workshops

### Introduction to OMERO

OMERO is an image data management and hosting solution. This workshop covers how to store, view, share, annotate, and analyze image data in OMERO.  
No prior experience with OMERO is necessary.

[Workshop materials](https://thejacksonlaboratory.github.io/omero-training-materials/)  
[GitHub repository](https://github.com/TheJacksonLaboratory/omero-training-materials)

### [OMERO for Python Users](#omero-for-python-users-1)

## Software tools workshops

### Introduction to CellProfiler

[CellProfiler](https://cellprofiler.org) is a Python-based software package focused on image processing and analysis. This workshop serves as an introduction to the software and covers key concept such as projects, modules, and pipelines, as well as building and testing pipelines. 

[Workshop slide-deck](https://thejacksonlaboratory.github.io/intro_cellprofiler_workshop/)  
[GitHub repository](https://github.com/TheJacksonLaboratory/intro_cellprofiler_workshop)

### Introduction to Fiji

[Fiji](https://fiji.sc) is a distribution of the [ImageJ](https://imagej.net/software/imagej/) open-source software package for analyzing scientific images. This workshop covers the basic concepts of image analysis (e.g. pixels, bit-depth) and then key Fiji concepts including the GUI layout, scale bars, measurements, and stacks. Finally, selected analysis applications/workflows are demonstrated, including segmentation, colocalization, and tracking. 

[Workshop slide-deck](https://thejacksonlaboratory.github.io/fiji_workshops/IntroFiji.html)  
[GitHub repository](https://github.com/TheJacksonLaboratory/fiji_workshops)

### Intermediate Fiji: Macros & Scripting
<materials in progress>

### Introduction to napari

[napari](https://napari.org) is a Python image visualization and annotation application. This workshop is an introduction to napari and the napari ecosystem. It covers key concepts such as the GUI layout, viewer and layer models, as well as more advanced concepts such as the ability to bidirectionally interact with napari from Python code and make simple GUI widgets.  
Note: It is intended for people who already have some familiarity with Python.

[Workshop slide-deck](https://thejacksonlaboratory.github.io/intro-napari-workshop/)  
[GitHub repository](https://github.com/TheJacksonLaboratory/intro-napari-workshop)

### Introduction to QuPath

[QuPath](https://qupath.github.io) is a Java-based image visualization, annotation, and analysis package. This workshop begins with an introduction to the software and cover key concepts such as projects, images, classes, annotations, detections, followed by an example of segmentation and classification.

[Workshop slide-deck](https://thejacksonlaboratory.github.io/intro_qupath_workshop/)  
[GitHub repository](https://github.com/TheJacksonLaboratory/intro_qupath_workshop)

## Python-related workshops

Note: These workshops are intended for people who already have some familiarity with Python.

### (Bio)Image Processing with Python

This workshop will cover reading image files into Python to visualize and manipulate the image data using scikit-image, the most prominent image processing library for Python. Then it covers building a basic bioimage processing pipeline to apply basic filters, threshold, and segment objects in an image.  

[Workshop materials](https://thejacksonlaboratory.github.io/image-processing-ia/)  
[GitHub repository](https://github.com/TheJacksonLaboratory/image-processing-ia)

### OMERO for Python Users

This workshop covers interacting with the OMERO server from Python using primarily [ezomero](https://github.com/TheJacksonLaboratory/ezomero) and either the JSON or Blitz APIs.  

[Workshop Jupyter Notebooks](https://github.com/TheJacksonLaboratory/omero_for_developers#workshop-notebooks)  
[GitHub repository](https://github.com/TheJacksonLaboratory/omero_for_developers)

### Zarr and Dask for Large-Scale Imaging

[Zarr](https://zarr.dev) is a format for storing image data in chunks that is amenable for parallel computing and cloud storage. [Dask](https://www.dask.org) is a Python library for parallel computing that enables working with data that is larger than computer RAM. This workshop covers the use of the Zarr file format and Dask library to scale-up image analysis pipelines in Python.  
Note: these Colab notebooks require a Google account.

| Topics | Notebooks | Solutions |
|--------|-----------|-----------|
| Intro to Zarr | [link](https://colab.research.google.com/drive/1Um_1hgM0zkq8varrRWM4tqFGp-kVZF-w) | [link](https://colab.research.google.com/drive/1wdanwx1dvFZkw9OGYTjPvcf_onbW3Wrv) |
| Converting images to Zarr arrays for image analysis | [link](https://colab.research.google.com/drive/1mwxIWU2Pb8pS7RATd_Cp34p6xyMQIwDi) | [link](https://colab.research.google.com/drive/1UxVo0G97xbcXIFd7a_t50cBO86lZUIXA) |
| Tools for image analysis and visualization | [link](https://colab.research.google.com/drive/150CYBrKQn41H4klwh7-sQA3eciD4MJJ0) |  [link](https://colab.research.google.com/drive/1NrrpbP5S7zSASi15bYtvHDkYnXZ5aesc) |
| Intro to Dask | [link](https://colab.research.google.com/drive/1UcVfEbMwZkWjFtigYOS1KnQfDU6QnrgR) | [link](https://colab.research.google.com/drive/1_kPDnqs-Rvg8wzOV1_cxZFkwJt119xg0) |
| Computation on Dask arrays | [link](https://colab.research.google.com/drive/1uNlv7WdW4mPVr7TsYhx-WUeneULn0PeE) | [link](https://colab.research.google.com/drive/1KHsmnYLc4OEQdBmQ1MfFTJwmbVJWdMe8) |

### Introduction to Machine Learning with Python

This workshop provides an introduction to machine learning methods in Python, focusing on [scikit-learn](https://scikit-learn.org/stable/) and [PyTorch](https://pytorch.org).  
Note: these Colab notebooks require a Google account.

| Topics | Notebooks | Solutions |
|--------|-----------|-----------|
| Intro to ML with scikit-learn (sklearn) | [link](https://colab.research.google.com/drive/1zxmDK5049NpPYZw_N19hqv38nwf7Dev5) | [link](https://colab.research.google.com/drive/1CW2sscX2iOWhcyOk0ScQ2jmm8W5C9jI-) |
| Model comparison with confusion matrices | [link](https://colab.research.google.com/drive/1FkgumW-hrkFSaMWJYMbRqOgoeR1ykvwY) | [link](https://colab.research.google.com/drive/18eNfASrxeCaGd8WgkLeyBx32IYVBupLa) |
| [Optional] PCA for features extraction (Requires to download and upload the dataset from the first notebook) |  [link](https://colab.research.google.com/drive/1y0eNMrUp607Rg6SQUAfZ3Bb9S9aPfLSF) | [link](https://colab.research.google.com/drive/1VNwX7JLHIbh6ygbE_x1ULzlbXguk4kig) |
| Intro to PyTorch | [link](https://colab.research.google.com/drive/1woc7ihB4O9nx6s_2TzFM8CIvKU_9yANx) | [link](https://colab.research.google.com/drive/1pPBf645eZRXtImSZLp2jyYNQxAeDXuWN) |
| Deep Learning for image classification and feature extraction | [link](https://colab.research.google.com/drive/1XI7QXw-4OsxCHuRFTYaPwMTVgIJsD2cU) | [link](https://colab.research.google.com/drive/103cSwSoeAva4O2_UDACgh55KF5w3-Dzm) |
| [Optional] Tissue classification combining Deep Learning and Classic Machine Learning | [link](https://colab.research.google.com/drive/1H0k2dkoWSfdv6KPZaGwmzREExnAFfzWJ) | [link](https://colab.research.google.com/drive/1zrpaB-7nJoAZ2BYf9Mk-5_kBs-Xby8hg) |

### Advanced Machine Learning in Python

### Best practices in Python

This workshop focuses on ways Python coders can improve code readability, maintainability and reproducibility. It covers virtual environments, automated testing, code formatting, and documentation.

[Workshop materials (md)](https://github.com/TheJacksonLaboratory/bestpractices_workshop/blob/main/README.md#bestpractices_workshop)  
[GitHub repository](https://github.com/TheJacksonLaboratory/bestpractices_workshop)
