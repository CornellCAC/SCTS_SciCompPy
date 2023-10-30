# Instructions for running notebook and exercises for "Scientific Computing with Python"

Chris Myers / Cornell Center for Advanced Computing / c.myers@cornell.edu

## Overall logistics
* This material can be found at in a github repository at https://github.com/CornellCAC/SCTS_SciCompPy .
* This material accompanies the Zoom-based lecture "Scientific Computing with Python", offered as part of the Cornell/WCM Scientific Computing Training Series (SCTS).
* The lecture will be run within a Jupyter notebook, with optional exercises available for participants to work on within the notebook, during the hands-on portion of the lecture.
* If you would like to be able to run the notebook and work on the exercises, you will need a suitable Jupyter+Python environment where you can access the notebook (more below).
* If you do not want to run the notebook and work on the exercises, you do not need to do anything further.  Both the lecture-based material at the beginning of the session and the hands-on exercises at the end of the session will be conducted over Zoom.
* If you have any problems getting any of this to work, please send me an email and I'll see what I can do to help.

## Accessing the notebook contained in this repository

The repository contains the following files:
* Scientific_Computing_with_Python.ipynb : a Jupyter notebook containing lecture materials and exercises
* README.md : this file
* figures: a directory containing png images that are embedded within the notebook

There are a few different options for accessing this material, two of which are described here.

### Use git

If you have git installed locally, you should be able to clone the repository, either through a GUI or on the command line with a suitable "git clone" command (which differs depending on whether you are using an https or ssh interface).

### Download the repository in a zip file

Click on the Code button above the file browser, and then click "Download ZIP".  Unzip the file to access its contents.

## Running the notebook and participating in the exercises

There are a few different options for running the notebook and exercises, which are described below.  Once you've loaded the notebook into a JupyterLab environment, you can run cells by clicking the Run icon (right-pointing triangle) or by examining the various Run options in the Run menu.

### 1. Run Jupyter locally

If you want to run on your own machine, you'll need python installed, along with the following packages:
* jupyter 
* numpy
* scipy
* pandas
* matplotlib
* statsmodels
* openpyxl

Depending on how you have python installed, there are few different options for proceeding.

(a) You might already have all these packages installed, especially if you are running a big bundle like the Anaconda Python Distribution.  You could try starting up "jupyter lab" (either from the command line, or from a GUI such as Anaconda Navigator if you have that installed), and then try importing each of the remaining packages (numpy, scipy, pandas, matplotlib, statsmodels, openpyxl).

(b) You might have a miniconda installation, in which case you could create a conda environment containing what is needed.  For example, you could create a new environment named ```py_sci_comp``` with the requisite packages:

```
conda create --name py_sci_comp python numpy scipy pandas matplotlib statsmodels openpyxl jupyter
conda activate py_sci_comp
```

(c) You might have a non-conda-based python installation, in which case you could create a python virtual environment containing what is needed.  For example, you could create a new virtual environment named ```py_sci_comp``` with the requisite packages:

```
python -m venv py_sci_comp       # might be installed as python3 on your system
source py_sci_comp/bin/activate
pip install --upgrade pip      # get the latest version of pip
pip install numpy scipy pandas matplotlib statsmodels openpyxl jupyter
```

(d) You might not have any python installation on your machine, but are interested in being able to run python and associated packages locally.  In this case, I would recommend downloading and installing miniconda following the instructions at:

https://docs.conda.io/projects/miniconda/en/latest

and then following the instructions in item (b) above in order to create a new conda environment.  With miniconda, you can create as many customized conda environments as you need to support different projects and workflows.

### 2. Run Jupyter in the Cloud

Several options exist for running Jupyter notebooks on cloud resources, including many paid options and some free ones.  We discuss a few here, in no particular order.

(a) **Amazon SageMaker Studio Lab**  ( https://studiolab.sagemaker.aws/ )

Amazon SageMaker Studio Lab is a free service that gives customers access to AWS compute resources, in an environment based on open-source JupyterLab. It is based on the same architecture and user interface as Amazon SageMaker Studio, but with a subset of Studio capabilities.

Steps
* You can sign up for a free Studio Lab account and get access to free computational resources to run this notebook and participate in this session.  **Note**: your request for an account needs to first be approved by AWS, and this might not happen immediately.  Therefore, if you want to use this option, I would suggest signing up for an account in advance of the workshop.
* Once you have an account, sign up, and click the button labeled "Start Runtime".  You only need a CPU runtime to carry out the exercises in this notebook.
* Once the runtime is started, click "Open Project", which should put you in a JupyterLab environment.
* Use the file upload icon near the upper left (upward pointing arrow) to upload the notebook "Scientific_Computing_with_Python.ipynb".
* Click (double-click) on the notebook you uploaded to launch it.
* When asked about a Kernel, select "sagemaker-distribution:Python".
* **Note**: the sagemaker-distribution:Python kernel contains most of the packages we need, but it does not contain ```statsmodels``` and ```openpyxl```.  Therefore, you will need to separately install those.  In the notebook section on "Working in this notebook", there is an exercise entitled "Exercise: Do you have all the packages installed that you need?"  Run that code cell, and it should tell you what packages you need.  If you need additional packages (statsmodels, openpyxl, or something else), follow the instructions in the following cell to run something like:

%conda install statsmodels openpyxl

(b) **Amazon SageMaker Studio** ( https://aws.amazon.com/sagemaker/ )

Amazon SageMaker Studio is a paid service (albeit with a free tier) that requires an AWS account.  SageMaker Studio was the basis of the Cloud environment highlighted by Christopher Cameron in his SCTS lecture on "JupyterLab (in the Cloud) with Python".

I have not run in SageMaker Studio myself, but I assume that it is similar to Studio Lab.  Follow the Amazon SageMaker Studio Lab instructions above.

(c) **Google Colaboratory** ( https://colab.research.google.com )

Google Colaboratory (Colab) is a web service that enables users to run Jupyter notebooks and to connect with data stored in their Google Drive.  It has both free and paid versions, as well as access to both CPU-only and CPU+GPU resources.  For these exercises, we only need the default CPU runtime.

Steps
* Navigate to Colab, and upload the notebook in this repository by selecting "File > Upload notebook".
* All of the packages that you need should be part of the notebook environment you are running in.  If one or more packages are not available, you could try using pip to install them, since Colab does not use conda.  Try something like "%pip install statsmodels" in a code cell if needed.
* For some reason, the embedded images that show up in other Jupyter environments do not get rendered in Colab.  Instead, only file names for the images are shown.  That is not a deal-breaker, and any plots you make in the notebook will get rendered correctly.  If anyone figures out how to get those embedded message to render correctly in Colab, I would appreciate finding out how to do that.
* The Colab user interface is similar to, but a bit different than, the interface provided by JupyterLab.
























