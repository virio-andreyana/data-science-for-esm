# Build Your Own Content

This section assists academics, and alike, in  build their content, by modifying this repository, or the original TU Berlin [repository][1].

* Its primary purpose if for teaching, providing lectures and learning material, but can also be used for any other purpose. The first step is to fork this repository.

By doing so, one is able to create his own website, similar to this one, with a tailor-made content, quickly and with ease.

- This setup draws from the [peaceiris actions-gh-pages][2], and [Stanford RC website][3]. However, these serve only as a reference, as the the full explanation is given blow.

## Create a new fork

:::{note}

Before forking this repository please have the following in mind. In the `Create a new fork` pop-up menu, deselect the default **Copy the `main` branch only** option. By doing so, you will reduce further branch creation.

<a href='https://github.com/open-energy-transition/data-science-for-esm/fork'>
<img src='https://github.com/open-energy-transition/data-science-for-esm/raw/stanford/data-science-for-esm/_images/03_fork_option.png' alt='' width='95%' style='vertical-align:middle;border:5px solid goldenrod;margin:20px 0px' />
</a>

:::
[:joy]
[]
[x]

The first step is forking the repository, having the **Note** above in mind.

The following steps are:
- Create and push a branch named `stanford` - to be skipped if adhering to the **Note** above
- `gh-pages` branch will be automatically generated, as defined by the workflow in the `.github/workflows/deploy.yml` file  which will contain the required `HTML`, `css`, `.js`, and other files
- in the `.github/workflows/deploy.yml` file you also specify the branch, used by the workflow, which upon the `git push` command, is used for generating the required `HTML`, `css`, `.js`, as well as the other files - other than the `gh-pages`
- in the `data-science-for-esm/_toc.yml` file, a sequence of files to be included in the GitHub Page is defined, thereafter displayed in the menu, located on the left side of the page
- on preexisting knowledge disseminating the gained expertise by OET, and TU Berlin, to help .   Welcome to the website accompanying the course [Data Science for Energy System Modelling](https://moseskonto.tu-berlin.de/moses/modultransfersystem/bolognamodule/beschreibung/anzeigen.html;jsessionid=DQfixqzzpn1XIg5N1GG7S9um4EDykZn99AHmH6Fj.moseskonto?number=31027&version=1&sprache=2). This course is being developed by [Dr. Fabian Neumann](https://neumann.fyi) and offered as part of the curriculum of the [Department of Digital Transformation of Energy Systems at TU Berlin](https://www.tu.berlin/ensys).

In the your own forked repository `owner/data-science-for-energy-system-modelling`, please go to the **Settings** -> **Pages**. in the GitHub Page, go to the Branch section, and change the selection from None to `main`, or any branch other than `gh-pages`. Once the branch has been selected, in a manner of minutes a custom  

## GitHub Pages Setup

<a href='https://github.com/open-energy-transition/data-science-for-esm/settings/pages'>
<img src='https://raw.githubusercontent.com/open-energy-transition/data-science-for-esm/stanford/data-science-for-esm/_images/04_gh_pages-options.png' width='97%'style='vertical-align:middle;border:5px solid goldenrod;margin:30px 30px' />
</a>

# References

[1]: https://github.com/fneum/data-science-for-esm
[2]: https://github.com/peaceiris/actions-gh-pages
[3]: https://stanford-rc.github.io/rse-services/docs/resources/documentation
[4]: 
[5]: 