# README
The codes refer to a publication entitled "An integrated regulatory network of 9 haematopoietic transcription factors with experimentally validated binding sites reveals mechanisms of cell state stabilisation"

ABSTRACT:
Transcription factor (TF) networks determine cell type identity by establishing and maintaining lineage-specific expression profiles, yet reconstruction of mammalian regulatory network models has been hampered by a lack of comprehensive functional validation of regulatory interactions.  Here, we report comprehensive ChIP-Seq, transgenic and reporter gene experimental data that have allowed us to construct an experimentally validated regulatory network model for haematopoietic stem/progenitor cells (HSPCs).  Model simulation coupled with subsequent experimental validation using single cell expression profiling revealed potential mechanisms for cell state stabilisation, and also how a leukemogenic TF fusion protein perturbs key HSPC regulators. The approach presented here should help to improve our understanding of both normal physiological and disease processes.  

The Matlab codes include three modules: 

1.	In silico model

2.	Simplified model

3.	Exponents changed model

As explained in Supplementary text, exponents changed model refers to the setting where the exponents in equations change less than linearly along with the increase in the number of motifs. 

To run simulations using in silico, or simplified, or exponents changed model:

First, change Current Folder of MATLAB to ‘in silico model’, or ’Simplified model’, or ’Probabilities changed model’.

Second, type in Command Window:

run single_run

% simulate the expression of a single wild-type cell over 50 discrete time points. Output is a 50x9 matrix named as ‘output’.

run multiple_run

% simulate the overall distributions of all nine TFs expression as might be seen in a cell population by implementing 1000 independent simulations. Each simulation has 50 discrete time points. A single time point (sample) is randomly drawn from each simulation after the first 10 time points (burn-in period used to secure the reach of stabilization). The selected samples together form a pool of 1000 simulated single cells, which are used to derive the overall distributions of all nine TFs expression. Please note all perturbation simulations mentioned below follow the same subsampling strategy as described here. Output is a 1000x9 matrix named as ‘matrix_wildtype’, or ‘matrix_wildtype_sm’, or ‘matrix_wildtype_ex’. 

run down_PU1

% simulate complete removal of PU.1 after the model reaching its initial steady state. Output is a 1000x9 matrix named as ‘matrix_down_PU1’, or ‘matrix_down_PU1_sm’, or ‘matrix_down_PU1_ex’.

run up_Gfi1b

% simulate Gfi1b overexpression by increasing the expression level of Gfi1b to the hypothetical maximum level 1 after the model had reached its initial steady state. Output is a 1000x9 matrix named as ‘matrix_up_Gfi1b’, or ‘matrix_up_Gfi1b_sm’, or ‘matrix_up_Gfi1b_ex’.

run down_Scl

% simulate complete removal of Scl after the model reaching its initial steady state. Output is a 1000x9 matrix named as ‘matrix_down_Scl’ or ‘matrix_down_Scl_sm’. 

run down_Lyl1

% simulate complete removal of Lyl1 after the model reaching its initial steady state. Output is a 1000x9 matrix named as ‘matrix_down_Lyl1’ or ‘matrix_down_Lyl1_sm’. 

run down_SclLyl1

% simulate simultaneous complete removal of Scl and Lyl1 after the model reaching its initial steady state. Output is a 1000x9 matrix named as ‘matrix_down_SclLyl1’ or ‘matrix_down_SclLyl1_sm’. 

run up_Runx1_AE

% simulate the leukemic scenario caused by AML-ETO expression. The level of Runx1 is fixed at the hypothetical maximum level 1, and at the same time all activating inputs of Runx1 are converted to inhibiting inputs in the model. Output is a 1000x9 matrix named as ‘matrix_up_Runx1_AE’, or ‘matrix_up_Runx1_AE_ex’. 

Third, any distribution fitting technique can then be applied to the outputs to produce desired plots. 
