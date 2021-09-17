### 2.3.1 Absorption

Herein, the model parameter `Specific intestinal permeability` was optimized to best match clinical data (see  [Section 2.3.5](#235-automated-parameter-identification)). The results of the optimization can be found in [Section 2.3.5](#235-automated-parameter-identification).

Measured aqueous solubility ([Boman 1974](#5-references), see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)) was set as default solubility.

As observed data do not show substantial differences between different formulations for oral rifampicin administration, all oral administrations were modelled as an oral solution.

### 2.3.2 Distribution

Recent measurements of fraction unbound in plasma yielded values of approximately 17% ([Templeton 2011](#5-references), [Shou 2008](#5-references), see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)). This value was implemented in this model.

`Lipophilicity` was optimized within the range of measured values to find a best match of simulated to observed rifampicin PK profile data.

After testing the available organ-plasma partition coefficient and cell permeability calculation methods built in PK-Sim®, observed clinical data was best described by choosing the partition coefficient calculation by `Rodgers and Rowland` and cellular permeability calculation by `PK-Sim Standard ` for rifampicin. The PK-Sim® calculated `Blood/plasma concentration ratio` is well in line with the observed value of 0.9 ([Loos 1985](#5-references)).

### 2.3.3 Metabolism and Elimination

Integrating and testing active processes that were considered vital to the PK of rifampicin after literature review resulted in a final model that applies transport by OATP1B1 ([Tirona 2003](#5-references)), metabolism by arylacetamide deacetylase (AADAC) ([Nakajima 2011](#5-references)), transport by P-gp ([Collett 2004](#5-references)) and glomerular filtration. No study clearly demonstrated that rifampicin is substrate of CYP3A4; hence, in this PBPK model rifampicin only acts as a perpetrator on CYP3A4 without being metabolized by it.

The implemented expression profile of AADAC, P-gp and OATP1B1 were based on high-sensitive real-time RT-PCR ([Nishimura 2003](#5-references)) of the PK-Sim® expression database. The relative expression in the mucosa of the gut wall was modified based on an optimized value as reported by Hanke *et al.* ([Hanke 2018](#5-references)). Herein, this value was increased by a factor of 3.57 based on digoxin PK data in combination with PBPK modeling.

It was assumed that the mRNA concentration is proportional to the respective protein concentration. Thus, the expression of a protein in a specific organ relates to the expression in the organ with the highest expression which is termed reference concentration of the protein ([Meyer 2012](#5-references)). OATP1B1 was configured as influx transporter and P-gp as efflux transporter. Reference concentrations of the implemented active processes (enzymes and transporters) are summarized below:

| Protein | Reference concentration<br />[µmol/L] | Reference Organ        |
| ------- | ------------------------------------- | ---------------------- |
| AADAC   | 1.0 (assumed)                         | Liver                  |
| P-gp    | 1.41 ([Hanke 2018](#5-references))    | Mucosa Small Intestine |
| OATP1B1 | 1.0 (assumed)                         | Liver                  |

The kinetic parameters describing the rifampicin metabolism by AADAC and transport by P-gp and OATP1B1 were imputed in the model as follows: while Michaelis-Menten constants (K<sub>m</sub> values) of AADAC-catalyzed metabolism and the two transport processes were taken from reported in vitro experiments, enzymatic and transport turnover values (k<sub>cat</sub>) were optimized based on *in vivo* PK data (see [Section 2.3.5](#235-automated-parameter-identification)).

Multiple dose studies that measured PK profiles of rifampicin at different days of a 600 mg po once daily regimen indicate that rifampicin exposure decreases over time due to auto-induction processes ([Baneyx 2014](#5-references)), ([Smythe 2012](#5-references)). *In-vitro* studies in human hepatocytes suggest that rifampicin induces P-gp ([Collett 2004](#5-references), [Dixit 2007](#5-references), [Williamson 2013](#5-references)) and OATP1B1 ([Dixit 2007](#5-references), [Williamson 2013](#5-references)). It has further been shown in DDI studies with prototypical substrates of these transporters (pravastatin and digoxin, respectively) that the induction of these transporters can also be observed *in vivo* ([Kyrklund 2000](#5-references), [Greiner 1999](#5-references)). As in the case of CYP3A4 induction, both induction processes are mediated via pregnane X receptor (PXR) ([Geick 2001](#5-references)). Furthermore, it has been demonstrated that B-esterases are inducible by rifampicin via PXR ([Smythe 2012](#5-references), [Staudinger 2010](#5-references)) and that AADAC, the enzyme catalyzing the main metabolic pathway of rifampicin, is regulated by PXR ([Zhang 2012](#5-references)). Therefore, (auto-)induction of P-gp, OATP1B1 and AADAC expression was assumed and implemented in the rifampicin model. Modelling induction of an endogenously expressed protein requires three parameters, in particular **EC<sub>50</sub>** (concentration at which induction is half maximum), **E<sub>max</sub>** (maximum induction effect on endogenous synthesis rate) and the endogenous **protein turnover (half-life)**. Little is known about these values *in vivo* for AADAC, P-gp and OATP1B1 induction. 

#### (Auto-) Induction Processes: AADAC, P-gp and OATP1B1

##### EC<sub>50</sub>

As all induction processes are mediated by PXR, the same unbound EC<sub>50</sub> of 0.34 µmol/L (originally measured in primary human hepatocytes for CYP3A4 induction after correcting for the fraction unbound ([Baneyx 2014](#5-references), [Shou 2008](#5-references), [Templeton 2011](#5-references))) was applied for all induction processes. This assumption is supported by the fact that Moore *et al.* [Moore 2000](#5-references) found a general EC<sub>50</sub> value for PXR-mediated rifampicin induction of 0.71 µmol/L (resulting in an unbound EC<sub>50</sub> of 0.30 µmol/L after correcting for the fraction unbound reported by [Shou 2008](#5-references)). 

##### E<sub>max</sub>

E<sub>max</sub> values for AADAC and OATP1B1 are unknown and fitted based on observed clinical PK data of rifampicin (see [Section 2.3.5](#235-automated-parameter-identification)).

A study by Greiner et al. ([Greiner 1999](#5-references)) found 3.5-fold elevated P-gp levels in human duodenal biopsies after multiple doses of rifampicin. This value was assumed to represent an *in vivo* maximum effect corresponding to an E<sub>max</sub> value of 2.5. This E<sub>max</sub> was included in the model for P-gp induction (see also [Section 2.2.1](#221-in-vitro-and-physicochemical-data)).

##### Protein turnover (half-lives)

Endogenous half-lives of these proteins are not known. Therefore, the same values applicable for CYP3A4 turnover (as implemented in PK-Sim ([PK-Sim Ontogeny Database Version 7.3](#5-references)) were assumed, i.e. 36 hours in the liver ([Obach 2007](#5-references)) and 23 hours in the intestine ([Greenblatt 2003](#5-references)).

### 2.3.4 DDI Parameters

The following sub-section describe the model input for DDI-related parameters, i.e. induction and inhibition of certain enzymes and transporters, for which rifampicin may act as a perpetrator. Verification of these model parameters and linked processes is not evaluated in this report. Applications are assessed in specific use cases and reported elsewhere. 

#### CYP3A4 induction and inhibition
Induction of CYP3A4 was incorporated using the weighted mean **EC<sub>50</sub>** of 0.8 µmol/L and **E<sub>max </sub>** estimate of 9 based on CYP3A4 activity induction in primary human hepatocytes ([Templeton 2011](#5-references), see also [Section 2.2.1](#221-in-vitro-and-physicochemical-data)). Similar values for EC<sub>50</sub> (0.77, 0.80 µmol/L) and E<sub>max </sub> (7, 9, 10) have been reported by other groups ([Kolars 1992](#5-references), [Mills 2004](#5-references), [Sahi 2000](#5-references)). The *in vitro* value of EC<sub>50</sub> of 0.8 µmol/L was corrected by the unbound fraction of rifampicin in hepatocytes of 0.419 to obtain an **unbound EC<sub>50</sub>** value of 0.34 µmol/L ([Baneyx 2014](#5-references), [Shou 2008](#5-references), [Templeton 2011](#5-references)) which was used in the PBPK model. 

Competitive inhibition of CYP3A4 by rifampicin was included using a dissociation (inhibition) constant (**K<sub>i</sub>**) of 18.5 µmol/L determined in human liver microsomes via inhibition of midazolam 1-hydroxylation ([Kajosaari 2005](#5-references)). No correction of this *in vitro* value was applied to account for potential binding in the assay, as only 0.1 mg/mL human liver microsomal protein was used and a negligible unbound fraction of 0.90 – 0.98 was predicted ([Austin 2002](#5-references)).

Time to reach newly induced CYP3A4 levels and time for de-induction depends on the half-lives of the perpetrator drug but also of the endogenous natural turnover of the induced protein. CYP3A4 turnover featured zero-order synthesis rate and first-order degradation rate. A distinct degradation rate constant (k<sub>deg</sub>) was considered for the intestinal mucosa which rather reflects enterocytic turnover than protein turnover, while in all other CYP3A4 expressing organs CYP3A4 turnover was assumed to follow that of the liver. **CYP3A4 half-life** (= ln(2)/k<sub>deg</sub>) of 23 and 36 h in intestine and liver, respectively, were incorporated ([Obach 2007](#5-references), [Greenblatt 2003](#5-references), [PK-Sim Ontogeny Database Version 7.3](#5-references)).

#### P-gp induction and inhibition
P-gp induction is described above.

An *in vitro* determined K<sub>i</sub> value for rifampicin ([Reitman 2011](#5-references)) served directly as model input (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)).

#### OATP1B1 induction and inhibition

OATP1B1 induction is described above. 

An *in vitro* determined K<sub>i</sub> value for rifampicin ([Hirano 2006](#5-references)) served directly as model input (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)).

#### OATP1B3 induction and inhibition

The same parameters as for OATP1B1 induction were assumed.

An *in vitro* determined K<sub>i</sub> value for rifampicin ([Annaert 2010](#5-references)) served directly as model input (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)).

#### CYP2C8 induction and inhibition

For PXR-mediated induction, the same unbound EC<sub>50</sub> of 0.34 µmol/L (originally measured in primary human hepatocytes for CYP3A4 induction after correcting for the fraction unbound ([Baneyx 2014](#5-references), [Shou 2008](#5-references), [Templeton 2011](#5-references))) was applied (see above).

An E<sub>max</sub> value reported by Buckley *et al.* ([Buckley 2014](#5-references)) served as model input (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)).

CYP2C8 half-life of 23 h in the liver ([Renwick 2000](#5-references), [PK-Sim Ontogeny Database Version 7.3](#5-references)) and of 23 h in the intestine (assuming that the turnover here rather reflects enterocytic turnover than protein turnover) ([Greenblatt 2003](#5-references), [PK-Sim Ontogeny Database Version 7.3](#5-references)) were incorporated.

An *in vitro* determined K<sub>i</sub> value for rifampicin ([Kajosaari 2005](#5-references)) served directly as model input.

#### CYP1A2 induction

For PXR-mediated induction, the same unbound EC<sub>50</sub> of 0.34 µmol/L (originally measured in primary human hepatocytes for CYP3A4 induction after correcting for the fraction unbound ([Baneyx 2014](#5-references), [Shou 2008](#5-references), [Templeton 2011](#5-references))) was applied (see above).

An E<sub>max</sub> value reported by Chen *et al.* ([Chen 2010](#5-references)) served as model input (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)).

CYP1A2 half-life of 39 h in the liver ([Obach 2007](#5-references), [PK-Sim Ontogeny Database Version 7.3](#5-references)) and of 23 h in the intestine (assuming that the turnover here rather reflects enterocytic turnover than protein turnover) ([Greenblatt 2003](#5-references), [PK-Sim Ontogeny Database Version 7.3](#5-references)) were incorporated.

#### CYP2E1 induction

For PXR-mediated induction, the same unbound EC<sub>50</sub> of 0.34 µmol/L (originally measured in primary human hepatocytes for CYP3A4 induction after correcting for the fraction unbound ([Baneyx 2014](#5-references), [Shou 2008](#5-references), [Templeton 2011](#5-references))) was applied (see above).

An E<sub>max</sub> value reported by Rae *et al.* ([Rae 2001](#5-references)) served as model input (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)).

CYP2E1 half-life of 50 h in the liver ([Emery 1999](#5-references), [PK-Sim Ontogeny Database Version 7.3](#5-references)) and of 23 h in the intestine (assuming that the turnover here rather reflects enterocytic turnover than protein turnover) ([Greenblatt 2003](#5-references), [PK-Sim Ontogeny Database Version 7.3](#5-references)) were incorporated.

#### Summary DDI Parameters

| Protein | K<sub>i</sub><br />[µmol/L] | E<sub>max</sub><br />                                | EC<sub>50,u</sub><br />[µmol/L] | Half-life<br />liver [h] | Half-life<br />intestine [h] |
| ------- | --------------------------- | ---------------------------------------------------- | ------------------------------- | ------------------------ | ---------------------------- |
| CYP1A2  | -                           | 0.65                                                 | 0.34                            | 39                       | 23 (assumed)                 |
| CYP2C8  | 30.2                        | 3.2                                                  | 0.34                            | 23                       | 23 (assumed)                 |
| CYP2E1  | -                           | 0.8                                                  | 0.34                            | 50                       | 23 (assumed)                 |
| CYP3A4  | 18.5                        | 9                                                    | 0.34                            | 36                       | 23                           |
| AADAC   | -                           | [optimized](#235-automated-parameter-identification) | 0.34                            | 36 (assumed)             | 23 (assumed)                 |
| P-gp    | 169                         | [optimized](#235-automated-parameter-identification) | 0.34                            | 36 (assumed)             | 23 (assumed)                 |
| OATP1B1 | 0.477                       | [optimized](#235-automated-parameter-identification) | 0.34                            | 36 (assumed)             | 23 (assumed)                 |
| OATP1B3 | 0.9                         | assumed to be equal to OATP1B1                       | 0.34                            | 36 (assumed)             | 23 (assumed)                 |



### 2.3.5 Automated Parameter Identification

This is the result of the final parameter identification:

| Model Parameter                                             | Optimized Value                                              | Unit      |
| ----------------------------------------------------------- | ------------------------------------------------------------ | --------- |
| `Lipophilicity`                                             | 2.5                                                          | Log Units |
| `Specific intestinal permeability`                          | 1.24E-05                                                     | cm/min    |
| `Fraction unbound (plasma, reference value)`                | 17 FIXED (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)) | %         |
| `Solubility at reference pH`                                | 2800 FIXED (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)) | mg/L      |
| `kcat` AADAC (with a reference concentration of 1 µmol/L)   | 9.865                                                        | 1/min     |
| `kcat` P-gp (with a reference concentration of 1.41 µmol/L) | 0.6088                                                       | 1/min     |
| `kcat` OATP1B1 (with a reference concentration of 1 µmol/L) | 7.796<sup>*</sup>                                            | 1/min     |
| `Emax` AADAC                                                | 0.985                                                        |           |
| `Emax` P-gp                                                 | 2.5 FIXED (see [Section 2.2.1](#221-in-vitro-and-physicochemical-data)) |           |
| `Emax` OATP1B1                                              | 0.383                                                        |           |

<sup>*</sup> The value in the model was updated to 5.210 with the release of PK-Sim 10 to account for the updated calculation method of interstitial concentrations (please refer to the respective [release notes of version 10](https://github.com/Open-Systems-Pharmacology/Suite/releases/tag/v10.0)).

