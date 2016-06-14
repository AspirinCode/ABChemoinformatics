# ABC of Chemoinformatics

... with focus on macromolecule-ligand interactions.

Inspired by magnus' [RNA Structural Bioinformatics Crash Course](https://github.com/mmagnus/RNA-Structural-Bioinformatics-Crash-Course/blob/master/README.md#rna-structural-bioinformatics-crash-course)

![email](data/email.png)

# TOC

# Intro - to read

- https://en.wikipedia.org/wiki/Enzyme_inhibitor
- https://en.wikipedia.org/wiki/Enzyme_assay
- https://en.wikipedia.org/wiki/Biological_target
- https://en.wikipedia.org/wiki/Drug_design
- https://en.wikipedia.org/wiki/ADME
- https://en.wikipedia.org/wiki/Quantitative_structure%E2%80%93activity_relationship
- https://en.wikipedia.org/wiki/Docking_%28molecular%29

## Basic concepts

### Molecular scaffolds

![scaffolds](data/scaffolds.png)

### Ligands activity measures

* **IC50** - half maximal inhibitory concentration [wiki](https://en.wikipedia.org/wiki/IC50)
  *  **pIC50** = -log(IC50)
* **EC50** - half maximal effective concentration
* **LD50**  - median lethal dose
* **Ki** - binding affinity - describes the interaction of most ligands with their binding sites; high-affinity ligand binding results from greater intermolecular force between the ligand and its receptor while low-affinity ligand binding involves less intermolecular force between the ligand and its receptor. In general, high-affinity binding involves a longer residence time for the ligand at its receptor binding site than is the case for low-affinity binding. 

The median affinity (IC50, EC50, ED50, Ki, Kd) for current small-molecule drugs is around **20 nM** (source: doi:10.1038/nrd2199)


# Software

## Drawing and visualizing small molecules

MarvinSketch from MarvinBeans Suite. Download for free (after registration): https://www.chemaxon.com/download/marvin-suite/#mbeans

:zap: **Practicals:**
- Draw the LSD molecule
- Save it as smiles, mol2, sdf
- copy it to clipboard as smiles and paste to the notepad
- optimize the 3D structure


## Molecule formats and formats conversion

- http://openbabel.org/wiki/Main_Page
- http://openbabel.org/docs/current/Command-line_tools/babel.html

:zap: **Practicals:**
- convert saved molecules to sdf, mol2 and PDB
- add hydrogens
- optimize 3D structure
- generate conformers


## Pymol

See: https://github.com/mmagnus/RNA-Structural-Bioinformatics-Crash-Course/blob/master/README.md#pymol

## KNIME

- Download: https://www.knime.org/knime
- Quick Start Guide: https://tech.knime.org/files/KNIME_quickstart.pdf (PDF)

:zap: **Practicals:**

- From the ChemBlDb, download IC50 activity for JAK2 Kinase
- prepare a workflow:
 - Read the data from CSV file
 - convert smiles string to structures
 - calculate moelcular descriptors: AMW, logP, TPSA
 - calculate logBB according to the formlula: ![formula](https://raw.githubusercontent.com/filipsPL/CADD-PW/master/KNIME/JAK/BBB.png) (:bulb: use Math Node)
 - calculate the pareto rank, minimizing IC50 value, MW, logP and TPSA

- For these data:
 - Create a 3D plot:
 - xyz: TPSA / logP / AMW
 - color by: IC50
 - points size: logBB
 - save as png
- play with another types of plot (parallel coordinates, bar plots, conditional bar plots etc)
- sort the table according to Pareto Ran value (ascending)
- save 10 top ranking compounds to csv and xls files.


# Databases and online tools :: macromolecules

## Scientific literature
* Pubmed: http://www.ncbi.nlm.nih.gov/pubmed/
* Google scholar: https://scholar.google.pl/

## Patents
* google patents: http://www.google.com/patents
* espace net: http://worldwide.espacenet.com/
  * depatis net: https://depatisnet.dpma.de
* WIPO: https://patentscope.wipo.int/search/en/search.jsf
* https://www.surechembl.org/search/ - Open Patent Data


## Sequences

* http://www.uniprot.org/ high-quality and freely accessible resource of protein sequence and functional information.
* http://www.ebi.ac.uk/interpro/ - provides functional analysis of proteins by classifying them into families and predicting domains and important sites

### Similar sequences

* http://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE=Proteins&PROGRAM=blastp&RUN_PSIBLAST=on - search protein databases using a protein query. 
* http://www.ebi.ac.uk/Tools/sss/ncbiblast/ - to find regions of sequence similarity, which will yield functional and evolutionary clues about the structure and function of your novel sequence. 
* http://toolkit.tuebingen.mpg.de/cs_blast CS-BLAST is an extension to standard NCBI BLAST that allows to increase its sensitivity by a factor of more than two on remote homologs at the same speed.
* http://toolkit.tuebingen.mpg.de/hhpred - Homology detection & structure prediction by HMM-HMM comparison
* Inne: http://toolkit.tuebingen.mpg.de/sections/search


### Sequences Alignment
* Pairwise Sequence Alignment: https://www.ebi.ac.uk/Tools/psa/
* Multiple Sequence Alignment: http://www.ebi.ac.uk/Tools/msa/clustalo/

## Other

* https://www.targetvalidation.org/

-----

:zap: **Practicals:**
1. Find residues crutial for 2'-O-methyltransferase activity of Dengue virus type 2 (strain Thailand/16681/1984)
1. Find all sequences containing mRNA cap 0-1 NS5-type MT domain
1. Find reviewed sequences of Flaviviridae methyltransferases (`taxonomy: Flaviviridae`)

1. Find sequences similar to the human IDO1 proteins
1. What are differences between four most similar sequences?
 
# Databases and online tools :: small molecules

## Chemical structures

* http://zinc.docking.org/ (aspirin)
* https://pubchem.ncbi.nlm.nih.gov/
* http://www.chemspider.com/
* http://www.emolecules.com/

## Activity
* https://www.ebi.ac.uk/chembl/ :boom:
* Also: https://pubchem.ncbi.nlm.nih.gov/ - BioAssay
* http://www.bindingdb.org/bind/index.jsp
* http://chemoinfo.ipmc.cnrs.fr/MOLDB/index.html - e-Drug3D offers a facility to explore FDA approved drugs and active metabolites.
* http://bitterdb.agri.huji.ac.il/ - currently holds over 680 bitter compounds obtained from the literature and from Merck index and their associated 25 human bitter taste receptors (hT2Rs). 
* http://www.eidogen-sertanty.com/kinasekb.php - Kinase Knowledgebase (KKB)
* https://www.ebi.ac.uk/chembl/malaria/ - resource for publicly available compounds, targets, assays and data for malaria research

## Other
* http://www.swissbioisostere.ch/ - baza izosterów (COOH)

## Drugs
* http://www.drugbank.ca/ (1-phenyl-2-aminopropane)
* http://bidd.nus.edu.sg/group/ttd/ttd.asp (ALK)
* https://www.ebi.ac.uk/chembl/drugstore
* http://www.genome.jp/kegg/drug/ -  a comprehensive drug information resource for approved drugs in Japan, USA, and Europe unified based on the chemical structures and/or the chemical components, and associated with target, metabolizing enzyme, and other molecular interaction network information.

## Metabolites
* http://www.hmdb.ca/ - detailed information about small molecule metabolites found in the human body
  * Np: L-tyrosine http://www.hmdb.ca/metabolites/HMDB00158
* http://www.ebi.ac.uk/metabolights/index -  a database for Metabolomics experiments and derived information.
The database is cross-species, cross-technique and covers metabolite structures and their reference spectra as well as their biological roles, locations and concentrations, and experimental data from metabolic experiments. (urea)
* http://smpdb.ca/ - SMPDB (The Small Molecule Pathway Database) - an interactive, visual database containing more than 618 small molecule pathways found in humans
 * cykl mocznikowy ("Urea Cycle")

## ADMET properties estimation

* http://www.organic-chemistry.org/prog/peo/ - OSIRIS Property Explorer



:zap: **Practicals:**

* Find all activities of the compound:

![structure](https://raw.githubusercontent.com/filipsPL/CADD-PW/master/elementy/bazy_danych/dopalacz.png)

* Find all registered drugs that targets RNA
* Find possible bioisosteres of 3-methylindole (R in position 5)

* For compound named `(2S)-4-[3-(5-methyl-2-furyl)benzofuran-2-yl]-2-phenyl-butan-2-ol`
 - find vendors
 - find calculated values of logP i TPSA
 - find comercially available compounds that are similar at 80% (Tanimoto similarity)

* For compound:

![zapytanie](https://raw.githubusercontent.com/filipsPL/CADD-PW/master/elementy/bazy_danych/zapytanie_patentowe.png)

 - Find patents mentioning this structure
