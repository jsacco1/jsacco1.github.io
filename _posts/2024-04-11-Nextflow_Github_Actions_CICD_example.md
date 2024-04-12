---
title: "Streamlining Bioinformatics Projects with CI/CD Using Nextflow and Github Actions"
date: 2024-04-11
tags: [bash, tests, automation, CICD, programming, best practices, reproducibility, research, methods, data management, project management, version control, Github, bioinformatics, open-source, Nextflow, tools, productivity]
header:
  image: 
excerpt: "CI/CD in a generic bioinformatics workflow with Nextflow and Github Actions"
mathjax: "true"
---

## Bioinformatics Projects CI/CD with Nextflow and Github Actions

In the field of bioinformatics, there's a growing need for bioinformaticians to be familiar with CI/CD frameworks. Whether you're exploring scientific questions or building automated pipelines, demonstrating proficiency in CI/CD becomes important, especially when stakeholders want to use your tools or methods beyond the prototype phase. This is where CI/CD tools like Nextflow and Github Actions come in handy.

I've worked on integrating Nextflow, pytest, and Github into a general bioinformatics repository, facing some challenges along the way. The trickiest part was setting up the main.yml file to handle tasks like setting up and using a conda environment, installing conda packages, and running Pytest scripts.

Even though the Github Actions runner does not interface with my local conda environment, I still need an environment yaml made with:

`conda env export > project_root/path/to/environment.yml`

I also had to create a main.nf file to run the Nextflow pipeline, which involved defining processes and workflows correctly. This was more straightforward than correctly formatting and calling methods for Github Actions.

Helpful Github Actions features include: its clear error messages, progress indicators during build and test, and email notifications for workflow failures. It seamlessly integrates with Github, where each push triggers a pipeline run that can be monitored in real time on the Actions tab, with detailed logs showing where errors occurred. Each run also gets a unique identifier for tracking.

While the web interface of Github Actions was easy to use, dealing with the syntax of Nextflow and Github Actions was more challenging. However, the Nextflow documentation has many useful examples (e.g., the Machine Learning pipeline<sup>[1](#ref1)</sup>; there's even an RNA-seq pipeline<sup>[2](#ref2)</sup>.).  

I appreciate the simplicity in task sequencing and dependency assignment offered by Nextflow and Github Actions. Their template workflow files simplify task management, making them stand out among CI/CD tools. 

I personally prefer Github Actions to other CI/CD tools, and Nextflow has been great for organizing my workflows, eliminating the need for manual script numbering and cluttered bash scripts. Despite the learning curve, Nextflow and Github Actions have significantly improved my development and production workflows.

### Code availability

Code for this project can be found at [https://github.com/jsacco1/crispr-bio](https://github.com/jsacco1/crispr-bio).

### References

<a name="ref1">1</a>: Source: [Machine Learning pipeline](https://www.nextflow.io/example5.html). Accessed April 11, 2024.

<a name="ref2">2</a>: Source: [RNA-seq pipeline](https://www.nextflow.io/example4.html). Accessed April 11, 2024.
