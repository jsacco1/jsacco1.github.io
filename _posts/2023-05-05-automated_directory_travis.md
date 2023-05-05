---
title: "Single-cell python modules with Travis CI"
date: 2023-05-05
tags: [bash, tests, automation, argparse, python, CICD, programming, bioinformatics, productivity]
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

I made a script that would download python and pip if they weren't already installed, and then downloaded Travis CI and created a 
`travis_ci` directory in my home directory. Next, it would `pip install argparse` to process two arguments to a toy
python script. Finally, the script would run the Travis CI build `build.sh` script. 

I ran into some errors and warnings that may be instructive for people new to using a tool such as Travis CI with their projects:

My toy requirements.txt file included pysam, velocyto, and CellRanger from 10X. I ended up deleting those, especially since
CellRanger needs to be downloaded separately as a tar.gz file (at least that's one way). Veloctyo is available via pip, but not conda.

Finally, I made: 

1. A toy class in my python script to process the two arguments (`python my_script --arg1 --arg2`)
 
2. `setup.py` script 
 
3. `tests` directory to contain my unit tests.

The result of running this script resulted in three folders, with their appropriate files:

```
build/

dist/

my_bioinformatics_project.egg-info/
```

The `dist` folder is to help future users in distributing the project with a wheel file, and the egg info folder
has all sorts of information about the project, including dependencies.


The result of this effort to make an automatic directory structure and README, and to use CI/CD is now to separate these tasks into two scripts.
One bash script can create the structure, while I run the python script with tests in another. I am excited to be on the path to contribute to open questions in computational biology by improving my programming practices.

References:

http://velocyto.org/velocyto.py/install/index.html#install-using-conda
