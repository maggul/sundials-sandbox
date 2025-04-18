# sundials-sandbox
Template repository for codes that utilize SUNDIALS.

This includes simple implementations of customized N_Vector and SUNLinearSolver modules, along with testing routines for each.  It also includes five SUNDIALS examples, to serve as templates for codes that utilize the ARKODE and CVODE integrators from SUNDIALS:

* N_Vector module: `nvector_serialcomplex.h` and `nvector_serialcomplex.c`, with testing routine `testComplexNVector.c`.

* SUNLinearSolver modules: `sunlinsol_sptfqmrcomplex.h` and `sunlinsol_sptfqmrcomplex.c`, with testing routine `test_SPTFQRM.c`,
                           `sunlinsol_pcgcomplex.h` and `sunlinsol_pcgcomplex.c`, with testing routine `test_PCG.c`

This repository provides a simple `CMakeLists.txt` file to compile each of the above codes against a given SUNDIALS installation.

This setup assumes out-of-source builds, and requires that the path for the installed `SUNDIALSConfig.cmake` file be held in the CMake variable  `SUNDIALS_DIR`.  For example, from within this directory:

```
mkdir build
cd build
cmake -DSUNDIALS_DIR=/usr/local/sundials/lib/cmake/sundials ..
make
```

This has been tested using SUNDIALS v7.1.0.  Older SUNDIALS installations may be used by changing to a different branch:

* `main`: designed to work with SUNDIALS v7.1.0 (should work with any v > v7.1.x)

