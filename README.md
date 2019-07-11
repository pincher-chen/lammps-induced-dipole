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
It should be note that only serial execute can be run.
```
$ cd /examples/induced-dipole/Bulk H2
$ yhrun -pdocker_128 -n 1 ~/sf_box/lammps-PIM4/lammps/src/lmp_intel_cpu_mpich -in h2.input
LAMMPS (4 Jan 2019)
OMP_NUM_THREADS environment is not set. Defaulting to 1 thread. (../comm.cpp:87)
  using 1 OpenMP thread(s) per MPI task
Reading data file ...
  orthogonal box = (-10.7974 -10.7974 -10.7974) to (10.7974 10.7974 10.7974)
  1 by 1 by 1 MPI processor grid
  reading atoms ...
  750 atoms
  scanning bonds ...
  4 = max bonds/atom
  reading bonds ...
  600 bonds
Finding 1-2 1-3 1-4 neighbors ...
  special bond factors lj:   0          0          0         
  special bond factors coul: 0          0          0         
  4 = max # of 1-2 neighbors
  3 = max # of 1-3 neighbors
  3 = max # of 1-4 neighbors
  4 = max # of special neighbors
Setting atom values ...
  150 settings made for static_polarizability
Setting atom values ...
  300 settings made for static_polarizability
Setting atom values ...
  300 settings made for static_polarizability
150 rigid bodies with 750 atoms
EwaldDisp initialization ...
  G vector = 0.219679,   accuracy = 0.0332064
Neighbor list info ...
  update every 1 steps, delay 10 steps, check yes
  max neighbors/atom: 2000, page size: 100000
  master list distance cutoff = 12.7974
  ghost atom cutoff = 12.7974
  binsize = 6.39872, bins = 4 4 4
  2 neighbor lists, perpetual/occasional/extra = 2 0 0
  (1) pair lj/cut/coul/long/polarization, perpetual
      attributes: half, newton on
      pair build: half/bin/newton
      stencil: half/bin/3d/newton
      bin: standard
  (2) pair lj/cut/coul/long/polarization, perpetual, copy from (1)
      attributes: half, newton on
      pair build: copy
      stencil: none
      bin: none
Setting up Verlet run ...
  Unit style    : real
  Current step  : 0
  Time step     : 1
  vectors: nbox = 4, nkvec = 128
Per MPI rank memory allocation (min/avg/max) = 19.13 | 19.13 | 19.13 Mbytes
Step TotEng KinEng PotEng E_vdwl E_coul E_long E_pol Temp Press 
       0    202.61103    226.42419   -23.813156   -23.427106    5158.6145   -5158.8882  -0.11226309    305.06274    2084.1534 
       1    202.62011     226.3899   -23.769794   -23.397525    5158.6262   -5158.8878  -0.11072426    305.01655    521.68055 
       2    202.78721    226.32304   -23.535822   -23.336418     5158.797   -5158.8872  -0.10920535    304.92646    527.49824 
       3    202.85466    226.22592    -23.37126   -23.256304    5158.8795   -5158.8866  -0.10780101    304.79562    531.21953 
       4    202.90416    226.09978   -23.195617   -23.146307    5158.9433    -5158.886  -0.10656974    304.62567    535.19806 
       5    202.74336    225.94664   -23.203277   -23.014909    5158.8025   -5158.8853  -0.10555976    304.41934    533.94308 
       6    202.88368    225.76848   -22.884796   -22.861137    5158.9658   -5158.8847  -0.10478023     304.1793    542.60338 
       7    202.74949    225.56349   -22.813998    -22.68232    5158.8567   -5158.8841  -0.10427068    303.90312    543.97044 
       8    202.82228    225.33298   -22.510702   -22.476642    5158.9537   -5158.8837  -0.10411492    303.59255     552.4537 
       9     202.6741    225.07847   -22.404371     -22.2442    5158.8273   -5158.8833  -0.10419452    303.24965    555.21747 
      10    202.69657    224.79662   -22.100047   -21.982647    5158.8702   -5158.8831  -0.10456272    302.86991     564.0518 
Loop time of 1.58275 on 1 procs for 10 steps with 750 atoms

Performance: 0.546 ns/day, 43.965 hours/ns, 6.318 timesteps/s
100.7% CPU use with 1 MPI tasks x 1 OpenMP threads

MPI task timing breakdown:
Section |  min time  |  avg time  |  max time  |%varavg| %total
---------------------------------------------------------------
Pair    | 1.5583     | 1.5583     | 1.5583     |   0.0 | 98.46
Bond    | 6.6757e-06 | 6.6757e-06 | 6.6757e-06 |   0.0 |  0.00
Kspace  | 0.01163    | 0.01163    | 0.01163    |   0.0 |  0.73
Neigh   | 0          | 0          | 0          |   0.0 |  0.00
Comm    | 0.00055695 | 0.00055695 | 0.00055695 |   0.0 |  0.04
Output  | 0.01042    | 0.01042    | 0.01042    |   0.0 |  0.66
Modify  | 0.0016067  | 0.0016067  | 0.0016067  |   0.0 |  0.10
Other   |            | 0.0002024  |            |       |  0.01

Nlocal:    750 ave 750 max 750 min
Histogram: 1 0 0 0 0 0 0 0 0 0
Nghost:    6971 ave 6971 max 6971 min
Histogram: 1 0 0 0 0 0 0 0 0 0
Neighs:    245758 ave 245758 max 245758 min
Histogram: 1 0 0 0 0 0 0 0 0 0

Total # of neighbors = 245758
Ave neighs/atom = 327.677
Ave special neighs/atom = 4
Neighbor list builds = 0
Dangerous builds = 0
Total wall time: 0:00:02
```



## Acknowledgements
Special thanks to the contributors:
 - [aurix](https://github.com/aurix) - [lammps-induced-dipole-polarization-pair-style][polarization]
 - [lammps](http://lammps.sandia.gov/) - [lammps][lammps]


[lammps]: https://github.com/lammps/lammps
[polarization]: https://github.com/aurix/lammps-induced-dipole-polarization-pair-style

