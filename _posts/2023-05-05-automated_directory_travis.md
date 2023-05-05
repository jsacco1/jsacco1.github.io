---
title: "Single-cell python modules with Travis CI"
date: 2023-05-05
tags: [bash, tests, automation, argparse, python, CICD, programming, best practices, computational biology, single cell, reproducibility, research, methods, data management, project management, version control, Github, bioinformatics, open-source, Travis, tools, productivity]
header:
  image: 
excerpt: "In which I try to merging CI/CD and automated directory structures for single-cell analysis"
mathjax: "true"
---

## Automation of directory structure creation with CI/CD integration

As I continue to automate common bioinformatics tasks, and try to integrate more programming best practices for open-source
distribution, today I tried to install and integrate Travis CI into my automatic directory structure script. 

I chose Travis CI as a CI/CD tool as it's relatively common with Python programmers, and doesn't have as complex a UI as 
Jenkins, which has many bells and whistles I do not need for now. 

I made a script that would download python and pip if they weren't already installed, and then downloaded Travis CI and created a `travis_ci` directory in my home directory. Next, it would `pip install argparse` to process two arguments to a toy python script. Finally, the script would run the Travis CI build `build.sh` script. 

I ran into some errors and warnings that may be instructive for people new to using a tool such as Travis CI with their projects:

My toy `requirements.txt` file included pysam and velocyto. I had trouble with their installation, despite the fact that I explicitly specified stable version numbers. Note that Veloctyo is available via pip, but not conda. CellRanger from 10X Genomics, a popular tool for single-cell genomics, must be downloaded separately; it is not available via conda or pip.

Finally, I made: 

1. A toy class in my python script that processes user arguments: `python my_script --arg1 --arg2`
 
2. A `setup.py` script to install the requirements.
 
3. `tests` directory to contain my unit tests.

The result of running this script resulted in three folders, with their appropriate files:

`build/`

`dist/`

`my_bioinformatics_project.egg-info/`

The `dist` folder is to help future users in distributing the project with a wheel file, and the egg info folder has metadata about the project, including dependencies.


The result of this effort to automate directory creation and CI/CD integration has been has provided me 
some useful insights. Since I now have Travis CI installed after my initial experiment, I have created a new bash script. This script creates a directory called `my_project` and sets up the directory structure for code, data (raw and processed), and a virtual environment `venv`, which is immediately activated. Next it installs required packages, and initializes Git. It also creates a simple Python script called `my_script.py` and a test script called `test_my_script.py`, and adds them to the appropriate directories. The script also creates a `requirements.txt` file, a `setup.py` file, a `README.md` file, a `build.sh` script (with executable permissions), and a `.travis.yml` file. Note that this is just an example, and you may need to modify these files to suit your specific project requirements. 

I am excited to adopt more programming best practices to contribute to open questions in computational biology! Please reach out if you have any questions. 

References:

Velocyto docs about not supporting conda installation (yet):

http://velocyto.org/velocyto.py/install/index.html#install-using-conda . accessed 5/5/23.
