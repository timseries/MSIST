MSIST and Variants Installation, Organization, and Usage

------------
Dependencies
------------

The software is written in Python, and requires Python >=2.7. https://www.python.org/downloads/.
The most up-to-date versions of the following freely-available Python packages are also required:

<package name>: url
 
numpy: http://www.numpy.org/
scipy: http://www.scipy.org/
scikit-learn: http://scikit-learn.org/stable/
matplotlib: http://matplotlib.org/
nibabel: http://nipy.org/nibabel/
libtiff: http://www.libtiff.org/
nose: https://nose.readthedocs.org/en/latest/
mpldatacursor: https://pypi.python.org/pypi/mpldatacursor/
pypng: http://pythonhosted.org/pypng/
PIL: http://www.pythonware.com/products/pil/ 
Note that Pillow is now available as a replacement for PIL: https://pypi.python.org/pypi/Pillow/)

For convenience, all dependencies can be installed (optionally in a virtualenvironment) using:
```pip install requirements.txt```

They python wrapper for libtiff has separate dependenices, which will need to be installed separately:
Linux: ```sudo apt-get install libtiff```
MAC OSX: ```brew install libtiff```

-------------------------
Download and Installation
-------------------------
1. git clone --recursive http://github.com/timseries/msist.git

2. Install dependencies (optionally in a virtual environment) using the instructions above.

3. Ensure this repo directory is added to your PYTHONPATH environment variable. In Linux, this can be accomplished by adding a line in the user's .bashrc file: export PYTHONPATH=$PYTHONPATH:<absolute path to this folder>
 
4. Install the DT-CWT package: 
   3.1 From <path to this folder>/py_operators/dtcwt/
   ```python setup.py install```

------------
Organization
------------

The software is organized with respect to conceptional unints of the MSIST algorithm and variants: solvers (py_solvers), operators (py_operators), and utlity functions/classes (py_utils). Solvers and operators are instantiated from sections in the specified configuration (.ini file). In this way, experimental settings and model parameters are separated from code as much as possible. Utility functions and classes are used throughout to manage data and store or interactively display results.

****
Data 
****

The data for all experiments can be found in /py_solvers/application/data/, including pre-computed sparse matrices used for the group variants of MSIST (in */avg_matrices/).

**************
Configurations 
**************

The software is bundled with several example configuration files, which are located in /py_solvers/application/<application_name>/config where <application_name> is one of:

mixed_poisson_gaussian, superresolution, compressed_sensing, deconvolution

Note: mixed_poisson_gaussian is a deconvolution fluorescence microsocopy application.

****
Code 
****

The implementation of the MSIST solver, and it's variants, is provided in subrepo py_sovlers: /py_solvers/so_msist.py.
Other solvers are included for benchark comparisons. 

-----
Usage 
-----

In a terminal, change directory to the py_solvers directory:

```python run_application.py```

You should see a series of two prompts with numerical options. 
    1. The first prompt corresponds to the application category. 
    2. The second prompt corresponds to configuration file (.ini) within the chosen application category.


