A-WDRUC
====================================================
This repository includes the MATLAB codes and data files used to perform the simulations in **[Wassertein Distributionally Robust Unit Commitment with Affine Rule][paper_link]**.

## 1. Requirements
To run our codes, the following softwares must be installed:
- **[MATLAB][MATLAB]**
- **[CPLEX Optimization Studio][CPLEX]**

which are free for students and academics. Regarding their versions, we used R2019a and 12.10, respectively. 

## 2. File Description
### 2.1 MAT-files 
The folder has two MAT-files containing the test-system-related parameters and one-year-long PV forecast data:
`6bus.mat` and `24bus.mat` for the 6-and the 24-bus test systems, respectively.
### 2.2 Script files
The folder has 14 script files. The script files `sol_AWDR.m`, `sol_SP.m`, `sol_RO.m`, and `sol_EWDR.m` are run to obtain solutions of the UC models "A-WDRUC", "SUC", "RUC", and "E-WDRUC", respectively. The script file `comparisons.m` is run to compare the cost performances of the solutions of these different UC models. The remaining nine script files are included in one or more of the aforesaid script files as sub-codes and thus automatically run. 

## 3. Simulations
### 3.1 Comparisons of A-WDRUC, SUC, and RUC
The cost performances of "A-WDRUC", "SUC", and "RUC" are compared as follows:

1. Run `sol_AWDR.m`. This yields the results of 50 independent simultaion runs, in each of which 10 training samples are generated and a solution of "A-WDRUC" is returned. The 50 sets of results are saved as MAT-files `sol_AWDR_1.mat`,...,`sol_AWDR_50.mat`.
2. Run `sol_SP.m`. This yields the results of 50 independent simulation runs, in each of which a solution of "SUC" is returned for the 10 training samples generated in Step 1. The 50 sets of results are saved as MAT-files `sol_SP_1.mat`,...,`sol_SP_50.mat`.
3. Run `sol_RO.m`. This yields a solution of "RUC". The results are saved as a MAT-file `sol_RO.mat`.
4. Run `comparisons.m`. This yields the results of 50 independent simulation runs, in each of which 10,000 test samples are generated and the expected costs incurred by the solutions of "A-WDRUC", "SUC", and "RUC" are returned. The 50 sets of results are saved as MAT-files `comparisons_1.mat`,...,`comparisons_50.mat`.
5. Repeat Steps 1-4 for different numbers of training samples `J` (line 3 in `sol_AWDR.m`).

### 3.2 Comparison of A-WDRUC and E-WDRUC
The cost performances of "A-WDRUC" "E-WDRUC" are compared in a similar way. Specifically, run `sol_AWDR.m`, `sol_EWDR.m`, and `comparisons.m` in sequence for different numbers of training samples `J`. Note that, in this case, the lines related to "SUC" and "RUC" should be commented out and those related to "E-WDRUC" should be uncommented in `comparisons.m`. 

## 4. Troubleshooting
MATLAB might suddenly crashes while running the codes, which can be the result of incompatibilities between CPLEX functions and recent versions of MATLAB. If this problem recurs, try a lower version of MATLAB. More details are described on the following page:

Why does MATLAB crash when I run code using IBM's MATLAB-CPLEX Connector?
https://www.mathworks.com/matlabcentral/answers/354479-why-does-matlab-crash-when-i-run-code-using-ibm-s-matlab-cplex-connector

[paper_link]: ..
[MATLAB]: https://matlab.mathworks.com
[CPLEX]: https://www.ibm.com/products/ilog-cplex-optimization-studio
