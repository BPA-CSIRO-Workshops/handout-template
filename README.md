[![Build Status](https://travis-ci.org/BPA-CSIRO-Workshops/handout-template.png?branch=master)](https://travis-ci.org/BPA-CSIRO-Workshops/handout-template)

Table of Contents
================
<!-- toc -->

* [Do You Belong Here?](#do-you-belong-here)
* [An Example Provided](#an-example-provided)
* [Starting a New Handout Project](#starting-a-new-handout-project)
  * [1. Installing Hub](#1-installing-hub)
  * [2. Create a New GitHub Repo Based on handout-template](#2-create-a-new-github-repo-based-on-handout-template)
* [Merge in Updates From handout-template](#merge-in-updates-from-handout-template)
* [Credits](#credits)
* [License](#license)

<!-- toc stop -->

Do You Belong Here?
===================
This README.md file contains nitty-gritty details of how to use this repository
for developing your own hands-on workshop handout. For example, you shouldn't
be scared off by the prospect of trying things like:

 * Cloning git repositories
 * Adding upstream remotes
 * Installing a LaTeX environment for building PDFs from the source LaTeX
 * Setting up Travis Continuous Integration (Travis-CI) for automating the PDF
   build process

The idea is to help you go from the barebones contents of this repository to a
fully-fledge LaTeX document like the one developed for an [NGS Workshop](https://github.com/BPA-CSIRO-Workshops/ngs-handout):

 * [Trainee Handout PDF](http://bpa-csiro-workshops.github.io/ngs-handout/pdfs-latest/trainee_handout.pdf)
 * [Trainer Handout PDF](http://bpa-csiro-workshops.github.io/ngs-handout/pdfs-latest/trainer_handout.pdf)

An Example Provided
===================
We have provided a short example [example.tex](example.tex) demonstrating the
main features. The PDFs built directly from this example can be found here:

 * [Trainee Example PDF](http://bpa-csiro-workshops.github.io/handout-template/pdfs-latest/trainee_example.pdf)
 * [Trainer Example PDF](http://bpa-csiro-workshops.github.io/handout-template/pdfs-latest/trainer_example.pdf)

Starting a New Handout Project
==============================
There are some established git and GitHub workflows when it comes to cloning a
repository. However, we can assume your planned future handout document
is going to differ significantly from the way this repository looks right now.

I recommend the following approach:

1. Installing Hub
-----------------
To install [`hub`](https://hub.github.com/) you first need to install `rake`, a ruby make-like utility. On Ubuntu this can be achieved using `apt-get`:

```bash
# Install rake
sudo apt-get install -y rake

# Clone and install hub
git clone https://github.com/github/hub.git
cd hub
sudo rake install prefix=/usr/local
```

Wherever we need to use `hub`, as opposed to `git`, we'll be explicit in the code which follows.

2. Create a New GitHub Repo Based on handout-template
-----------------------------------------------------

```bash
my_new_handout_project='my_new_handout'

# Clone the handout-template repo
hub clone --origin template BPA-CSIRO-Workshops/handout-template "${my_new_handout_project}"
cd "${my_new_handout_project}"

# Create a new project on GitHub to house your new handout project
hub create "${my_new_handout_project}"

# If you want to create the repository within an organisation, you can do something like:
# my_organisation='BPA-CSIRO-Workshops'; hub create "${my_organisation}/${my_new_handout_project}"

# Push the code into your newly created repository on GitHub
git push -u origin master
```

You can now modify the files and push the changes to your new GitHub repo:

```bash
git push
```

Merge in Updates From handout-template
======================================

The beauty of having the `handout-template` as an upstream, is that you can
easily pull in any changes from that repository:

```bash
# Fetch any changes from your own GitHub repository
git fetch origin

# Fetch any changes to the template
git fetch template

# Merge changes into your working directory
git merge template/master

# Push changes back to your own GitHub repository
git push
```

Credits
=======
This style was originally designed for the Next Generation Sequencing (NGS)
hands-on workshop developed by Bioplatforms Australia (BPA), CSIRO
Bioinformatics Core and the EBI. It was written predominantly by Nathan S.
Watson-Haigh.

License
=======
The contents of this repository are released under the Creative Commons
Attribution 3.0 Unported License. For a summary of what this means,
please see:
http://creativecommons.org/licenses/by/3.0/deed.en_GB

