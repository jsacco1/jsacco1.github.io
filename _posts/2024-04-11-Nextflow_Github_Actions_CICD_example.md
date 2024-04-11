---
title: "Bioinformatics Projects CI/CD with Nextflow and Github Actions"
date: 2023-05-05
tags: [bash, tests, automation, CICD, programming, best practices, reproducibility, research, methods, data management, project management, version control, Github, bioinformatics, open-source, Nextflow, tools, productivity]
header:
  image: 
excerpt: "CI/CD in a generic bioinformatics workflow with Nextflow and Github Actions"
mathjax: "true"
---

## Bioinformatics Projects CI/CD with Nextflow and Github Actions

If you work in the field of bioinformatics, you've probably noticed how more and more institutions demand that bioinformaticians know how to use at least one CI/CD framework. 

Whether you are studying an open-ended scientific question or building some sort of automated pipeline, at some point you may need to show your proficiency in CI/CD. Someone will want to run your tool or method in a post-prototype, or even production environment. To do that, CI/CD tools can come in handy. 

I have worked on installing and setting up Nextflow, pytest, and Github to use in a generic bioinformatics repository. 

The hardest part was getting the main.yml to run correctly, with its esoteric syntax for (1) installing and calling a conda environment, then (2) installing a conda package, and (3) making sure the python script I wanted to run used the right conda environmemt.

Even though the Github Actions runner does not interface with my local conda environment, I still need an environment yaml made with:

`conda env export > project_root/path/to/environment.yml`

I also needed to create a main.nf file to run the Nextflow pipeline. I had to define processes and workflows correctly, and even this was more straightforward than correctly formatting and calling methods for Github Actions.

The greatest things about Github Actions are its error messages, its little progress circles for `build` and `test`, and that Github emails you when your workflow runs, and whether it failed. So, for me the web UI is great. It's mastering the formatting and syntax for Nextflow and Github Actions that's quite sophisticated. I do appreciate that as CI/CD tools the authors did aim for simplicity of ordering tasks and assigning dependencies. 

Overall, I can say that I much prefer Github Actions to other CI/CD tools, and I really like Nextflow for organizing my workflows by manually numbering script file names. 

### Code availability
Code for this project can be found at `https://github.com/jsacco1/crispr-bio`