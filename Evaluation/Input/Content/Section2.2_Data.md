### 2.2.1 In vitro and physico-chemical data

A literature search was performed to collect available information on physical chemical properties of itraconazole and metabolites. The obtained information from literature is summarized in the table below, and is used for model building.



| **Parameter**                           | **Unit**                           | **Value**        | Source                            | **Description**                                              |
| :-------------------------------------- | ---------------------------------- | ---------------- | --------------------------------- | ------------------------------------------------------------ |
| MW                                      | g/mol                              | 822.940          | [DrugBank DB01045](#5-References) | Molecular weight                                             |
| pK<sub>a,base</sub>                     |                                    | 7.9              | [The Merck Index](#5-References)  | Basic dissociation constant                                  |
| pK<sub>a,acid</sub>                     |                                    | 1.7              | [The Merck Index](#5-References)  | Acid dissociation constant                                   |
| Solubility (pH)                         | mg/L                               | 1100<br />(6.5)  | [Baneyx 2014](#5 References)      | Solubility                                                   |
|                                         |                                    | 1400<br />(6.8)  | [Panchagnula 2006](#5 References) | Solubility                                                   |
|                                         |                                    | 990<br />(4)     | [Agrawal 2005](#5 References)     | Solubility                                                   |
|                                         |                                    | 1650<br />(6)    | [Agrawal 2005](#5 References)     | Solubility                                                   |
|                                         |                                    | 2540<br />(6.8)  | [Agrawal 2005](#5 References)     | Solubility                                                   |
|                                         |                                    | 3350<br />(7.4)  | [Agrawal 2005](#5 References)     | Solubility                                                   |
|                                         |                                    | 2800<br />(7.5)  | [Boman 1974](#5 References)       | Aqueous solubility                                           |
| logP                                    |                                    | 1.3              | [Baneyx 2014](#5 References)      | Partition coefficient between octanol and water @ pH 7.4     |
|                                         |                                    | 2.7              | [DrugBank DB01045](#5-References) | Partition coefficient between octanol and water              |
| fu                                      | %                                  | 11.1             | [Boman 1974](#5 References)       | Fraction unbound in plasma                                   |
|                                         | %                                  | 16.0             | [Baneyx 2014](#5 References)      | Fraction unbound in plasma in tuberculosis patients          |
|                                         | %                                  | 17               | [Templeton 2011](#5-References)   | Fraction unbound in plasma                                   |
|                                         | %                                  | 17.5             | [Shou 2008](#5-References)        | Fraction unbound in plasma                                   |
| B/P ratio                               |                                    | 0.9              | [Loos 1985](#5-References)        | Blood to plasma ratio                                        |
| V<sub>max</sub>, K<sub>m</sub> OATP1B1  | pmol/min/mg,<br />µmol/L           | 9.3<br />1.5     | [Tirona 2003](#5-References)      | OATP1B1 uptake in transfected HeLa cells                     |
| V<sub>max</sub>, K<sub>m</sub> P-gp     | nmol/h/cm<sup>2</sup>,<br />µmol/L | 4.3<br />55      | [Collett 2004](#5-References)     | P-gp net secretion across Caco-2 Monolayers                  |
| V<sub>max</sub>, K<sub>m</sub> AADAC    | pmol/min/mg,<br />µmol/L           | 162.6<br />195.1 | [Nakajima 2011](#5-References)    | Kinetic parameters of the deacetylase activity in HLM        |
| E<sub>max</sub>, EC<sub>50</sub> CYP3A4 | *dimensionless*<br />µmol/L        | 9<br />0.34      | [Templeton 2011](#5-References)   | CYP3A4 induction parameters in primary human hepatocytes,<br />EC<sub>50</sub> corrected for fraction unbound in human hepatocytes of 0.419 [Shou 2008](#5-References) |
| K<sub>i</sub> CYP3A4                    | µmol/L                             | 18.5             | [Kajosaari 2005](5-References)    | CYP3A4 inhibition constant                                   |
| E<sub>max</sub> P-gp                    | *dimensionless*                    | 2.5              | [Greiner 1999](#5-References)     | P-gp induction parameter based on an increased intestinal P-gp content in duodenal biopsies of 3.5 after rifampicin treatment |
| K<sub>i</sub> P-gp                      | µmol/L                             | 169.0            | [Reitman  2011](5-References)     | P-gp inhibition constant                                     |
| K<sub>i</sub> OATP1B1                   | µmol/L                             | 0.477            | [Hirano  2006](5-References)      | OATP1B1 inhibition constant (based on OATP1B1-mediated pitavastatin uptake) |
| K<sub>i</sub> OATP1B3                   | µmol/L                             | 0.9              | [Annaert 2010](5-References)      | OATP1B3 inhibition constant                                  |
| E<sub>max</sub> CYP2C8                  | *dimensionless*                    | 3.2              | [Buckley 2014](5-References)      | CYP2C8 E<sub>max</sub> in primary human hepatocytes (based on activity) |
| K<sub>i</sub> CYP2C8                    | µmol/L                             | 30.2             | [Kajosaari 2005](5-References)    | CYP2C8 inhibition constant                                   |
| E<sub>max</sub> CYP1A2                  | *dimensionless*                    | 0.65             | [Chen 2010](5-References)         | CYP1A2 E<sub>max</sub> in cultured human hepatocytes (based on activity) |
| E<sub>max</sub> CYP2E1                  | *dimensionless*                    | 0.8              | [Rae 2001](5-References)          | CYP2E1 fold induction of 1.8 calculated as the normalized ratio of expression in rifampin-treated versus vehicle control-treated cells. |

*AADAC* arylacetamide deacetylase



### 2.2.2 Clinical data

A literature search was performed to collect available clinical data (plasma concentration, fraction excreted into urine, fraction excreted into bile) on rifampicin in adults. The rifampicin model was built and verified using various clinical studies, covering a dosing range from 300 to 600 mg, administered intravenously or orally.

The following dosing senarios were simulated and compared to respective data:

| Route | Dose<br />[mg] | Dosing                    | PK Data                               | Used for [Optimization](#2.3.5-Automated-Parameter-Identification) | Reference                                         |
| ----- | -------------- | ------------------------- | ------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------- |
| iv    | 300            | SD, 30 min infusion       | Plasma                                | x                                                            | [sanofi-aventis U.S. LLC. 2013](5-References)     |
|       |                | SD, 3 h infusion          | Plasma, excretion into urine          | x                                                            | [Nitti 1977](5-References)                        |
|       | 450            | SD, 3 h infusion          | Plasma, excretion into urine          | x                                                            | [Nitti 1977](5-References)                        |
|       | 600            | SD, 30 min infusion       | Plasma                                | x                                                            | [sanofi-aventis U.S. LLC. 2013](5-References)     |
|       |                | SD, 3 h infusion          | Plasma, excretion into urine          | x                                                            | [Nitti 1977](5-References)                        |
|       |                | SD, 3 h infusion          | Plasma, excretion into urine          | x                                                            | [Acocella 1977](5-References)                     |
|       |                | OD (7 days), 3 h infusion | Plasma                                | x                                                            | [Acocella 1977](5-References)                     |
| po    | 300            | SD                        | Plasma                                | x                                                            | [Chouchane 1995](5-References)                    |
|       |                | SD                        | Plasma                                |                                                              | [Furesz 1970](5-References)                       |
|       | 450            | SD                        | Plasma                                | x                                                            | [Blume 1989](5-References)                        |
|       |                |                           | Plasma                                |                                                              | [Furesz 1970](5-References)                       |
|       |                | MD                        | Plasma, excretion into urine and bile | x                                                            | [Acocella 1972a](5-References)                    |
|       | 600            | SD                        | Plasma                                | x                                                            | [Peloquin 1997](5-References)                     |
|       |                |                           | Plasma                                |                                                              | [Blume 1989](5-References)                        |
|       |                |                           | Plasma                                |                                                              | [Acocella 1972b](5-References)                    |
|       |                |                           | Plasma                                |                                                              | [Furesz 1970](5-References)                       |
|       |                |                           | Plasma, excretion into urine          | x                                                            | [Eon Labs Manufacturing, Inc. 1997](5-References) |
|       |                | OD (7 days)               | Plamsa                                | x                                                            | [Baneyx 2014](5-References)                       |





