#	Relational Concept Analysis on a simple model with FCA4J

In this document, you will find the command lines to apply RCA to the **Esport** example.

The used scaling operator is written in the .rcft file. The written operator is **exist** (see [esport.rcft](../TP/Esport/esport.rcft)).

STEP 0- Download files fca4j-cli-0.4.jar at https://www.lirmm.fr/fca4j/ and [esport.rcft](../TP/Esport/esport.rcft)

STEP 1- Assume or move fca4j-cli-0.4.jar in current Directory `./`

STEP 2- Create directory ./Esport 

```bash
mkdir ./Esport
```	
Assume or move [esport.rcft](../TP/Esport/esport.rcft) in Directory './Esport'

STEP 3- Build the Relational Lattice Family (set of lattices)
- Create directory ./Esport/Lattice
```bash
mkdir ./Esport/Lattice
```
- Launch fca4j
```bash
java -jar fca4j-cli.jar RCA ./Esport/esport.rcft ./Esport/Lattice -v -a ADD_EXTENT
```
- This builds several files including:
	- [esport.json](../TP/Esport/Lattice/esport.json) that can be used to navigate the lattices with RCAviz (http://rcaviz.lirmm.fr/).
	- [step2.dot](../TP/Esport/Lattice/step2.dot) which contains the set of connected lattices (the Relational Lattice Family). 
	- several `.txt` files containing metrics (step, number of concepts and relational attributes)
- To produce a pdf view of the lattice, we can use Graphviz (https://graphviz.org/) 

```bash
dot -Tpdf ./Esport/Lattice/step2.dot -o ./Esport/step2.pdf
```