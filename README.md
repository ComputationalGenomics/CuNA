# CuNA
Cumulant-based Network Analysis




<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#abstract">Abstract</a>
    </li>
    <li>
      <a href="#citation">Citation</a>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#download">Download</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
      <ul>
        <li><a href="#options">Options</a></li>
        <li><a href="#input">Input</a></li>
        <li><a href="#output">Output</a></li>
      </ul>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#license">License</a></li>
  </ol>
</details>



<!-- Abstract -->
## Abstract

Parkinson's Disease (PD) is a progressive neurodegenerative movement disorder characterized by loss of 
striatal dopaminergic neurons. Progression of PD is usually captured by a host of clinical features 
represented in different rating scales. PD diagnosis is associated with a broad spectrum of non-motor 
symptoms such as depression, sleep disorder as well as motor symptoms such as movement impairment, etc. 
The variability within the clinical phenotype of PD makes detection of the genes associated with early 
onset PD a difficult task. To address this issue, we developed CuNA, a cumulant-based network analysis 
algorithm that creates a network from higher-order relationships between eQTLs and phenotypes as captured 
by cumulants. We also designed a multi-omics simulator, CuNAsim to test CuNA's qualitative accuracy.
CuNA accurately detects communities of clinical phenotypes and finds genes associated with them. When 
applied on PD data, we find previously unreported genes INPP5J, SAMD1 and OR4K13 associated with symptoms 
of PD affecting the kidney, muscles and olfaction. CuNA provides a framework to integrate and analyze RNA-seq, 
genotype and clinical phenotype data from complex diseases for more targeted diagnostic and therapeutic 
solutions in personalized medicine.

<!-- Citation -->
## Citation
Aritra Bose, Daniel Platt, Niina Haiminen and Laxmi Parida. 
CuNA: Cumulant-based Network Analysis of genotype-phenotype relationships in Parkinson's Disease

<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple example steps.

### Download

To download please run:

`git clone https://github.com/ComputationalGenomics/CuNA.git`

<!-- USAGE EXAMPLES -->
## Usage

The command to run CuNA

```
./CuNA --file MockData.xlsx 
```

This is a default example. You can change the parameters as you see fit. 


### Options
```
usage: CuNAwrapper [-h] \
                
usage: CuNAwrapper [-h] [-f FILE] [-p FLOAT] [-z FLOAT] [-c INT] [-a BOOL]
                   [-t FILE]

optional arguments:
  -h, --help            show this help message and exit
  -f FILE, --file FILE  Enter the file with all features (phenotypes,
                        genotypes and gene expression) in Excel format
  -p FLOAT, --pval FLOAT      Enter the pvalue threshold for cumulant significance
                        (default is 0.0001)
  -z FLOAT, --zscore FLOAT      Enter the zscore threshold for cumulant significance
                        (default is 3)
  -c INT, --pc INT        Enter the percentage of edges in the network (default
                        is 1)
  -a BOOL, --annot BOOL
                        Enter the annotation binary flag (default is 0)
  -t FILE, --atf FILE
                        Enter the annotation file in tab delimited format
 
```

## Input

There is ONE necessary input for CuNAwrapper. It is a tab delimited Excel (.xlsx) file containing the phenotypes, SNPs and gene expression variables for each sample. 
Please refer to MockData.xlsx for a sample input. 



## Output
There are three outputs.  Two network files for the entire graph and for the Maximum Spanning Tree (MST). The  network files can be used to generate networks in standard 
software like Cytoscape for further analysis and visualization. It also generates a separate  file for the communities obtained from the network. 

 - The full network file for the user-defined percentage of edges. 
 - Maximum Spanning Tree 
 - Communities observed from the network. Each row is one community. 
 
 
<!-- CONTACT -->
## Contact

For assistance with running CuNA, interpreting the results, or other related questions, 
please feel free to contact: Laxmi Parida <parida@us.ibm.com> or Aritra Bose <a.bose@ibm.com>

<!-- LICENSE -->
## License

See [LICENSE](https://github.com/ComputationalGenomics/CuNA/blob/master/license) for license information.
