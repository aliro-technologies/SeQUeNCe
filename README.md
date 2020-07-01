# SeQUeNCe-Python

SeQUeNCe is an open source, discrete-event simulator for quantum networks. As described in our paper TODO: link?, the simulator includes 5 modules on top of a simulation kernel:
* Hardware
* Entanglement Management
* Resource Management
* Network Management
* Application

These modules can be edited by users to define additional functionality and test protocol schemes, or may be used as-is to test network parameters and topologies. TODO: link to full documentation page

## Installing
SeQUeNCe requires an installation of Python 3.7. this can be found at the [Python Website](www.python.org/downloads/). Then, simply download the package, navigate to its directory, and install with
```
$ pip install .
```
Or, using the included makefile,
```
$ make install
```
This will install the sequence library as well as the numpy, json5, and pandas dependancies.

## Usage Examples
Many examples of SeQUeNCe in action can be found in the example folder. These include both quantum key distribution and entanglement distribution examples.

### Starlight Experiments
Code for the experiments performed in our paper can be found in the file `starlight_experiments.py`. This script uses the `starlight.json` file (also within the example folder) to specify the network topology.

### Jupyter Notebook Examples
The example folder contains several scripts that can be run with jupyter notebook for easy editing and visualization. These files require that the notebook package be installed:
```
$ pip install notebook
```
To run each file, simply run
```
$ jupyter notebook <filename>
```
These examples include:
* `BB84_eg.ipynb`, which uses the BB84 protocol to distribute secure keys between two quantum nodes
* `two_node_eg.ipynb`, which performs entanglement generation between two adjacent quantum routers
* `three_node_eg_ep_es.ipynb`, which performs entanglement generation, purification, and swapping for a linear network of three quantum routers

## Additional Tools

### Network Visualization
The example directory contains an example json file `starlight.json` to specify a network topology and a the script `draw_topo.py` to visualize json files. To use this script, the Graphviz library must be installed. Installation information can be found on the [Graphviz website](www.graphviz.org/download/).

To view a network, simply run the script and specify the relative location of your json file:
```
$ python example/draw_topo.py example/starlight.json
```
This script also supports a flag `-m` to visualize BSM nodes created by default on quantum links between routers.
