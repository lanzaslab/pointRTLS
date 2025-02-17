# pointRTLS

This contains a set of 3 Rmarkdown files, an example data file, and folder of pre-cooked data runs. These files are directly derived from 
the supplementary files associated with Dawson et al.(2019). This set deals with the processing of point-based location data into a contact network, the computation of information (i.e. entropy) loss on contact networks as a function processing decisions, and the integration of point-based contact data into a network model of transmission. 

These Rmd files include:

1. S1_ProcessingDecision_ContactProcessing.RmD
2. S2_ProcessingDecisions_Entropy_Fourier.Rmd
3. S3_TransmissionModel.RMD

Note that the labels have been changed from the files listed with the supplementary info from Dawson et al. (2019) so that its easier to follow here. 

In the first file, the user can process a provided example location dataset (S1_CattleData_Processing_Example1.RData) into contact matrices of varying specifications, including using different spatial thresholds (SpTh), temporal sampling windows (TSW), and Minimum contact duration (MCD). The example is preset to produce two datasets, including a table of contact duration times between individuals, and an array of adjacency matrices that is later used in the Transmission Model file(S3). We have included these files in the "Pre-cooked Data Runs" folder in this respository to save users time if they just want to jump ahead. 

In the second file, the user can assess the amount of entropy contained within a contact dataset. By generating multiple datasts using different processing criteria, users can ascertain the impact of processing criteria on the information content of their datasets. The user can use "S1_DurationTime_10sec_TSW_0.5m_SpTh_1_MCD_522016.RData" dataset produced by the S1 above, or directly from the "pre-cooked runs" folder. The script produces a vector of entropy values for the contact dataset, included as the pre-cooked RData file "S2_HVEC_0.5m_Dist_10sec_TSW_1_MCD". The user can then use a fourier transformation to compute the power spectrum density over particular time steps. These values succinctly summarize the differences in information content of the contact datat at various intervals, such as hours or days. The included datasets includes 8640 10-sec intervals over 1 day, so hour intervals is a natural time unit to consider.    

In the third file, the user can use the contact duration array "S1_DurationTime_10sec_TSW_0.5m_SpTh_1_MCD_522016" created in S1 in a network-based model of transmission. The user can manipulate various model parameters, and create longer or shorter duration runs. Model outputs summarizes the progression of the epidemic, as well a variety of epidemic metrics. 


Reference:
Dawson, D., Farthing, T., Sanderson, M, and Lanzas, C. 2019. Transmission on empirical dynamic contact networks is influenced by data processing decisions. Epidemics.26:32-42.



