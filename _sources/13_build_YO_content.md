# Build Your Own Content

This section assists academics, and alike, in  build their content, by modifying this repository, or the original TU Berlin [repository](https://github.com/fneum/data-science-for-esm). Its primary purpose if for teaching, providing lectures and learning material, but can also be used for any other purpose. The first step is to fork this repository. By doing so, one is able to create his own website, similar to this one, with a tailor-made content, quickly and with ease.

This setup draws from the [peaceiris actions-gh-pages](https://github.com/peaceiris/actions-gh-pages), and [Stanford RC website](https://stanford-rc.github.io/rse-services/docs/resources/documentation). However, these serve only as a reference, as the the full explanation is given blow.

## Create a new fork

:::{note}

Before forking this repository please have the following in mind. In the `Create a new fork` pop-up menu, deselect the default **Copy the `main` branch only** option. By doing so, you will reduce further branch creation.

<img src='https://github.com/open-energy-transition/data-science-for-esm/raw/stanford/data-science-for-esm/_images/03_fork_option.png' alt='' width='80%'/>

:::

The first step is forking the repository, having the **Note** above in mind.

The following steps are:
- Create and push a branch named `stanford` - to be skipped if adhering to the **Note** above
- `gh-pages` branch will be automatically generated, as defined by the workflow in the `.github/workflows/deploy.yml` file  which will contain the required `HTML`, `css`, `.js`, and other files
- in the `.github/workflows/deploy.yml` file you also specify the branch, used by the workflow, which upon the `git push` command, is used for generating the required `HTML`, `css`, `.js`, as well as the other files - other than the `gh-pages`
- in the `data-science-for-esm/_toc.yml` file, a sequence of files to be included in the GitHub Page is defined, thereafter displayed in the menu, located on the left side of the page
- on preexisting knowledge disseminating the gained expertise by OET, and TU Berlin, to help .   Welcome to the website accompanying the course [Data Science for Energy System Modelling](https://moseskonto.tu-berlin.de/moses/modultransfersystem/bolognamodule/beschreibung/anzeigen.html;jsessionid=DQfixqzzpn1XIg5N1GG7S9um4EDykZn99AHmH6Fj.moseskonto?number=31027&version=1&sprache=2). This course is being developed by [Dr. Fabian Neumann](https://neumann.fyi) and offered as part of the curriculum of the [Department of Digital Transformation of Energy Systems at TU Berlin](https://www.tu.berlin/ensys).

In the your own foreked repository `owner/data-science-for-energy-system-modelling`, please go to the **Settings** -> **Pages**. in the GitHub Page, go to the Branch section, and change the selection from None to `main`, or any branch other than `gh-pages`. Once the branch has been selected, in a manner of minutes a custom  


<img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/04_gh_pages-options.png' width='100%'/>

<a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'>
<img src='/_images/04_gh_pages-options.png' width='100%'/>
</a>

:

- 
- 
- 
- 
- 
- 
- 
- 

## Installing the package manager `conda`

[open-source](https://opensource.org/)
_distribution_ and/or _package manager_

### Anaconda

[Anaconda Python Distribution](https://www.anaconda.com/download/).

For **Linux and MacOS users**, you can access the command line by opening the _terminal_ program.

For **Windows users**, you should first install Anaconda (described above) or miniconda (described below), which gives you access to the "Anaconda Prompt" desktop application. (Instructions for this are given on the [Anaconda Website](https://docs.anaconda.com/anaconda/user-guide/getting-started/#write-a-python-program-using-anaconda-prompt-or-terminal).)

From the Anaconda Prompt, you should be able to run `conda` and other shell commands.

### Lightweight `miniconda`

If you don't want to download a large file like the Anaconda Python Distribution (ca. 800 MB), there is a
lightweight alternative installation called `miniconda`.

- [Miniconda Installation](https://docs.conda.io/en/latest/miniconda.html)

### Google Colab

You can even start the course without a local Python installation using online services like  [Google Colab (colab.google)](https://colab.google) which provide an online Python version
in a [Jupyter Notebook](jupyter.org/) environment.

## Managing environments with `conda`

Python coupled with a package manager provides a way to make isolated,
reproducible _environments_ where you have fine-tuned control over all packages
and configuration.

First, ensure that your conda installation is up to date:

    conda update -n base -c conda-forge conda

To create a conda environment, you execute the following command:

    conda create --name my_environment python=3.11 numpy

To use this environment, simply "activate" it by executing:

    conda activate my_environment

You should now see the string `(my_environment)` prepended to your prompt.
Now, if you execute any Python-related tool from the
command line, it will first search in your environment.

To install additional packages into your environment:

    conda install <package-name>

Some packages are community-maintained (e.g. `conda-forge`) and require you to specify a different "channel":

    conda install -c conda-forge <package-name>

You can deactivate your environment by typing:

    conda deactivate

To see all the environments on your system:

    conda info --envs

To get a complete summary of all the packages installed in your environment, run

    conda list

If you want to permanently remove an environment and delete all the data
associated with it:

    conda env remove --name my_environment --all

A conda environment can also be defined through an `environment.yaml` file. With that file, a new environment with the exact
configuration can be installed by executing

    conda env create -f my_environment.yml

For extensive documentation on using environments, please see
[the conda documentation](https://conda.io/docs/using/envs.html).

## Environment for this course: `esm-2024`

### ... with `conda`

The latest environment specification for this course can be downloaded under the following link as a [`YAML`-file](https://en.wikipedia.org/wiki/YAML):

https://github.com/fneum/data-science-for-esm/blob/main/environment.yaml

There is a download button at the top-right corner.

After navigating to the folder where the `environment.yaml` file is stored,
you can reate this environment using `conda` (faster)

    conda env create -f environment.yaml

Activate this environment

    conda activate esm-2024

This environment should be sufficient for all of your work in this course.

The environment has to be activated whenever you open a new terminal,
*before* starting a new Jupyter window with

    jupyter lab

### ... with `pip`

If you want to use `pip` for managing your environment, download

https://github.com/fneum/data-science-for-esm/blob/main/requirements.txt

There is a download button at the top-right corner.

After navigating to the folder where the `requirements.txt` file is stored,
you can install the required packages with

    pip install -r requirements.txt

This should allow you to start a new Jupyter window:

    jupyter lab

## JupyterLab

[JupyterLab](https://jupyterlab.readthedocs.io) will be our primary method for
interacting with the computer. JupyterLab contains a complete environment for
interactive data science which runs in your web browser.

JupyterLab has excellent documentation. Rather than repeat that documentation
here, we point you to their docs. The following pages are particularly relevant:

- [The JupyterLab Interface](https://jupyterlab.readthedocs.io/en/stable/user/interface.html)
- [Working with Files](https://jupyterlab.readthedocs.io/en/stable/user/files.html)
- [The Text Editor](https://jupyterlab.readthedocs.io/en/stable/user/file_editor.html)
- [Notebooks](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html)
- [Terminals](https://jupyterlab.readthedocs.io/en/stable/user/terminal.html)
- [Managing Kernels and Terminals](https://jupyterlab.readthedocs.io/en/stable/user/running.html)

## Markdown

Throughout the course, you might want to write rich text documents using Markdown.
This is also very common in Jupyter Notebooks.
Here are some useful references on Markdown syntax.

- [Markdown Guide / Basic Syntax](https://www.markdownguide.org/basic-syntax)
- [Official Markdown Documentation](https://daringfireball.net/projects/markdown/)
