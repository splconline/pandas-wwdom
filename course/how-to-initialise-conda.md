# How to Initialise Conda

## 1. Download

We will use the 'mini' version available [here](https://docs.conda.io/en/latest/miniconda.html) (scroll down to 'Linux Installers').

As of writing 20.02.2022, the latest miniconda file was `Miniconda3-py39_4.11.0-Linux-x86_64.sh`

## 2. Install

To install, navigate to the folder containing the above and then 'bash' it:

```
bash Miniconda3-py39_4.11.0-Linux-x86_64.sh
```

Note that this command was current at 20.02.2022, don't copy-paste it!

(Hint: use tab predictive text to select the file, saves you typing out the whole filename)

## 3. Create Environment

A 'base' environment will be created. To see what environment you are in:

```
conda info --envs
```

Create a separate environment to the base environment (leave the base environment clean, no sure why, the video said so), then activate it.

```
conda create -n wwdom python=3
conda activate wwdom
```

If you like, check the current environment as before with `conda info --envs`.

## 4. Add Packages

Add the required packages:

```
conda install pandas xlsxwriter xlrd openpyxl notebook
```

## Optional: Cookie Cutter
To automate the creation of a template 'cookie cutter' file structure, first install cookiecutter (note that the [cookiecutter](https://github.com/talkpython/pbp_cookiecutter) page has a different install command - [and here's why](https://snarky.ca/why-you-should-use-python-m-pip/)):

```
python -m pip install cookiecutter
```

Then:

```
cookiecutter https://github.com/talkpython/pbp_cookiecutter
```

You will then be prompted for the name of the project, directory name then short description
