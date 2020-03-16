# Rifampicin-Model
Whole-body PBPK model of rifampicin.

**The latest release of this model including a report on model building, model features and model evaluation can be found [here](../../releases/latest).**

<p align="center">
  <img src="Rifampicin.png">
</p> 

This rifampicin model is intended to be used as a perpetrator in CYP3A4-mediated drug-drug interactions. The model features verified CYP3A4 induction, transient competitive CYP3A4 inhibition. Additional features represent P-gp induction and inhibition.

Rifampicin is an antibiotic used for the treatment of mycobacterium infections, including tuberculosis and leprosy. For the investigation of DDIs, rifampicin is an established potent inducer of multiple drug metabolizing enzymes (CYP3A4, CYP2B6, CYP2C8, CYP2C9, CYP2C19) and transporters (P-gp, MRP2, MRP3, MRP4, OATP1A2). In addition to its inducing capabilities, rifampicin also competitively inhibits enzymes and transporters like CYP3A4, P-gp, OATP1B1 and OATP1B3. 

The presented model is based on the published model by Hanke et al. 2018 [[1](#reference)].The herein presented model represents the rifampicin model originally published by Hanke *et al.* [[1](#reference)]., and extended in later publications [[2,3](#reference)].  It was built and evaluated using several clinical studies, covering a dosing range from 300 to 600 mg after intravenous and oral administration. Integrating and testing processes that were described as vital to the pharmacokinetics of rifampicin resulted in a final model that applies transport by OATP1B1, metabolism by arylacetamide deacetylase (AADAC), transport by P-gp and glomerular filtration. Furthermore, auto-induction of OATP1B1, AADAC and P-gp expression has been incorporated. Studies that measured pharmacokinetic profiles of rifampicin at different days of a 600 mg po once daily regimen indicate that the clearance of rifampicin increases over time due to auto-induction of elimination processes. Therefore, induction of OATP1B1, AADAC and P-gp expression is included in the rifampicin model. The hypothesis of AADAC induction by rifampicin was based on the fact, that 

- rifampicin induces its own metabolism, and 
- B-esterases are inducible by rifampicin via PXR. 

For applications in the context of DDI, the model features CYP3A4 induction, transient competitive 
CYP3A4 inhibition. Additional features represent P-gp induction and inhibition.



## Code of conduct
Everyone interacting in the Open Systems Pharmacology community (codebases, issue trackers, chat rooms, mailing lists etc...) is expected to follow the Open Systems Pharmacology [code of conduct](https://github.com/Open-Systems-Pharmacology/Suite/blob/master/CODE_OF_CONDUCT.md#contributor-covenant-code-of-conduct).

## Contribution
We encourage contribution to the Open Systems Pharmacology community. Before getting started please read the [contribution guidelines](https://github.com/Open-Systems-Pharmacology/Suite/blob/master/CONTRIBUTING.md#ways-to-contribute). If you are contributing code, please be familiar with the [coding standard](https://github.com/Open-Systems-Pharmacology/Suite/blob/master/CODING_STANDARDS.md#visual-studio-settings).

## License
The model code is distributed under the [GPLv2 License](https://github.com/Open-Systems-Pharmacology/Suite/blob/develop/LICENSE).

## Reference
[1] [Hanke N, Frechen S, Moj D, Britz H, Eissing T, Wendl T, Lehr T. PBPK Models for CYP3A4 and P-gp DDI Prediction: A Modeling Network of Rifampicin, Itraconazole, Clarithromycin, Midazolam, Alfentanil, and Digoxin. CPT Pharmacometrics Syst Pharmacol. 2018 Oct;7(10):647-659.](https://ascpt.onlinelibrary.wiley.com/doi/abs/10.1002/psp4.12343)

[2] [Britz H, Hanke N, Volz AK, Spigset O, Schwab M, Eissing T, Wendl T, Frechen S, Lehr T. Physiologically-Based Pharmacokinetic Models for CYP1A2 Drug-Drug Interaction Prediction: A Modeling Network of Fluvoxamine, Theophylline, Caffeine, Rifampicin, and Midazolam. CPT Pharmacometrics Syst Pharmacol. 2019 May;8(5):296-307.](https://doi.org/10.1002/psp4.12397)

[3] [Türk D, Hanke N, Wolf S, Frechen S, Eissing T, Wendl T, Schwab M, Lehr T. Physiologically Based Pharmacokinetic Models for Prediction of Complex CYP2C8 and OATP1B1 (SLCO1B1) Drug-Drug-Gene Interactions: A Modeling Network of Gemfibrozil, Repaglinide, Pioglitazone, Rifampicin, Clarithromycin and Itraconazole. Clin Pharmacokinet. 2019 Dec;58(12):1595-1607](https://dx.doi.org/10.1007/s40262-019-00777-x)



