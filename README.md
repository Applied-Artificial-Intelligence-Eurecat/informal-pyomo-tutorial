# An informal Pyomo tutorial

**_Biweekly_ · AAI Eurecat** \
June 4, 2024 \
_Giulia Zarpellon_

This repository accompanies the tutorial on [Pyomo](https://pyomo.readthedocs.io/en/stable/index.html) presented at our **_Biweekly_** on June 4, 2024. 
The slideshow was derived from the notebook `pyomo-tutorial.ipynb`, which you can run yourself by following the instructions below. 

## Installation

A vanilla conda environment is specified in `environment.yml`. Simply run 
```
conda env create -f environment.yml
conda activate pyomo-env
```

If you have your own favourite base environment that already contains Jupyter, just add to it Pyomo and [HiGHS](https://highs.dev/), which is the solver used here. 
Using HiGHS in Pyomo is possible via some contributed [APPSI](https://pyomo.readthedocs.io/en/stable/library_reference/appsi/appsi.html) (Auto-Persistent Pyomo Solver Interfaces), 
so install Pyomo with its conditional dependencies [followed by the HiGHS solver](https://ergo-code.github.io/HiGHS/dev/interfaces/python/#python-getting-started):
```
pip install 'pyomo[optional]'
pip install highspy
```

To run the same environment in a Jupyter kernel:
```
python -m ipykernel install --user --name=ipy-pyomo-env
```

You should be all set! To test the installation, open a Python console and try
```
import highspy
import pyomo.environ as pyo
from pyomo.contrib import appsi
```

## Slideshow

To visualize the notebook as a slide deck and serve it in a local https server, 
we use [`nbconvert`](https://nbconvert.readthedocs.io/en/latest/index.html) with the `--post serve` option specified:
```
jupyter nbconvert pyomo-tutorial.ipynb --to slides --post serve
```
See [here](https://nbconvert.readthedocs.io/en/latest/usage.html#serving-slides-with-an-https-server-post-serve) for more details.

Note: this works because the notebook cells have a "Slide Type" associated with them. If you wish to build a similar presentation in the future, 
use the "Property inspector" icon (the two little gears) at the top right of a Jupyter notebook to define extra properties for cells.
Under "Common tools" you should be able to edit the "Slide Type" field to build your own presentation.

