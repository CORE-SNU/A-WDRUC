A-WDRUC
====================================================
This repository includes the MATLAB codes and data files used to perform the simulations in **[Wassertein Distributionally Robust Unit Commitment with Affine Rule][paper_link]**.

## 1. Requirements
To run our codes, the following softwares must be installed:
- **[MATLAB][MATLAB]**
- **[CPLEX Optimization Studio][CPLEX]**

which are free for students and academics. Regarding their versions, we used R2019a and 12.10 in the simulations, respectively. 

## 2. File Description
### 2.1 MAT-files 
The folder has two MAT-files containing the test-system-related parameters and one-year-long PV forecast data:
`6bus.mat` and `24bus.mat` for the 6-and the 24-bus test systems, respectively.
### 2.2 Script files
The folder has 14 script files. The script files `sol_AWDR.m`, `sol_SP.m`, `sol_RO.m`, and `sol_EWDR.m` are run to obtain solutions of the UC models "A-WDRUC", "SUC", "RUC", and "E-WDRUC", respectively. The script file `comparisons.m` is run to compare the cost performances of the solutions of these different UC models. The remaining nine script files are included in one or more of the aforesaid script files as sub-codes and thus automatically run. 

## 3. Simulations
### 3.1 Comparisons of A-WDRUC, SUC, and RUC
To compare the cost performances of "A-WDRUC", "SUC", and "RUC", first run `sol_AWDR.m`, by which 50 sets of 10 training samples and corresponding solutions of "A-WDRUC" will be obtained. 

..

The following settings may be modified: 

the number of training samples `J` (line 3 in `sol_AWDR.m`)

the number of test samples `J_oos` (line 8 in `sol_AWDR.m`)

The candidate values of the Wasserstein ball's radii `epsilon_DRO_track` (line 7 in `sol_AWDR.m`)

The true distribution of PV forecast error (line 55 in `sol_AWDR.m`)

### 3.2 Comparison of A-WDRUC and E-WDRUC
..


## 6. Troubleshooting

Most commonly reported problems we found are follows:

Why does MATLAB crash when I run code using IBM's MATLAB-CPLEX Connector?
https://www.mathworks.com/matlabcentral/answers/354479-why-does-matlab-crash-when-i-run-code-using-ibm-s-matlab-cplex-connector


[paper_link]: ..
[MATLAB]: https://matlab.mathworks.com
[CPLEX]: https://www.ibm.com/products/ilog-cplex-optimization-studio
