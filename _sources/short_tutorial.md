# Short tutorial

The installation procedure installs PyPSA-Earth model with all the
software dependencies needed to build and run it. To properly model any
region of the Earth, it is first crucial to get familiar with a tutorial
where a simpler model is considered. This section explains how to run
and analyze the tutorial model.

## Build the tutorial model

The user can explore the majority of the model\'s functions on a local
machine by running the tutorial, which uses fewer computational
resources than the entire model does. A tutorial data kit was developed
to facilitate exploring the model. You can build it using the tutorial
configuration file [config.tutorial.yaml]{.title-ref} (placed in the
project folder [pypsa-earth]{.title-ref}). By default, PyPSA-Earth reads
configuration parameters of simulation from [config.yaml]{.title-ref}
file located in [pypsa-earth]{.title-ref} folder. Thus, to run the
tutorial model, [config.tutorial.yaml]{.title-ref} needs to be stored as
\`config.yaml\`:

``` bash
.../pypsa-earth (pypsa-earth) % cp config.tutorial.yaml config.yaml
```

::: note
::: title
Note
:::

You may want to do a reserve copy of your current configuration file
([config.yaml]{.title-ref}) as it will be overwritten by a tutorial
configuration.
:::

In the configuration file [config.yaml]{.title-ref} there is a flag
[retrieve_databundle]{.title-ref} which triggers data loading and a
[tutorial]{.title-ref} flag which determines that the loaded data belong
to the tutorial kit. Currently the tutorial can be run only for Nigeria
(\"NG\"), Benin (\"BJ\"), Botswana (\"BW\") and Morocco (\"MA\").

``` yaml
tutorial: true
...
enable:
    retrieve_databundle: true
```

It\'s recommended to set [retrieve_databundle: true]{.title-ref} when
building the model for the first time to download all needed common data
files. When the first run is completed and all the necessary data are
extracted, it may be a good idea to set [retrieve_databundle:
false]{.title-ref} to avoid data loss.

## Run the model

After configuration set-up, the model is ready to be built and run.
Before to actually run the workflow you may check how it will look by
using [\--dryrun]{.title-ref} or [-n]{.title-ref} Snakemake option:

``` bash
.../pypsa-earth (pypsa-earth) % snakemake -j 1 solve_all_networks --dryrun
```

To run the whole modeling workflow you just need the following command:

``` bash
.../pypsa-earth (pypsa-earth) % snakemake -j 1 solve_all_networks
```

This command will trigger loading of the whole dataset needed to build
the model for a tutorial case if both [tutorial]{.title-ref} and
[retrieve_databundle]{.title-ref} flags are on. The tutorial model will
run simulation of power systems in Nigeria and Benin. Note that data
load will need about 1.6Gb and model building will take a while (about
20..50 minutes).

## Analyse the solved networks

The solved networks can be analysed just like any other PyPSA network
(e.g. in Jupyter Notebooks).

``` python
import pypsa

network = pypsa.Network("results/networks/elec_s_6_ec_lcopt_Co2L-4H.nc")
```

The video below shows how to analyse solved PyPSA-Eur networks in
Jupyter Notebooks. Fabian Neumann did a great job explaining the basics
of PyPSA and how to use it for analysis.

```{=html}
<iframe width="560" height="315" src="https://www.youtube.com/embed/mAwhQnNRIvs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```
We also prepared an example notebook such that you can explore the
tutorial network yourself. Just open in our [notebooks
repository](https://github.com/pypsa-meets-earth/documentation/tree/main/notebooks)
the file [sample-network-analysis.ipynb]{.title-ref}. For further
inspiration on what you can analyse and do with PyPSA, you can explore
the [examples section in the PyPSA framework
documentation](https://pypsa.readthedocs.io/en/latest/examples-basic.html).

After playing with the tutorial model and before playing with different
functions, it\'s important to clean-up data in your model folder before
to proceed further to avoid data conflicts. You may use the
[clean]{.title-ref} rule for making so:

``` bash
.../pypsa-earth (pypsa-earth) % snakemake -j 1 clean
```

Generally, it\'s a good idea to repeat the cleaning procedure every time
when the underlying data are changed to avoid conflicts between run
settings corresponding to different scenarios.

It is also possible to make manual clean-up removing folders
\"resources\", \"networks\" and \"results\". Those folders store the
intermediate output of the workflow and if you don\'t need them anymore
it is safe to delete them.

::: note
::: title
Note
:::

This tutorial only covers Nigeria. To make the workflow run on other
regions you need to use the `config.default.yaml` as `config.yaml`. To
use the model in and outside Africa, you should also read [How to create
a model for you region of interest with
PyPSA-Earth?](https://github.com/pypsa-meets-earth/pypsa-earth/discussions/505)
:::

`tutorial`{.interpreted-text role="ref"} section elaborates on building
and running a full PyPSA-Earth model.
