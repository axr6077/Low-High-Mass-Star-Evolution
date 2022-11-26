# Low-High-Mass-Star-Evolution
## Introduction
Stellar evolution codes are one of the basic building blocks of stellar astrophysics. These
codes model the interior of a star and then evolve that model over time so we can test our
understanding of the physics of stars. Stellar codes help us understand processes that happen
too deep inside a star for us to observe, as well as processes that happen too quickly to be
observed. They help us refine our understanding of atomic physics, nuclear physics, hydro-
dynamics, and thermodynamics and even make predictions about galaxies or our Universe
as a whole.

## Some Math
Stars are governed by the equations of stellar structure along with equations that dictate
the mixing and nuclear burning of chemical elements. For a spherically symmetric and
non-rotating star (the simplest model), the equations are (use light theme if its not visible):

![eq1](https://github.com/axr6077/Low-High-Mass-Star-Evolution/blob/main/equations/eq1.svg)

![eq2](https://github.com/axr6077/Low-High-Mass-Star-Evolution/blob/main/equations/eq2.svg)

![eq3](https://github.com/axr6077/Low-High-Mass-Star-Evolution/blob/main/equations/eq3.svg)

![eq4](https://github.com/axr6077/Low-High-Mass-Star-Evolution/blob/main/equations/eq4.svg)

![eq5](https://github.com/axr6077/Low-High-Mass-Star-Evolution/blob/main/equations/eq5.svg)

Dont worry, MESA will do everything internally!

## About MESA
MESA is an open-source one-dimensional stellar evolution code written mostly in Fortran.
For the first 10 years of its life it was primarily developed by Bill Paxton, along with involvement from many other astrophysicists. Currently its actively maintained by a globally distributed
community. 

## Installation

The MESA-sdk can be found [here](https://docs.mesastar.org/en/release-r22.05.1/quickstart.html).

<p>

#### Minimum System Requirements from the [MESA Project Page](https://docs.mesastar.org/en/release-r22.05.1/installation.html):

- MacOS or GNU/Linux
- 64-bit processor
- 8 GB RAM
- 20 GB free disk space

#### Windows Users:
- [Mesa-Docker](https://github.com/evbauer/MESA-Docker) contains pre-built version inside a container. 
- [WSL2](https://learn.microsoft.com/en-us/windows/wsl/install) installs an instance of Linux within Windows where MESA can be built. 

Windows doesn't have pgplot for visualization. To access it install [VcXsrv Windows X Server](https://sourceforge.net/projects/vcxsrv/).

</p>
</details>

## Build

To build project files, go to root project directory and run
```bash
./mk 
```

## Demo
To run the simulations, go to root project directory and run 
```bash
./rn
```
You should see a pgplot after a couple minutes like this:

![High Mass Stellar Evolution](https://github.com/axr6077/Low-High-Mass-Star-Evolution/blob/main/high_mass/highmass_sim.gif)

The simulations will take a while to run. MESA ends a simulation either when it can’t converge the model anymore, or when it
reaches a specified stopping condition. Your model should stop with a message in your
terminal similar to 
```shell
stopping because of problems dt < min_timestep_limit
```
If you see a different message, e.g., something about hydrodynamics, then something has
gone wrong.

## Run Configurations

In the `inlist_project` file the following parameters may be changed to simulate custom parametric simulations:
- Under `&star_job`: `pgstar_flag = .true` tells MESA to have live plots on screen. If you want the plots running in background set `pgstar_flag = .false`
- Under `&controls`: 
  - `initial_mass` sets the initial mass of the star in the simulation in solar masses. For the purpose of this repository it was set to 2 and 40 respectively for low and high mass stars.
  - `initial_z` sets the star's metallicity as a percentage (Z = 0.02 is solar metallicity). In this repository, for low mass star, it was set to 0.02 and for high mass star, it was set to 0.01. 
  - `! when to stop` puts an exit condition to the simulation. `xa_central_lower_limit_species(1) = ‘h1’` tells MESA to stop when the
central mass fraction of H1 drops below a user-defined limit.
`xa_central_lower_limit(1) = 1d-3` tells MESA that the user-defined limit is
0.001. Since the main sequence ends when central hydrogen is exhausted, this
tells MESA to end the simulation at the terminal age main sequence (TAMS).

## MESA Output Analysis
MESA outputs several files to use, all located in the LOGS folder. The `history.data`
file gives the parameters at each timestep of the model. The profile files (named `profileN.dat`
with N is an integer counting up from 1) give information about the internal structure of
the model at a given timestep. The `profiles.index` file shows which profiles map to which
stellar models. The outputs can be plotted using Python, Matlab or any data analysis language of your choice. 

#### Python Analysis



## Contributions
Feel free to create a pull request. 
