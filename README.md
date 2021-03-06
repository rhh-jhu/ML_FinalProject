# A Simple Plug-in Image Ensemble Defender (SPIE-D)
Project mentor: Dr. Mark Dredze

Russ Huang rhuang23@jh.edu, Randy Kuang rkuang2@jh.edu, Shaurya Kumar skumar65@jh.edu, Annie Liang jliang28@jh.edu

Link to Github Repo:
https://github.com/randy99kuang/ML_FinalProject

Link to Google Drive Folder:
https://drive.google.com/drive/folders/1DpGUPeNIxg7PVTRsdc5vFUIHa2WQKAz4?usp=sharing

## Overview of Code Repository
A few Colab/Jupyter Notebooks are containing in the root of the repository:
- "all.ipynb" contains every class/model/function as well as code that calls these models/functions.
- "condensed.ipynb" contains only the code that calls underlying models & functions by importing. Note that this file is no different than "all.ipynb" except that it imports Python code from the "Code" directory instead using additional cells to store code.
- The final report .ipynb file contains all code as well as text containing an overview of the project.

There are also two associated folders containing relevant files:
- The "Code" directory classes/models/functions used in the project. Note that none of this code produces executable output.
- "The "Models and Images" directory contains saved model and image files that were used. By default, the .ipynb notebooks will load these pre-trained models and images in interest of time.
Note that this directory is not in the Github repo due to size limitations, and is instead on Google Drive and can be accessed through the link above.

## Running the Notebooks
In order to actually run the code in any of the Notebooks, a few variables must be correctly set:
1. The "PATH" variable contained in the Notebooks must properly point to the directory containing saved model/image files.
2. If the condensed notebook is being run, then the path to the "Code" directory must be properly specified in order to import the files in "Code".
Specifically, the line `sys.path.append('appropriate/path/to/code')` in the Notebook must be properly set.
3. Next, note that if model or image recreation is desired when running the condensed Notebook, then the Python files in the "Code" directory also contain "PATH" variables that must be directed at a folder where model/images will be saved.
4. Lastly, see the section below on Provably Robust Boosting if this section of the .ipynb files need to be run.

## Provably Robust Boosting
One of the models we wanted to compare accuracies and test errors with used an ensemble of trees and adversarial training to create a robust model. The the link to their repository is here: https://github.com/max-andr/provably-robust-boosting We did make modifications to their code in order to evaluate their model on the adversarial attacks that we created, but are unable to add this code to our repo, since a lot of the code comes from their repo. This Google Drive link (https://drive.google.com/drive/folders/1DpGUPeNIxg7PVTRsdc5vFUIHa2WQKAz4?usp=sharing) should take you to the ML Project Files folder which containes the provably robust boosting folder which is modified to work on our datasets and our datasets. This folder is needed to run the Testing Eval on PRB python notebook.

Steps to Run Testing Eval on PRB:
1. Download the ML Final Project Files from the Google Drive Link
2. Go to ./provably robust boosting/eval.py and change the paths on line 19, 75, 77, 80, and 82 depending on the location of the folder on your system
3. Run the cells in the Testing Eval on PRB notebook to get test results 
`! python '(your path to this folder)/ML Final Project Files/provably-robust-boosting/eval.py' --iter 51 --n_eval 1`
will give you the test errors (TE) on our adversarial attacks 
`! python '(your path to this folder)/ML Final Project Files/provably-robust-boosting/eval.py' --iter 51`
will give you the test errors (TE) on their adversarial attacks 
