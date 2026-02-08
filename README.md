# Introduction to Machine Learning with Python

<a style="width: 400px" href="https://www.amazon.com/Introduction-Machine-Learning-Python-Scientists/dp/1449369413"><img alt="Introduction to Machine Learning with Python Cover" src="./cover.png" style="width: 400px; height: auto; padding: 10px;"></a>

This repository contains the reproduced code, exercises, and notes based on the O'Reilly book "Introduction to Machine Learning with Python". The primary goal of this project is to provide a working, up-to-date environment to run the examples provided in the book, addressing common compatibility issues with modern Python libraries.

📋 Table of Contents

Prerequisites

Installation Guide

Option A: Conda (Recommended)

Option B: Python Virtual Environment

Project Structure

Usage

Troubleshooting & Common Issues

Dependencies

Acknowledgments

📋 Prerequisites

To ensure a smooth setup, please ensure you have the following installed on your system:

Python 3.9+: While the book was written for earlier versions, this repo is tested on Python 3.9+.

Anaconda or Miniconda: Highly recommended for data science environment management.

Git: For version control.

Graphviz: Required for visualizing decision trees (see Troubleshooting section).

🛠 Installation Guide

The book relies heavily on a custom helper library called mglearn, written by the authors to simplify plotting and data loading.

Option A: Conda (Recommended)

Using Conda ensures that binary dependencies (like those needed for numpy and scipy) are handled correctly.

Clone the repository:

git clone [https://github.com/farrelrassya/IntroductionMachineLearningwithpython.git](https://github.com/farrelrassya/IntroductionMachineLearningwithpython.git)
cd intro-to-ml-python


Create a dedicated environment:

conda create -n ml-book python=3.9


Activate the environment:

conda activate ml-book


Install core data science libraries:

conda install numpy pandas scikit-learn matplotlib jupyter seaborn


Install the book's helper library and utilities:

pip install mglearn imageio graphviz


Option B: Python Virtual Environment

If you prefer using standard pip:

Create a virtual environment:

# Windows
python -m venv venv
# macOS/Linux
python3 -m venv venv


Activate the environment:

# Windows
.\venv\Scripts\activate
# macOS/Linux
source venv/bin/activate


Install dependencies:

pip install -r requirements.txt


📂 Project Structure

The repository is organized by chapter to mirror the book's progression:

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


🚀 Usage

Activate your environment:

conda activate ml-book


Launch the Jupyter Notebook server:

jupyter notebook


Navigate to the specific chapter folder and open the .ipynb file.

⚠️ Troubleshooting & Common Issues

Since the book was published, scikit-learn has undergone significant updates. Here are common issues you might encounter:

1. ModuleNotFoundError: No module named 'mglearn'

Cause: The helper library is not installed.
Fix: Run pip install mglearn inside your active environment.

2. Graphviz Executable Not Found

Issue: When plotting Decision Trees, you get an error stating GraphViz's executables not found.
Fix: Installing the python library graphviz is not enough; you must install the system binary.

Windows: Download the installer from the Graphviz website, run it, and ensure you check the box "Add Graphviz to PATH".

macOS: brew install graphviz

Linux (Ubuntu/Debian): sudo apt-get install graphviz

3. FutureWarnings and DeprecationWarnings

Issue: You see red warning boxes regarding "default values changing" or "functions being deprecated."
Context: The API of scikit-learn evolves. For example, the default value of n_estimators in Random Forest changed from 10 to 100 in newer versions.
Fix: These are generally safe to ignore for learning purposes. However, it is good practice to explicitly set parameters mentioned in the warnings to silence them.

4. memory_profiler or other minor missing libs

Some sections of the book use memory_profiler. Install it via:

pip install memory_profiler


📦 Dependencies

The core requirements for this project are listed below. If creating a requirements.txt file manually, include:

numpy
pandas
scikit-learn>=1.0
matplotlib
mglearn
jupyter
imageio
graphviz


👏 Acknowledgments

Andreas C. Mueller & Sarah Guido: For writing the excellent book that serves as the foundation for this code.

scikit-learn community: For maintaining the library used throughout these examples.

For more information on the book, visit the O'Reilly website.
