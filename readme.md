# Experiments

This is for experimenting with pip vs conda install of pymc.

On macos (apple silicon, Nov 2024) I ended up not seeing a difference in the two methods on the MAC, no complaints about the blas library.  Odd. Only trouble was with using the correct python version! 

On Windows:

The conda version worked fine, sampled fast. 

The pip version complained on import:
```
WARNING (pytensor.configdefaults): g++ not available, if using conda: `conda install m2w64-toolchain`
WARNING (pytensor.configdefaults): g++ not detected!  PyTensor will be unable to compile C-implementations and will default to Python. Performance may be severely degraded. To remove this warning, set PyTensor flags cxx to an empty string.
WARNING (pytensor.tensor.blas): Using NumPy C-API based implementation for BLAS functions.
Running on PyMC v5.18.2
```

I tried to sample, and it started but it was very slow, predicting >6 hours to complete.  This is not just a problem with blas but rather also that it cannot find g++ toolchain.