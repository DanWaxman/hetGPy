## hetGPy: Heteroskedastic Gaussian Process Modeling in Python

`hetGPy` is a Python implementation of the `hetGP` R library.

This package is designed to be a "pure" Python implementation of `hetGP`, with the goals of:
*	Matching the behavior of the `R` package
*	Having minimal dependencies (i.e. `numpy` and `scipy`)

The motivation for such a package is due to the rising popularity of implementing simulation models (also known as computer experiments) in Python. 


## Installing and Environments

* `hetGPy` is not yet available as a compiled package on pypi, but you can build the package by doing the following, but you may install with `pip`. Assuming you have python 3.10 or later installed, you can do one of the two options:

### To Install and use `hetGPy`:
* For simply using the package (but not the source code)
```
python3.10 -m pip install git+https://github.com/davidogara/hetGPy.git
```

### To Install and use `hetGPy`:

* To build from the source files:

1. Clone the repository. Make sure to include `--recurve-submodules` if you do not already have `Eigen` installed on your system:

```
git clone --recurse-submodules https://github.com/davidogara/hetGPy.git
```

2. With `hetGPy` as your current working directory:
```
pip install -e .
```

We recommend installing in a virtual environment. One way to do this with `venv` is:
```
python3.10 -m venv .venv
```

After this you should be able to run the examples in the `examples` folder.



## Note on Dependencies
*	`hetGPy` requires `scipy>=1.14.0` which fixed a [memory leakage issue](https://github.com/scipy/scipy/issues/20768) when using `L-BFGS-B` in `scipy.optimize.minizmize`. That version of scipy requires Python 3.10. 

*	Since `hetGPy` is designed for large-scale problems, this was chosen as a necessary feature. Experienced users may be able to roll back some of the dependencies, but this is not the recommended use.

*	`hetGPy` also requires a c++17 compiler for the underlying covariance functions.


## Contact
For questions regarding this package, please contact:  
David O'Gara  
Division of Computational and Data Sciences, Washington University in St. Louis  
david.ogara@wustl.edu

## References

Binois M, Gramacy RB (2021). “hetGP: Heteroskedastic Gaussian Process Modeling and Sequential Design in R.” _Journal of Statistical Software_,
  *98*(13), 1-44. doi:10.18637/jss.v098.i13 <https://doi.org/10.18637/jss.v098.i13>