The general concept of building a PBPK model has previously been described by Kuepfer et al. ([Kuepfer 2016](#5-References)). Relevant information on anthropometric (height, weight) and physiological parameters (e.g. blood flows, organ volumes, binding protein concentrations, hematocrit, cardiac output) in adults was gathered from the literature and has been previously published ([Willmann 2007](#5-References)). The information was incorporated into PK-Sim® and was used as default values for the simulations in adults.

The applied activity and variability of plasma proteins and active processes that are integrated into PK-Sim® are described in the publicly available PK-Sim® Ontogeny Database Version 7.3 ([PK-Sim Ontogeny Database Version 7.3](#5-References)) or otherwise referenced for the specific process.

The model was built combining bottom-up and top-down techniques. An extensive literature search yielded (1) physicochemical parameter values (2) information on active ADME and DDI-related (i.e. induction and inhibition) processes and (3) clinical studies of intravenous and oral administration in single and multiple dosing regimens, covering a broad dosing range with observed concentrations. 

A mean PBPK model was developed using a typical European individual. Enterohepatic recycling for transport processes into the bile was enabled in a continuous fashion (continuous flow from the liver to the lumen of duodenum). One study was performed in female patients after cholecystectomy ([Acocella 1972a](#5-References)). The bile of these patients was collected via a T tube. In the simulations of these patients, enterohepatic recycling was switched off and a virtual gallbladder collected the excreted rifampicin over time. Relevant ADME processes reported to influence the PK of rifampicin were implemented into the model and tested. For parameters that could not be (reliably) informed from literature, parameter identification was performed using a representative set of available clinical studies (see below). Model evaluation was based on the ability of the model to describe observed plasma concentration-time profiles and fraction excreted of unchanged drug to urine and bile.

Details about input data (physicochemical, *in vitro* and clinical) can be found in [Section 2.2](#22-Data).

Details about the structural model and its parameters can be found in [Section 2.3](#23-Model-Parameters-and-Assumptions).



