---
title: "Bioinformatics Projects CI/CD with Nextflow and Github Actions"
date: 2024-04-11
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

The best parts of the user experience of Github Actions are: its error messages, its little progress circles for `build` and `test`, and that Github emails you when your workflow run fails. Every push automatically runs the pipeline, which can be tracked in real time from the Actions tab of your repo. The logging provides informative detail as to where the errors occurred. Each run of your pipeline also gets a name and number. 

While the web experience was easy to pick up, the complex syntax for Nextflow and Github Actions created a bigger challenge for me. However, the Nextflow documentation has many useful examples (e.g., the Machine Learning pipeline <sup>1/sup>; there's even an RNA-seq pipeline <sup>2</sup>).  

I appreciate that the authors of Nextflow and Github Actions aimed for simplicity of ordering tasks and assigning dependencies. The templates for Nextflow and Github Actions workflow files take heavily stereotyped forms. 

Overall, I can say that I much prefer Github Actions to other CI/CD tools, and I really like Nextflow for organizing my workflows; it beats manually numbering script file names, and then stashing them all in a bash script. For both development and production, my use case has allowed me to see that the learning curve for Nextflow and Github Actions is worth the effort. 

### Code availability
Code for this project can be found at `https://github.com/jsacco1/crispr-bio`

### References
<sup>1/sup> : Source: `https://www.nextflow.io/example5.html`. Accessed April 11, 2024.

<sup>2/sup> : Source: `https://www.nextflow.io/example4.html`. Accessed April 11, 2024.