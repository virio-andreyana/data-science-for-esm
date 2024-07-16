<!-- # Table of Contents

1. [BYOC](#build-your-own-content)
1. [New Fork](#creating-a-new-fork)
1. [GH Pages](#gh-pages-setup)
1. [GH Workflows Deployment](#gh-workflows-deployment) -->


# Build Your Own Content

<!-- ###### List of Abbreviation[^bignote] -->

This section assists academics, and alike, in build their content, by modifying this repository, or the original [Dr. F. Neumann's repository][01].

* Its primary purpose if helping/guiding on building a GitHub page, to be used for generating learning material, i.e. lectures, or similar.
* It can also be used for any other purpose, for that matter.
* This setup draws from the [peaceiris actions-gh-pages][02], and the [Stanford RC website][03]. However, these serve only as a reference, as the the full explanation is blow.

The first step is forking this repository. By doing so, one is able to create his own website, similar to this one, with a tailor-made content, quickly and with ease. However, there are two or three thing to keep in mind when doing so, so please read on.


# <font color="darkgreen">Creating a new fork of this repository</font>

> **Note:** The first step is forking the repository, having the below in mind.

Before forking this repository please have the following in mind. In the <mark>Create a new fork</mark> pop-up menu, shown in the figure below, **deselect** the default **Copy the `main` branch only** option. By doing so, you will reduce further branch creation, necessary for this to work.

:::{note}
<center>
<figure>
    <a href='https://github.com/open-energy-transition/data-science-for-esm/fork'>
    <img src='https://github.com/open-energy-transition/data-science-for-esm/raw/stanford/data-science-for-esm/_images/03_fork_option.png' alt='' width='95%' style='vertical-align:middle;border:5px solid goldenrod;margin:20px 0px' />
    </a>
    <figcaption>Clicking on the image above will lead directly to the <strong><b><mark>Create a new fork</mark></b></strong> menu</figcaption>
</figure>
</center>
:::

> **Note:** The key point is to have a `stanford` branch.

* Alternatively, `stanford` branch can be created locally and push - however, this is to be skipped if adhering to the **Note** above.
* `gh-pages` branch will be automatically generated, as defined by the workflow, hence its creation is not required.
* It is also **not** required to have the `gh-pages` locally, as it hosts only the website files, and is taken care by the workflow.

The remote `gh-pages`, itself, hosts the required `HTML`, `css`, `.js`, and the other files, used for generating the `github.io` website. Hence, there is no requirement for having the branch locally. (repetitive)

These will be generated, upon a successful workflow execution, every time `git push` is performed, in the prior specified git branch. How this is specified, is explained [below](#deployment-setup).

<!-- of the forked repository, in the `.github/workflows/deploy.yml` ([link][07]) file which will contain the required `HTML`, `css`, `.js`, and other files
is used for generating the required `HTML`, `css`, `.js`, as well as the other files - other than the `gh-pages`

- on preexisting knowledge disseminating the gained expertise by OET, and TU Berlin, to help .   Welcome to the website accompanying the course [Data Science for Energy System Modelling][04]. This course is being developed by [Dr. F. Neumann][05] and offered as part of the curriculum of the [Department of Digital Transformation of Energy Systems at TU Berlin][06]. -->


# <font color="darkgreen">GitHub Pages Setup</font>

In the your own forked repository `"owner"/data-science-for-energy-system-modelling`, please go to the GitHub **Settings** -> **Pages**. In the **GitHub Pages**, go to the Branch section, and change the selection from `None` to `gh-pages/root`. Once the branch has been selected, in a manner of minutes a custom URL will be provided: **"Your site is live at [https://...](https://open-energy-transition.github.io/data-science-for-esm/)"**

<center>
<figure>
    <a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'>
    <img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/04_gh_pages-options.png' width='97%'style='vertical-align:middle;border:5px solid darkgreen;margin:30px 30px' />
    </a>
    <figcaption>Clicking on the image above will lead directly to the <strong><b><mark>GitHub Pages</mark></b></strong> settings menu</figcaption>
</figure>
</center>


# <font color="darkgreen">Deployment Setup</font>

> **Note:** The key point is set the correct deployment branch set in the <code>./github/workflows/deploy.yml</code>.

* in the <code>.github/workflows/deploy.yml</code> file specify the branch, which will later be used by the workflow, which upon the `git push` command, triggers the workflow:
    ~~~
    push:
      branches:
      - stanford
    ~~~


# <font color="darkgreen">Content Modification Setup</font>

The website logo, as well as the other figures can be placed in the `data-science-for-esm/_images/` folder. The content in terms od the `.ipynb` & `.md` files are to be placed in the root of the `data-science-for--esm` folder, and specified in the `_toc.yml` file. If not being placed in the root, the workflow will be unable to locate the files specified in the `_toc.yml`, resulting in the unsuccessful deployment, and not accessible `github.io` site.

Both `_config.yml`, as well as the `_toc.yml``are to remain in the root of the `data-science-for esm` folder. In the `_config.yml` details of the website, such as the author, logo, other relevant links to GitHub, Google Collab, can be defined. Please use the already provided `_toc` and `_config.yml` files as a template, and follow the provided structure.

- in the `data-science-for-esm/_toc.yml` *file*, a sequence of files to be included in the GitHub Page is defined, thereafter displayed in the menu, located on the left side of the page

# <font color="darkgreen">GitHub Workflows Deployment</font>

`.github/workflows/deploy.yml` ([link][08]) needs specifying which branch of the repo will be used for deployment. You are free to use any branch, other than the `gh-pages`, keeping in mind that upon the `git push`, the workflow will be triggered.

This is indicated by the status indicator in the repository, in this case a beige-brown dot, which if clicked on, will show the running status and the deployment details. As mentioned, the deployment takes approx. 2 minutes.

<center>
<figure>
    <!-- <a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'> -->
    <img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/05_deployment_status.png' width='85%'style='vertical-align:middle;border:5px solid paleturquoise;margin:30px 30px' />
    <!-- </a> -->
    <figcaption>Deployment status upon <code>git push</code> to the branch specified in the <em>deploy.yml</em> file</figcaption>
</figure>
</center>

Upon a successful deployment, indicated by the deploy status, in that time you should be able to see the changes taking place in the specified `github.io` URL.

<center>
<figure>
    <!-- <a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'> -->
    <img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/06_successful_deployment.png' width='85%'style='vertical-align:middle;border:5px solid paleturquoise;margin:30px 30px' />
    <!-- </a> -->
    <figcaption>Successful deployment, after a finalized <code>jupyter book build</code> run</figcaption>
</figure>
</center>

<!-- # References -->
[01]: https://github.com/fneum/data-science-for-esm
[02]: https://github.com/peaceiris/actions-gh-pages
[03]: https://stanford-rc.github.io/rse-services/docs/resources/documentation
[09]: https://github.com/open-energy-transition/data-science-for-esm/fork
[10]: https://github.com/open-energy-transition/data-science-for-esm/settings/pages
[04]: https://moseskonto.tu-berlin.de/moses/modultransfersystem/bolognamodule/beschreibung/anzeigen.html;jsessionid=DQfixqzzpn1XIg5N1GG7S9um4EDykZn99AHmH6Fj.moseskonto?number=31027&version=1&sprache=2
[05]: https://neumann.fyi
[06]: https://www.tu.berlin/ensys
[07]: https://github.com/open-energy-transition/data-science-for-esm/blob/ef394898e3100e2bd2d074a8b2da89235355cd4e/.github/workflows/deploy.yml
[08]: https://github.com/open-energy-transition/data-science-for-esm/blob/6c6563e15d3035647e9e52c852fa1cd5748f15ed/.github/workflows/deploy.yml#L4C2-L7C15

<!-- <center><mark>Table of Abbreviations</mark></center> -->
<!-- ###### Table of Abbreviations -->

[^bignote]: | Acronym     | Description |
    |:-----------:|:-----------:|
    | **GH**      | GitHub      |
    | **repo**    | repository  |