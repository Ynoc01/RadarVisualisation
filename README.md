# RadarVisualisation
Radar display nc format

## Getting Started

## Installation

### Windows

As a prerequisite to be able to run the visualisation correctly, python 3.9 is required. In addition to the following libraries:

- proplot(v.0.9.7)
- matplotlib(v.3.4.3)
- xarray

It is also advisable to create a conda environment to be able to use these libraries without modifying your computer. To be able to run in a conda environment you need to have PATH enabled in python beforehand.

Creating the environment with python 3.9. We create the myenv environment:

```sh
conda create --name myenv python=3.9
```

We activate the environment:

```sh
conda activate myenv
```

We install the specific versions of the packages, also for this example we will run from jupyter notebook:

```sh
conda install -c conda-forge proplot=0.9.7
conda install -c conda-forge matplotlib=3.4.3
conda install -c conda-forge xarray
conda install -c conda-forge notebook
conda install -c anaconda ipykernel
```

Register the environment in Jupyter:

```sh
python -m ipykernel install --user --name myenv --display-name "Python (myenv)"
```

Initialise jupyter:

```sh
jupyter notebook
```

To close the environment just type Control+C to load jupyter and finally close the environment:

```sh
conda deactivate
```


