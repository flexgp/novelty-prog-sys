# Program Synthesis with Novelty Search

## Installation
This repository is adapted from the PonyGE2 repository, which can be seen in 
[src/PonyGE2](src/PonyGE2). Important installation instructions can be found in the README there regarding 
general setup, and a link to the original repository is included as well. In the 
original repository there is a detailed wiki documenting how much of the GE algorithm 
works. 

The python version used when running experiments was 3.5.2. 
Make sure to install the requirements in the requirements.txt file in both 
the src folder and the PonyGE2 folder.

## Adding Novelty

Novelty experiments can be run by adjusting the novelty parameters in 
[src/PonyGE2/parameters/progsys.txt](src/PonyGE2/parameters/progsys.txt).

Important parameters include:  
__SELECTION__ - Use "lexicase_and_novelty" to run a combination of novelty search and 
lexicase selection.   
__NOVELTY_SELECTION_ALG__ -  choices are 'knob', to use a static knob; 'exp' to use an 
exponentially decaying knob, and 'adapt' to use an adaptive knob based on number of duplicates
in population.   
__NOVELTY_FACTOR__ - when run with the NOVELTY_SELECTION_ALG set to 'knob', this will 
set the static knob value. If set to zero, don't use any novelty selection, if set to 1 
use pure novelty selection.   
__NOVELTY_ALGORITHM__ - Choose one of five different novelty algorithms to use when novelty 
search is chosen. Valid options include 'genotype', 'phenotype', 'ast', 'derivation', and 'output'.  
__NOVELTY_BY_GEN__: - Use the knob on a per generation basis, or on a per individual basis. 


## Notes
Novelty search may not work for all problem choices located in [src/PonyGE2/grammars/progsys](src/PonyGE2/grammars/progsys) as some 
modifications have been made to the grammars. However, it should definitely work for 
Median, Smallest, String Lengths Backwards, Number IO, Negative To Zero, Vectors Summed, and 
Small or Large. 