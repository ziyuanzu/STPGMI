# STPGMI
The scripts for simulation of metabolism and interactions in a single Pyomo modelling framework.
# Environment
The scripts were written and tested with Python 3.9
The core libraries essential for the pipeline including:
Cobrapy toolkit: version --0.25.0；
Pyomo package: version --6.4.0；
Gurobi solver: version --10.0.1.
# Software
The packages used to run the pipeline was listed in requirements.txt. To install the requirements using pip, run the following code at command-line:
$ pip install -r requirements.txt To create a stand-alone environment named STPGMI with Python 3.9 and all the required package versions (especially for cobrapy is also available), run the following code:
$ conda create -n STPGMI python=3.9 $ conda activate STPGMI $ pip install -r requirements.txt $ python -m ipykernel install --user --name STPGMI --display-name "STPGMI" You can read more about using conda environments in the Managing Environments section of the conda documentation.
# Steps to reproduce the main analysis in the publication
Typical results can be reproduced by executing the Jupyter Python notebooks:
The PMI.ipynb files in STPGMI folder simulate the strain competiveness
The flaml_competitive-summary.ipynb files in STPGMI folder simulate the effects of features on strain competiveness
Download the ETGEMs_function.py at https://github.com/tibbdc/ETGEMs, and place the file in the codes folder.
Rename the ETGEMs_function.py to ETGEMs_function_PMI.py
Close the thermodynamic constraints in functions of Max_Growth_Rate_Calculation and Min_Flux_Sum_Calculation in ETGEMs_function_PMI.py for Saccharomyces cerevisiae. Make 2 copies of each of the 2 functions. Rename the copies separately as Max_Growth_Rate_Calculation0, Max_Growth_Rate_Calculation1, Min_Flux_Sum_Calculation0 and Min_Flux_Sum_Calculation1. While the Max_Growth_Rate_Calculation1 and Min_Flux_Sum_Calculation1 functions are used to simulate the metabolism of S. cerevisiae, we make set_thermodynamics=False in the two functions.
