# Introduction to Machine Learning with Pythonn

<a style="width: 400px" href="https://www.amazon.com/Introduction-Machine-Learning-Python-Scientists/dp/1449369413"><img alt="Introduction to Machine Learning with Python Cover" src="./cover.png" style="width: 400px; height: auto; padding: 10px;"></a>


**Original Authors:** Andreas C. Mueller & Sarah Guido

This repository contains the reproduced code, exercises, and notes based on the O'Reilly book *"Introduction to Machine Learning with Python"*. The primary goal of this project is to provide a working, up-to-date environment to run the examples provided in the book, addressing common compatibility issues with modern Python libraries.

## 📋 Table of Contents

- [Prerequisites](#-prerequisites)
- [Installation Guide](#-installation-guide)
  - [Option A: Conda (Recommended)](#option-a-conda-recommended)
  - [Option B: Python Virtual Environment](#option-b-python-virtual-environment)
- [Project Structure](#-project-structure)
- [Usage](#-usage)
- [Troubleshooting & Common Issues](#-troubleshooting--common-issues)
- [Dependencies](#-dependencies)
- [Acknowledgments](#-acknowledgments)

## 📋 Prerequisites

To ensure a smooth setup, please ensure you have the following installed on your system:

* **Python 3.9+**: While the book was written for earlier versions, this repo is tested on Python 3.9+.
* **Anaconda or Miniconda**: Highly recommended for data science environment management.
* **Git**: For version control.
* **Graphviz**: Required for visualizing decision trees (see Troubleshooting section).

## 🛠 Installation Guide

The book relies heavily on a custom helper library called `mglearn`, written by the authors to simplify plotting and data loading.

### Option A: Conda (Recommended)
Using Conda ensures that binary dependencies (like those needed for `numpy` and `scipy`) are handled correctly.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/farrelrassya/IntroductionMachineLearningwithpython.git](https://github.com/farrelrassya/IntroductionMachineLearningwithpython.git)
    cd IntroductionMachineLearningwithpython
    ```

2.  **Create a dedicated environment:**
    ```bash
    conda create -n ml-book python=3.9
    ```

3.  **Activate the environment:**
    ```bash
    conda activate ml-book
    ```

4.  **Install core data science libraries:**
    ```bash
    conda install numpy pandas scikit-learn matplotlib jupyter seaborn
    ```

5.  **Install the book's helper library and utilities:**
    ```bash
    pip install mglearn imageio graphviz
    ```

### Option B: Python Virtual Environment
If you prefer using standard `pip`:

1.  **Create a virtual environment:**
    ```bash
    # Windows
    python -m venv venv
    # macOS/Linux
    python3 -m venv venv
    ```

2.  **Activate the environment:**
    ```bash
    # Windows
    .\venv\Scripts\activate
    # macOS/Linux
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

## 📂 Project Structure

The repository is organized by chapter to mirror the book's progression:

```text
.
├── Chapter 01 - Introduction
│   └── 01_introduction.ipynb
├── Chapter 02 - Supervised Learning
│   └── 02_supervised_learning.ipynb
├── Chapter 03 - Unsupervised Learning
│   └── 03_unsupervised_learning.ipynb
├── Chapter 04 - Data Representation
│   └── 04_data_representation.ipynb
├── Chapter 05 - Model Evaluation
│   └── 05_model_evaluation.ipynb
├── Chapter 06 - Algorithm Chains and Pipelines
│   └── 06_pipelines.ipynb
├── Chapter 07 - Working with Text Data
│   └── 07_text_data.ipynb
├── data/                  # Local datasets (if not loaded from sklearn)
├── images/                # Generated plots and figures
├── README.md
└── requirements.txt

```

## 🚀 Usage

1. Activate your environment:
```bash
conda activate ml-book

```


2. Launch the Jupyter Notebook server:
```bash
jupyter notebook

```


3. Navigate to the specific chapter folder and open the `.ipynb` file.

## ⚠️ Troubleshooting & Common Issues

Since the book was published, `scikit-learn` has undergone significant updates. Here are common issues you might encounter:

### 1. `ModuleNotFoundError: No module named 'mglearn'`

**Cause:** The helper library is not installed.
**Fix:** Run `pip install mglearn` inside your active environment.

### 2. Graphviz Executable Not Found

**Issue:** When plotting Decision Trees, you get an error stating `GraphViz's executables not found`.
**Fix:** Installing the python library `graphviz` is not enough; you must install the system binary.

* **Windows:** Download the installer from the [Graphviz website](https://graphviz.org/download/), run it, and **ensure you check the box "Add Graphviz to PATH"**.
* **macOS:** `brew install graphviz`
* **Linux (Ubuntu/Debian):** `sudo apt-get install graphviz`

### 3. FutureWarnings and DeprecationWarnings

**Issue:** You see red warning boxes regarding "default values changing" or "functions being deprecated."
**Context:** The API of `scikit-learn` evolves. For example, the default value of `n_estimators` in Random Forest changed from 10 to 100 in newer versions.
**Fix:** These are generally safe to ignore for learning purposes. However, it is good practice to explicitly set parameters mentioned in the warnings to silence them.

### 4. `memory_profiler` or other minor missing libs

Some sections of the book use `memory_profiler`. Install it via:

```bash
pip install memory_profiler

```

## 📦 Dependencies

The core requirements for this project are listed below. If creating a `requirements.txt` file manually, include:

```text
numpy
pandas
scikit-learn>=1.0
matplotlib
mglearn
jupyter
imageio
graphviz

```

## 👏 Acknowledgments

* **Andreas C. Mueller & Sarah Guido**: For writing the excellent book that serves as the foundation for this code.
* **scikit-learn community**: For maintaining the library used throughout these examples.

For more information on the book, visit the [O'Reilly website](https://www.oreilly.com/library/view/introduction-to-machine/9781449369880/).

