# regulatory-network-for-HSPCs
The Matlab codes include three modules: 
1.	In silico model
2.	Simplified model
3.	Exponents changed model
As explained in Supplementary text, exponents changed model refers to the setting where the exponents in equations change less than linearly along with the increase in the number of motifs. 

To run simulations using in silico, or simplified, or exponents changed model:
1.	Change Current Folder of MATLAB to ‘in silico model’, or ’Simplified model’, or ’Probabilities changed model’.
2.	Type in Command Window:
Run single_run   
% simulate the expression of a single wild-type cell over 50 discrete time points. Output is a 50x9 matrix named as ‘output’.
Run multiple_run
% simulate the overall distributions of all nine TFs expression as might be seen in a cell population by implementing 1000 independent simulations. Each simulation has 50 discrete time points. A single time point (sample) is randomly drawn from each simulation after the first 10 time points (burn-in period used to secure the reach of stabilization). The selected samples together form a pool of 1000 simulated single cells, which are used to derive the overall distributions of all nine TFs expression. Please note all perturbation simulations mentioned below follow the same subsampling strategy as described here. Output is a 1000x9 matrix named as ‘matrix_wildtype’, or ‘matrix_wildtype_sm’, or ‘matrix_wildtype_ex’. 
Run down_PU1
% simulate complete removal of PU.1 after the model reaching its initial steady state. Output is a 1000x9 matrix named as ‘matrix_down_PU1’, or ‘matrix_down_PU1_sm’, or ‘matrix_down_PU1_ex’.
Run up_Gfi1b
% simulate Gfi1b overexpression by increasing the expression level of Gfi1b to the hypothetical maximum level 1 after the model had reached its initial steady state. Output is a 1000x9 matrix named as ‘matrix_up_Gfi1b’, or ‘matrix_up_Gfi1b_sm’, or ‘matrix_up_Gfi1b_ex’.
Run down_Scl
% simulate complete removal of Scl after the model reaching its initial steady state. Output is a 1000x9 matrix named as ‘matrix_down_Scl’ or ‘matrix_down_Scl_sm’. 
Run down_Lyl1
% simulate complete removal of Lyl1 after the model reaching its initial steady state. Output is a 1000x9 matrix named as ‘matrix_down_Lyl1’ or ‘matrix_down_Lyl1_sm’. 
Run down_SclLyl1
% simulate simultaneous complete removal of Scl and Lyl1 after the model reaching its initial steady state. Output is a 1000x9 matrix named as ‘matrix_down_SclLyl1’ or ‘matrix_down_SclLyl1_sm’. 
Run up_Runx1_AE
% simulate the leukemic scenario caused by AML-ETO expression. The level of Runx1 is fixed at the hypothetical maximum level 1, and at the same time all activating inputs of Runx1 are converted to inhibiting inputs in the model. Output is a 1000x9 matrix named as ‘matrix_up_Runx1_AE’, or ‘matrix_up_Runx1_AE_ex’. 
3.	Any distribution fitting technique can then be applied to the outputs to produce desired plots. 
