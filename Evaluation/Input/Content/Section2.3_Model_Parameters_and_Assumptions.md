### 2.3.1 Absorption

Herein, the model parameter `Specific intestinal permeability` was optimized to best match clinical data (see  [Section 2.3.5](#2.3.5-Automated-Parameter-Identification)). The results of the optimization can be found in [Section 2.3.5](#2.3.5-Automated-Parameter-Identification).

Measured aqueous solubility ([Boman 1974](#5-References), see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)) was set as default solubility.

As observed data do not show substantial differences between different formulations for oral rifampicin administration, all oral administrations were modelled as an oral solution.

### 2.3.2 Distribution

Recent measure of fraction unbound in plasma showed values of approximately 17% ([Templeton 2011](#5-References), [Shou 2008](#5-References), see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)). This value was implemented in this model.

`Lipophilicity` was optimized within the range of measured values to find a best match of simulated to observed rifampicin PK profile data.

After testing the available organ-plasma partition coefficient and cell permeability calculation methods built in PK-Sim, observed clinical data was best described by choosing the partition coefficient calculation by `Rodgers and Rowland` and cellular permeability calculation by `PK-Sim Standard ` for itraconazole and its metabolites. The PK-Sim calculated `Blood/plasma concentration ratio` is well in line with the observed value of 0.9 ([Loos 1985](#5-References)).

### 2.3.3 Metabolism and Elimination

Integrating and testing active processes that were considered vital to the PK of rifampicin after literature review resulted in a final model that applies transport by OATP1B1 ([Tirona 2003](5-References)), metabolism by arylacetamide deacetylase (AADAC) ([Nakajima  2011](5-References)), transport by P-gp ([Collett 2004](5-References)) and glomerular filtration. No study so far clearly demonstrated that rifampicin was substrate of CYP3A4; hence, in this PBPK model rifampicin only acts as a perpetrator on CYP3A4 without being metabolized by it.

The implemented expression profile of AADAC, P-gp and OATP1B1 were based on high-sensitive real-time RT-PCR ([Nishimura 2013](#5 References)) of the PK-Sim expression database. The relative expression in the mucosa of the gut wall was modified based on an optimized value as reported by Hanke *et al.* ([Hanke 2018](#5-References)). Herein, this value was increased by factor 3.57 based on Digoxin PK data in combination wih PBPK modelling.

It is assumed that the mRNA concentration is proportional to the respective protein concentration. Thus, the expression of a protein in a specific organ relates to the expression in the organ with the highest expression which is termed reference concentration of the protein ([Meyer 2012](5-References)). OATP1B1 was configured as influx transporter and P-gp as efflux transporter. Reference concentrations of the implemented active processes (enzymes and transporters) are summarized below:

| Protein | Reference concentration<br />[µmol/L] | Reference Organ        |
| ------- | ------------------------------------- | ---------------------- |
| AADAC   | 1.0 (assumed)                         | Liver                  |
| P-gp    | 1.41 ([Hanke 2018](#5-References))    | Mucosa Small Intestine |
| OATP1B1 | 1.0 (assumed)                         | Liver                  |

The kinetic parameters describing the rifampicin metabolism and transport for AADAC, P-gp and OATP1B1  were imputed into the model as follows: while Michaelis constants (K<sub>m</sub> values) of AADAC metabolization and the two transport processes were taken from reported in vitro experiments, enzymatic and transport turnover values (k<sub>cat</sub>) were optimized based on *in vivo* PK data (see [Section 2.3.5](#2.3.5-Automated-Parameter-Identification)).

Multiple dose studies that measured PK profiles of rifampicin at different days of a 600 mg po once daily regimen indicate that rifampicin exposure decreases over time due to auto-induction processes ([Baneyx 2014](5-References)), ([Smythe 2012](5-References)). *In-vitro* studies in human hepatocytes suggest that rifampicin induces P-gp ([Collett 2004](5-References), [Dixit 2007](5-References), [Williamson 2013](5-References)) and OATP1B1 ([Dixit 2007](5-References), [Williamson 2013](5-References)). It has further been shown in DDI studies with prototypical substrates of these transporters (pravastatin and digoxin, respectively) that the induction of these transporters can also be observed *in vivo* ([Kyrklund 2000](5-References), [Greiner 1999](5-References)). As in the case of CYP3A4 induction, both induction processes are mediated via pregnane X receptor (PXR) ([Geick 2001](5-References)). Furthermore, it has been demonstrated that B-esterases are inducible by rifampicin via PXR ([Smythe 2012](5-References), [Staudinger 2010](5-References)) and that the esterase arylacetamide deacetylase (AADAC) as the enzyme catalyzing the main metabolic pathway of rifampicin is regulated by PXR ([Zhang 2012](5-References)). Therefore, (auto-)induction of P-gp, OATP1B1 and AADAC expression was assumed and implemented in the rifampicin model. Modelling induction of an endogenous expressed protein requires three parameters, i.e. **EC<sub>50</sub>** (concentration at which induction is half maximum), **E<sub>max</sub>** (maximum induction effect on endogenous synthesis rate) and endogenous **protein turnover (half-life)**. Little is known about these values *in vivo* for AADAC, P-gp and OATP1B1 induction. 

#### (Auto-) Induction Processes: AADAC, P-gp and OATP1B1

##### EC<sub>50</sub>

As all induction processes are mediated by PXR, the same unbound EC<sub>50</sub> of 0.34 µmol/L (originally measured in primary human hepatocytes for CYP3A4 induction after correcting for the fraction unbound ([Baneyx 2014](5-References), [Shou 2008](5-References), [Templeton 2011](5-References)) was applied for all induction processes. This assumption is supported by the fact that Moore *et al.* found a general EC<sub>50</sub> value for PXR-mediated rifampicin induction of 0.71 µmol/L (resulting in an unbound EC<sub>50</sub> of 0.30 µmol/L after correcting for the fraction unbound [Shou  2008](5-References)). 

##### E<sub>max</sub>

E<sub>max</sub> values for AADAC and OATP1B1 are unknown and fitted based on observed clinical PK data of rifampicin (see [Section 2.3.5](#2.3.5-Automated-Parameter-Identification)).,

A study by Greiner et al. ([Greiner 1999](5-References)) found 3.5 fold elevated P-gp levels in human duodenal biopsies after multiple doses of rifampicin. This value was assumed to represent an *in vivo* maximum effect correspodning to an E<sub>max</sub> value of 2.5. This E<sub>max</sub> was included in the model for P-gp induction (see also [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)).

##### Protein turnover (half-lives)

Endogenous half-lives of these proteins is not known. Therefore, the same values applicable for CYP3A4 turnover (as implemented in PK-Sim ([PK-Sim Ontogeny Database Version 7.3](#5-References)) were assumed, i.e. 36 hours in the liver ([Obach 2007](5-References)) and 23 hours in the intestine ([Greenblatt 2003](5-References)).

### 2.3.4 DDI Parameters

The following sub-section describe the model's input for DDI-related parameters, i.e. induction and inhibition on certain enzymes and transporters, for which rifampicin may act in a perpetrator role. Verification of these model parameters and linked processes is not evaluated in this report. Applications are assessed in specific use cases and reported elsewhere. 

#### CYP3A4 induction and inhibition
Induction of CYP3A4 was incorporated using the weighted mean **EC<sub>50</sub>** of 0.8 µmol/L and **E<sub>max </sub>** of 9 estimates based on CYP3A4 activity induction in primary human hepatocytes ([Templeton 2011](5-References), see also [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)). Similar values for EC<sub>50</sub> (0.77, 0.80 µmol/L) and E<sub>max </sub> (7, 9, 10) have been reported by other groups ([Kolars 1992](5-References), [Mills 2004](5-References), [Sahi 2000](5-References)). The *in vitro* value of EC<sub>50</sub> of 0.8 µmol/L was corrected by the unbound fraction of rifampicin in hepatocytes of 0.419 to obtain an **unbound EC<sub>50</sub>** value of 0.34 µmol/L ([Baneyx 2014](5-References), [Shou 2008](5-References), [Templeton 2011](5-References)) to be used in the PBPK model. 

Competitive inhibition of CYP3A4 by rifampicin was included using a dissociation (inhibition) constant (**K<sub>i</sub>**) of 18.5 µmol/L determined in human liver microsomes via inhibition of midazolam 1-hydroxylation ([Kajosaari 2005](5-References)) No correction of this *in vitro* value was applied to account for potential binding in the assay, as only 0.1 mg/mL human liver microsomal protein were used and a negligible unbound fraction of 0.90 – 0.98 was prediected ([Austin 2002](5-References)).

Time to reach newly induced CYP3A4 levels and time for de-induction depends on the half-lives of the perpetrator drug but also of the endogenous natural turnover of the induced protein. CYP3A4 turnover featured zero-order synthesis rate and first-order degradation rate. A distinct degradation rate constant (k<sub>deg</sub>) was considered for the intestinal mucosa which rather reflects enterocytic turnover than protein turnover, while in all other CYP3A4 expressing organs CYP3A4 turnover was assumed to follow that of the liver. **CYP3A4 half-life** (= ln(2)/k<sub>deg</sub>) of 23 and 36 h in intestine and liver were incorporated ([Obach 2007](5-References), [Greenblatt 2003](5-References), [PK-Sim Ontogeny Database Version 7.3](#5-References)).

#### P-gp induction and inhibition
P-gp induction is described above.

An *in vitro* determined K<sub>i</sub> values for rifampicin ([Reitman 2011](5-References)) served directly as model input (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)).

#### OATP1B1 induction and inhibition

OATP1B1 induction is described above. 

An *in vitro* determined K<sub>i</sub> values for rifampicin ([Hirano 2006](5-References)) served directly as model input (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)).

#### OATP1B3 induction and inhibition

The same parameters as for OATP1B1 induction were assumed.

An *in vitro* determined K<sub>i</sub> values for rifampicin ([Annaert 2010](5-References)) served directly as model input (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)).

#### CYP2C8 induction and inhibition

For PXR-mediated induction, the same unbound EC<sub>50</sub> of 0.34 µmol/L (originally measured in primary human hepatocytes for CYP3A4 induction after correcting for the fraction unbound ([Baneyx 2014](5-References), [Shou 2008](5-References), [Templeton 2011](5-References)) was applied (see above).

An E<sub>max</sub> value reported by Buckley *et al.* ([Buckley 2014](5-References)) served for model input (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)).

CYP2C8 half-life of 23 h in the liver ([Renwick 2000](5-References), [PK-Sim Ontogeny Database Version 7.3](#5-References)) and of 23 h in the intestine (assuming that the turnover here rather reflects enterocytic turnover than protein turnover) ([Greenblatt 2003](5-References), [PK-Sim Ontogeny Database Version 7.3](#5-References)) were incorporated.

An *in vitro* determined K<sub>i</sub> values for rifampicin ([Kajosaari 2005](5-References)) served directly as model input.

#### CYP1A2 induction

For PXR-mediated induction, the same unbound EC<sub>50</sub> of 0.34 µmol/L (originally measured in primary human hepatocytes for CYP3A4 induction after correcting for the fraction unbound ([Baneyx 2014](5-References), [Shou 2008](5-References), [Templeton 2011](5-References)) was applied (see above).

An E<sub>max</sub> value reported by Chen *et al.* ([Chen 2010](5-References)) served for model input (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)).

CYP1A2 half-life of 39 h in the liver ([Obach 2007](5-References),[PK-Sim Ontogeny Database Version 7.3](#5-References)) and of 23 h in the intestine (assuming that the turnover here rather reflects enterocytic turnover than protein turnover) ([Greenblatt 2003](5-References), [PK-Sim Ontogeny Database Version 7.3](#5-References)) were incorporated.

#### CYP2E1 induction

For PXR-mediated induction, the same unbound EC<sub>50</sub> of 0.34 µmol/L (originally measured in primary human hepatocytes for CYP3A4 induction after correcting for the fraction unbound ([Baneyx 2014](5-References), [Shou 2008](5-References), [Templeton 2011](5-References)) was applied (see above).

An E<sub>max</sub> value reported by Rae *et al.* ([Rae 2001](5-References)) served for model input (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)).

CYP2E1 half-life of 50 h in the liver ([Emery 1999](5-References), [PK-Sim Ontogeny Database Version 7.3](#5-References)) and of 23 h in the intestine (assuming that the turnover here rather reflects enterocytic turnover than protein turnover) ([Greenblatt 2003](5-References), [PK-Sim Ontogeny Database Version 7.3](#5-References)) were incorporated.

#### Summary DDI Parameter

| Protein | K<sub>i</sub><br />[µmol/L] | E<sub>max</sub><br />                                  | EC<sub>50</sub><br />[µmol/L] | Half-life<br />liver [h] | Half-life<br />intestine [h] |
| ------- | --------------------------- | ------------------------------------------------------ | ----------------------------- | ------------------------ | ---------------------------- |
| CYP1A2  | -                           | 0.65                                                   | 0.34                          | 39                       | 23 (assumed)                 |
| CYP2C8  | 30.2                        | 3.2                                                    | 0.34                          | 23                       | 23 (assumed)                 |
| CYP2E1  | -                           | 0.8                                                    | 0.34                          | 50                       | 23 (assumed)                 |
| CYP3A4  | 18.5                        | 9                                                      | 0.34                          | 36                       | 23                           |
| AADAC   | -                           | [optimized](#2.3.5-Automated-Parameter-Identification) | 0.34                          | 36 (assumed)             | 23 (assumed)                 |
| P-gp    | 169                         | [optimized](#2.3.5-Automated-Parameter-Identification) | 0.34                          | 36 (assumed)             | 23 (assumed)                 |
| OATP1B1 | 0.477                       | [optimized](#2.3.5-Automated-Parameter-Identification) | 0.34                          | 36 (assumed)             | 23 (assumed)                 |
| OATP1B3 | 0.9                         | assumed to be equal to OATP1B1                         | 0.34                          | 36 (assumed)             | 23 (assumed)                 |



### 2.3.5 Automated Parameter Identification

This is the result of the final parameter identification for the basic model:

| Model Parameter                                             | Optimized Value                                              | Unit      |
| ----------------------------------------------------------- | ------------------------------------------------------------ | --------- |
| `Lipophilicity`                                             | 2.5                                                          | Log Units |
| `Specific intestinal permeability`                          | 1.24E-05                                                     | cm/min    |
| `Fraction unbound (plasma, reference value)`                | 17 FIXED (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)) | %         |
| `Solubility at reference pH`                                | 2800 FIXED (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)) | mg/L      |
| `kcat` AADAC (with a reference concentration of 1 µmol/L)   | 9.865                                                        | 1/s       |
| `kcat` P-gp (with a reference concentration of 1.41 µmol/L) | 0.6088                                                       |           |
| `kcat` OATP1B1 (with a reference concentration of 1 µmol/L) | 7.796                                                        | 1/min     |
| `Emax` AADAC                                                | 0.985                                                        |           |
| `Emax` P-gp                                                 | 2.5 FIXED (see [Section 2.2.1](#2.2.1-In-vitro-and-physico-chemical-data)) |           |
| `Emax` OATP1B1                                              | 0.383                                                        |           |




