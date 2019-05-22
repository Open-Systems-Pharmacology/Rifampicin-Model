### Rifampicin model

Rifampicin is an antibiotic used for the treatment of mycobacterium infections, including tuberculosis and leprosy. For the investigation of DDIs, rifampicin is an established potent inducer of multiple drug metabolizing enzymes (CYP3A4, CYP2B6, CYP2C8, CYP2C9, CYP2C19) and transporters (P-gp, MRP2, MRP3, MRP4, OATP1A2). In addition to its inducing capabilities, rifampicin also competitively inhibits enzymes and transporters like CYP3A4, P-gp, OATP1B1 and OATP1B3. This qualification report focuses on the CYP3A4  effects of rifampicin. While induction by rifampicin involves upregulation of enzymes and transporters and therefore takes several days to fully develop, competitive inhibition has an instantaneous effect and is strongest at the time of highest exposure to the inhibitor. As a consequence, the effects of rifampicin caused via competitive inhibition are most prominent 1 - 2 h after its oral administration and of relatively short duration. These complex and opposing actions of rifampicin demand careful consideration of the timing of interacting drugs during clinical studies and modeling. 

The presented model is based on the published model by Hanke et al. 2018 [[1](#reference)]. It was built and evaluated using several clinical studies, covering a dosing range from 300 to 600 mg after intravenous and oral administration. Integrating and testing processes that were described as vital to the pharmacokinetics of rifampicin resulted in a final model that applies transport by OATP1B1, metabolism by arylacetamide deacetylase (AADAC), transport by P-gp and glomerular filtration. Furthermore, auto-induction of OATP1B1, AADAC and P-gp expression has been incorporated . Studies that measured pharmacokinetic profiles of rifampicin at different days of a 600 mg po once daily regimen indicate that the clearance of rifampicin increases over time due to auto-induction of elimination processes. Therefore, induction of OATP1B1, AADAC and P-gp expression is included in the rifampicin model. The hypothesis of AADAC induction by rifampicin was based on the fact, that 

- rifampicin induces its own metabolism, and 
- B-esterases are inducible by rifampicin via PXR. 

For applications in the context of DDI, the model features CYP3A4 induction, transient competitive 
CYP3A4 inhibition. Additional features represent P-gp induction and inhibition.

For further references please refer to the rifampicin model repository [[2](#reference)] and the database of observed data [[3](#reference)].



#### References

[1] [Hanke N, Frechen S, Moj D, Britz H, Eissing T, Wendl T, Lehr T. PBPK models for CYP3A4 and P-gp DDI prediction: a modeling network of rifampicin, itraconazole, clarithromycin, midazolam, alfentanil and digoxin. CPT: Pharmacometrics & Systems Pharmacology (2018)](https://ascpt.onlinelibrary.wiley.com/doi/abs/10.1002/psp4.12343)

[2] [https://github.com/Open-Systems-Pharmacology/Rifampicin-Model](https://github.com/Open-Systems-Pharmacology/Rifampicin-Model)

[3] [https://github.com/Open-Systems-Pharmacology/Database-for-observed-data](https://github.com/Open-Systems-Pharmacology/Database-for-observed-data)