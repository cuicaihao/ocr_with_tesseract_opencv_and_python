# OCR with Tesseract OpenCV and Python

A comprehensive guide to OCR with Tesseract, OpenCV and Python.

## Project Organization

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io

---

# OCR in Python with OpenCV, Tesseract and Pytesseract

Companion tutorial blog post can be found [here](https://nanonets.com/blog/ocr-with-tesseract/)

### Preprocessing of images using OpenCV

Basic functions for different preprocessing methods

- grayscaling
- thresholding
- dilating
- eroding
- opening
- canny edge detection
- noise removal
- deskwing
- template matching.

Different methods can come in handy with different kinds of images.

### Bounding box information using Pytesseract

While running and image through the tesseract OCR engine, pytesseract allows you to get bounding box imformation

- on a character level
- on a word level
- based on a regex template

We will see how to obtain all of them.

### Page Segmentation Modes

There are several ways a page of text can be analysed. The tesseract api provides several page segmentation modes if you want to run OCR on only a small region or in different orientations, etc.

Here's a list of the supported page segmentation modes by tesseract -

0 Orientation and script detection (OSD) only.  
1 Automatic page segmentation with OSD.  
2 Automatic page segmentation, but no OSD, or OCR.  
3 Fully automatic page segmentation, but no OSD. (Default)  
4 Assume a single column of text of variable sizes.  
5 Assume a single uniform block of vertically aligned text.  
6 Assume a single uniform block of text.  
7 Treat the image as a single text line.  
8 Treat the image as a single word.  
9 Treat the image as a single word in a circle.  
10 Treat the image as a single character.  
11 Sparse text. Find as much text as possible in no particular order.  
12 Sparse text with OSD.  
13 Raw line. Treat the image as a single text line, bypassing hacks that are Tesseract-specific.

To change your page segmentation mode, change the `--psm` argument in your custom config string to any of the above mentioned mode codes.

### Playing around with the config

By making minor changes in the config file you can

- specify language
- detect only digits
- whitelist characters
- blacklist characters
- work with multiple languages

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
