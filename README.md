#MSIST and Variants: Installation, Organization, and Usage

##Download and Installation

1. ```git clone --recursive http://github.com/timseries/msist.git```

2. Install dependencies (optionally in a virtual environment) using the instructions above.

```pip install requirements.txt```

The python wrapper for libtiff has separate dependenices, which will need to be installed separately:

Linux: ```sudo apt-get install libtiff```

MAC OSX: ```brew install libtiff```

3. Ensure this repo directory is added to your PYTHONPATH environment variable. In Linux, this can be accomplished by adding a line in the user's .bashrc file: export PYTHONPATH=$PYTHONPATH:<absolute path to this folder>
 
##Organization

The software is organized with respect to conceptional unints of the MSIST algorithm and variants: solvers (py_solvers), operators (py_operators), and utlity functions/classes (py_utils). Solvers and operators are instantiated from sections in the specified configuration (.ini file). In this way, experimental settings and model parameters are separated from code as much as possible. Utility functions and classes are used throughout to manage data and store or interactively display results.

###Data 

The data for all experiments can downloaded [here](https://drive.google.com/open?id=0B9NAB6NG4hq1UFo0aDhnaXFDSG8). This file should be decompressed to /py_solvers/application/.

###Configurations 

The software is bundled with several example configuration files, which are located in /py_solvers/application/<application_name>/config where <application_name> is one of:

mixed_poisson_gaussian, superresolution, compressed_sensing, deconvolution

Note: mixed_poisson_gaussian is a deconvolution fluorescence microsocopy application.

###Code 

The implementation of the MSIST solver, and it's variants, is provided in subrepo py_sovlers: /py_solvers/so_msist.py.
Other solvers are included for benchark comparisons. 

##Usage

In a terminal, change directory to the py_solvers directory:

```python run_application.py```

You should see a series of two prompts with numerical options. 
    1. The first prompt corresponds to the application category. 
    2. The second prompt corresponds to configuration file (.ini) within the chosen application category.


