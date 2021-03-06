
This directory contains code to estimate the model parameters for a given subtype (either H3N2 or H1N1pdm09), to simulate the latent dynamics of infection, and to perform the model validation. The work-flow follows below. Please refer to the [Introductory page](https://github.com/cobeylab/Influenza-immune-dynamics) for a step-by-step overview of the manuscript analysis.

1. Perform the model inference (using the code in the `Inference` subdirectory): 
    a. Execute the `make_host_data_list.R` script to generate a list of host data objects
    b. Convert the host data list from step 1 to a POMP object using the `data_to_pomp_object_structure.R` file.
    c. Execute global searches of the likelihood space and parameter profiles (see the detailed explanation on the  [Introductory page](https://github.com/cobeylab/Influenza-immune-dynamics)) to estimate the model parameters. 

2. Analyze the inference results and calculate the parameter MLEs/95% CIs (using the code in the `Results_analysis` subdirectory). After you have estimated all of the fitted parameters, create a `.rda` file containing a named vector of all parameters for the model simulations (step 3).

3. Simulate the dynamics from the best-fit model parameters, generate the output plots, and perform model validation (using code in the `Simulations` subdirectory).