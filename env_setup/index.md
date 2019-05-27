# Environment setup

## Requirements

Please install the following software:

**Warning**: You may need a few Gb of space in your hard drive (10Gb should be enough)
to accommodate software and data so please make sure you have some room before continuing!

* [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Docker](https://docs.docker.com/install/)
* [Google Cloud SDK](https://cloud.google.com/sdk/)
* [Python 3.7](https://www.python.org/downloads/)
* [Miniconda for Python 3.7](https://docs.conda.io/en/latest/miniconda.html)
* [GNU make](https://www.gnu.org/software/make/) (Installation instructions depend greatly on your OS. If you are on MacOS, 
the simplest way is need to install XCode, if you are on other Linux distributions it may be already installed)
* If you are on MacOS, sooner than later you may need to install the Developer Tools (search for `XCode` in the app store)

Also, you will need to create a `github.com` user if you don't have one. 
You may want to setup `SSH` key based authentication for github for convenience.

## Conda environment setup

(This step is to be run after you have installed the `Miniconda` software from the
previous section)

In order to manage the different packages we will use during the course,
we will create a conda environment from the provided configuration file:

```bash
wget https://raw.githubusercontent.com/mlinproduction/mlinproduction.github.io/master/env_setup/env_setup.tar
tar -xvf env_setup.tar
conda env create -f ml_in_prod_env.yml 
```

Whenever we want to run any piece of code, we just need to make sure
that this environment is active:

```bash
conda activate ml_in_prod
```

If you need to install additional packages, please remember to make sure that 
your conda environment is activated prior to running `conda install` or `pip install`. 
This will ensure that the packages are installed in the `ml_in_prod` environment
instead of your base environment or your system's python libraries.

*Tip*: If you install additional packages and would like to export the configuration
so that you can create an environment from it, you can run `conda env export > ml_in_prod_env.yml`

## Jupyter notebook setup

In order to set up a Jupyter Notebook kernel under the `ml_in_prod` environment
please run:

```bash
conda activate ml_in_prod
ipython kernel install --user --name="ml_in_prod"
```

## Testing your environment

Please run the following environment testing script, which tests
whether the main libraries and tools can be imported correctly.

**Note**: One of the tests will ask for your password. It's expected!
```bash
# In the same folder where you ran the steps for `Conda environment setup`
conda activate ml_in_prod
python env_test/env_test.py
```

[.](env_setup.tar)
