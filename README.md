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
non-rotating star (the simplest model), the equations are:



## About MESA
MESA is an open-source one-dimensional stellar evolution code written mostly in Fortran.
For the first 10 years of its life it was primarily developed by Bill Paxton, along with in-
volvement from many other astrophysicists. Currently its actively maintained by a globally distributed
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

## Simulations

To build project files, go to root project directory and run
```bash
./mk 
```

To run the simulations, go to root project directory and run 
```bash
./rn
```
![High Mass Stellar Evolution](https://github.com/axr6077/Low-High-Mass-Star-Evolution/blob/main/high_mass/highmass_sim.gif)
