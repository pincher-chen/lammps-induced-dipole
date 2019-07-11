## LAMMPS
**Adapt the code of [lammps-induced-dipole-polarization-pair-style][polarization] to the 12Dec18 version of [lammps]**

## Build & Run
The following package should be installed firstly.
```
$ make package-status | grep YES
Installed YES: package KSPACE
Installed YES: package MOLECULE
Installed YES: package RIGID
```

```shell
#by cmake
mkdir -p build && cd build
cmake ../cmake/ -DPKG_MOLECULE=ON -DPKG_KSPACE=ON -DPKG_RIGID=ON
make -j8
```
```
#by make
$module load intel-compilers/15.0.1
$make intel_cpu_mpich

```

## Acknowledgements
Special thanks to the contributors:
 - [aurix](https://github.com/aurix) - [lammps-induced-dipole-polarization-pair-style][polarization]
 - [lammps](http://lammps.sandia.gov/) - [lammps][lammps]


[lammps]: https://github.com/lammps/lammps
[polarization]: https://github.com/aurix/lammps-induced-dipole-polarization-pair-style

