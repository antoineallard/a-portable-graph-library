## PGL: A portable graph library

PGL provides a set of C++<!--/Python--> objects and Python scripts to analyze, manipulate and simulate the structure of graphs (or [complex networks]).

Except for a few exceptions, every objects provided by the PGL are written in standard C++. They are provided via self-contained header files making them easily integrable into any C++ project (can be included similarly to any header-only libraries such as [Boost] or the [STL]).

<!--- Some functionalities of the C++ library are also available as a Python module. Objects in this module are simple wrappers around the C++ objects generated by [pybind11].--->

### Why another graph library?

The development of this library was motivated by the need of a __fast__, __lightweight__ and __customizable__ code, which was __easy to install__ and straightforward to deploy on __supercomputing facilities__ whose softwares are not always up-to-date.

At the beginning of this project, none of the existing high-quality libraries such as [graph-tool], [NetworkX] or [igraph] fulfilled the aforementionned requirements.

I therefore decided to start writing my own code, adding new features following the needs of my research. This is a work in progress; comments, suggestions, contributions and bug reports are welcome.

### Requirements

  * A C++11 (or newer) compliant compiler
  <!--- * python 3.x (for the Python module)--->
  <!--- * [pybind11] (for the Python module; should be installed automatically)--->


### Installation<!-- (Linux, OS X)-->

Clone this reporsitory using the `--recurse-submodules` option (see [Git documentation]), for example:
```
git clone --recurse-submodules https://github.com/antoineallard/a-portable-graph-library.git
```

<!--- ##### C++--->
  * copy the required header file (`<sub-module>/src/<class object>.hpp`) file in your project directory.
  * add `#include "<class object>.hpp"` to your C++ code

<!--- ##### Python module
  * clone this repository
  * `cd a-portable-graph-library`
  * `pip3 install --global-option=build_ext --global-option="-I"${PWD} python_module_setup/`
  * add `import pgl` to your Python script--->


### Available sub-modules

No extensive documentation is available. However we provide several tutorials in the form of C++ codes and Jupyter notebooks to illustrate how to use the PGL. Codes validating several functionalities of the `pgl` are located in most sub-module's `validation/` sub-directory and provide additional examples.

#### Structure of graphs

  * `directed_graph`: Provides functions to compute and extract various structural properties of simple directed graphs without self-loops.
<!--- Most of these functionalities are also available in the `pgl` Python module.--->


#### Random graph generators

  * `geometric_Sd_model`: Generates random geometric graphs according to the S^D model.

<!---* `lcloning.py` [[source]](src_python/lcloning.py): A python script that generates an undirected edgelist using the [L-cloning algorithm][6]. As the number of copies goes to infinity, the generated edgelist belongs to the ensemble considered in the message passing approach.--->


#### Percolation on graphs

  * `percolation_on_graph`: Provides functions to efficiently simulate bond percolation on simple undirected graphs without self-loops.



[Boost]:              https://www.boost.org
[complex networks]:   https://en.wikipedia.org/wiki/Complex_network
[Eigen]:              http://eigen.tuxfamily.org
[Git documentation]:  https://git-scm.com/book/en/v2/Git-Tools-Submodules
[graph-tool]:         https://graph-tool.skewed.de/
[igraph]:             https://igraph.org/
[NetworkX]:           https://networkx.github.io/
[pybind11]:           https://github.com/pybind/pybind11
[Spectra]:            https://spectralib.org/
[STL]:                https://en.cppreference.com/w


[2]: http://doi.org/10.1103/PhysRevE.64.026118
[5]: http://doi.org/10.1103/PhysRevLett.113.208702
[6]: http://doi.org/10.1103/PhysRevE.91.052807
