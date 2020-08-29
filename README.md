## SeDuMi: Optimization over symmeric cones

[![Build Status](https://travis-ci.org/sqlp/sedumi.svg?branch=master)](https://travis-ci.org/sqlp/sedumi)

SeDuMi is a Matlab package for solving convex optimization problems involving linear equations and inequalities, second-order cone constraints, and semidefinite constraints (linear matrix inequalities). The original version was developed by Jos. F. Sturm, who sadly passed away in 2003. Development continued under the direction of [Prof. Tamás Terlaky](http://coral.ise.lehigh.edu/terlaky/) by former Ph.D. students Imre Pólik and Oleksandr Romanko. 

Of course, like many open-source projects, it has benefitted considerably from contributions by others, including the developers of [YALMIP](https://yalmip.github.io/) and [CVX](http://cvxr.com), two modeling frameworks for optimization that use SeDuMi as a solver. The authors of these packages co-administer this repo, along with [Jonathan Currie](http://www.i2c2.aut.ac.nz/) from AUT University.

Please note that this is an *unofficial* repository for SeDuMi. The [official SeDuMi site](http://sedumi.ie.lehigh.edu/) is hosted by the [CORAL Lab](http://coral.ise.lehigh.edu/) at the [Department of Industrial and Systems Engineering](https://engineering.lehigh.edu/ise) at [Lehigh University](https://www.lehigh.edu/). *We do not intend for this repository to remain a permanent fork from the official SeDuMi release.* All improvements that we make here are communicated to the official SeDuMi maintainers for inclusion in the official release.

You are welcome to submit bug reports on the [GitHub issue page](https://github.com/sedumi/sedumi/issues). We cannot guarantee that they will be addressed in a timely fashion, we will do our best.

This version of SeDuMi is distributed under the [GNU General Public License 2.0](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html).


!!!WARNING!!!

As of 29th August SeDuMi does not compile on my Fedora 32 system with openblas-0.3.10-4.fc32.x86_64:
```
------------------------------------------------------------------------
SeDuMi installation script
   Directory: /usr/local/octave-5.2.0/share/octave/5.2.0-robj/site/m/SeDuMi
   Octave 5.2.0-robj on x86_64-pc-linux-gnu
---------------------------------------------------------------------------
Looking for existing binaries...none found; building...
Attempting to recompile the SeDuMi binaries:
Template: mex -O2 -DOCTAVE -Wall -I/usr/include/openblas %s 
   bwblkslv.mex:   bwblkslv.c sdmauxFill.c sdmauxRdot.c
In file included from blksdp.h:41,
                 from bwblkslv.c:45:
/usr/include/openblas/f77blas.h:476:5: error: unknown type name ‘bfloat16’; did you mean ‘_Float16’?
  476 |     bfloat16 *, blasint *, bfloat16 *, blasint *, float *, float *, blasint *);
      |     ^~~~~~~~
      |     _Float16
```
bfloat16 is a  Brain floating-point format that is defined for
GCC ARM compilers. My solution was to downgrade to the
openblas-0.3.9-2.fc32.x86_64 package.
