# Welcome to the PyPSA workshop at TransnetBW

## Using Python for Energy System Modelling

### Anaconda

Coordinating the compatibility between different Python software packages and
their multiple versions can be difficult! Fortunately, the problem is solved by
using a Python _distribution_ and/or _package manager_.

For instance, you can install on your computer the popular [Anaconda Python
Distribution](https://www.anaconda.com/download/).

For **Linux and MacOS users**, you can access the command line by opening the
_terminal_ program.

For **Windows users**, you should first install Anaconda (described above) or
`miniconda` (described below), which gives you access to the "Anaconda Prompt"
desktop application. Instructions for this are given on the [Anaconda
Website](https://docs.anaconda.com/anaconda/user-guide/getting-started/#write-a-python-program-using-anaconda-prompt-or-terminal).
From the Anaconda Prompt, you should be able to run `conda`.

### Lightweight `miniconda`

If you don't want the full Anaconda Python Distribution, there is a lightweight
alternative installation called
[`miniconda`](https://docs.conda.io/en/latest/miniconda.html).

### Google Colab

You can even do the course without a local Python installation using online
services like [Google Colab (colab.google)](https://colab.google) which provide
an online Python environment. This requires a Google account.

## Managing environments with `conda`

Python coupled with a package manager provides a way to make isolated,
reproducible _environments_ where you have control over all installed packages
and configurations.

First, check that you have access to `conda` in your _terminal_ or _Anaconda Prompt_ application by typing:

    conda --version

To create a conda environment, you execute the following command:

    conda create --name my_environment python=3.11 numpy

To use this environment, simply _activate_ it by executing:

    conda activate my_environment

You should now see the string `(my_environment)` prepended to your prompt.
Now, any execution of Python will use the packages installed in your _environment_ "my_environment".

To install additional packages into your environment:

    conda install <package-name>

Some packages are community-maintained (e.g. `conda-forge`) and require you to specify a different "channel", i.e. a different source:

    conda install -c conda-forge <package-name>

You can deactivate your environment by typing:

    conda deactivate

To see all the environments on your system:

    conda env list

To get a complete summary of all the packages installed in your environment, run

    conda list

If you want to permanently remove an environment and delete all the data
associated with it:

    conda env remove --name my_environment --all

A conda environment can also be defined through an `environment.yaml` file. With that file, a new environment with the exact
configuration can be installed by executing

    conda env create -f my_environment.yml

For extensive documentation on using environments, please see
[the conda documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/environments.html).

## Environment for this course: `workshop`

### ... with `conda` (recommended)

The latest environment specification for this course can be downloaded under the following link as a [`YAML`-file](https://en.wikipedia.org/wiki/YAML):

https://github.com/Irieo/workshop-pypsa-transnetbw/blob/main/environment.yaml

There is a download button at the top-right corner.

After navigating to the folder where the `environment.yaml` file is stored ([here](https://tutorials.codebar.io/command-line/introduction/tutorial.html)'s a tutorial how to navigate with the command line),
you can reate this environment using `conda`

    conda env create -f environment.yaml

Activate this environment

    conda activate workshop

This environment should be sufficient for all of your work in this course.

The environment has to be activated whenever you open a new terminal,
*before* starting a new Jupyter window with

    jupyter lab

### ... with `pip`

If you want to use `pip` for managing your environment, download

https://github.com/Irieo/workshop-pypsa-transnetbw/blob/main/requirements.txt

There is a download button at the top-right corner.

After navigating to the folder where the `requirements.txt` file is stored,
you can install the required packages with

    pip install -r requirements.txt

This should allow you to start a new Jupyter window:

    jupyter lab
