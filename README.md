# RadarVisualisation
Radar display nc format

## Getting Started

## Installation

As a prerequisite to be able to run the visualisation correctly, python 3.9 is required. In addition to the following libraries:

- proplot(v.0.9.7)
- matplotlib(v.3.4.3)
- xarray

It is also advisable to create a conda environment to be able to use these libraries without modifying your computer. To be able to run in a conda environment you need to have PATH enabled in python beforehand.

### Windows and Linux

For both windows and Linux installation is almost the same except for details of masyusculas when installing.

Creating the environment with python 3.9. We create the myenv environment:

```sh
conda create --name myenv python=3.9
```

We activate the environment:

```sh
conda activate myenv
```

We install the specific versions of the packages. 

```sh
conda install -c conda-forge pandas
conda install -c conda-forge numpy
conda install -c conda-forge filterpy
conda install -c conda-forge proplot=0.9.7
conda install -c conda-forge matplotlib=3.4.3
conda install -c conda-forge xarray
conda install -c conda-forge scipy

```


Now we have different options depending on the program to be used. In the case of Jupyter notebook:

```sh
conda install -c conda-forge notebook
conda install -c anaconda ipykernel
python -m ipykernel install --user --name myenv --display-name "Python (myenv)"
```

Initialise jupyter:

```sh
jupyter notebook
```
In the case of Spyder we have:

```sh
conda install spyder
conda install spyder-kernels
```

Initialise Spyder (Windows)

```sh
Spyder
```
Initialise Spyder (Linux)

```sh
spyder
```
Alias on Linux for use conda(actualizar)
```sh
conda_start
```

for Visual studio is similar to spyder but you don't need to load a kernel to use it, just open in terminal after initializing myenv:

```sh
code .
```

# Usage
This code generates visualisations from radar data in NetCDF format. The steps for using the main function are described below:

Input arguments:
- input_file: NetCDF (.nc) format file containing the radar data.

Functionality:

The code generates two main graphs:

- Equivalent Reflectivity: Displays radar reflectivity in decibels (dBZ), allowing visualisation of precipitation intensity.
- Falling Speed: Displays the falling speed of hydrometeors in metres per second (m/s).

Customisation:

The code allows customisation of the colours used in the graphics, which facilitates the visual identification of meteorological phenomena such as convection, liquid rain, and ice crystals.

Example

To visualise radar data:

- Provide the NetCDF file as input and the output directory where the graphics will be saved.
- The generated graphs will include reflectivity and fall speed of hydrometeors.


```sh
new_time = pd.to_datetime(ds.time.values)
xlim = [new_time[0], new_time[-1]
heights = ds.height[0, :] + 500
Ze = ds['attenuated_radar_reflectivity'].T
Vf = ds['fall_velocity'].T
plot_mrr2(xlim, pd.to_datetime(ds.time.values), heights, Ze, Vf, hora_local=False)
```


