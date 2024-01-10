Welcome to the documentation of PyWLK
=====================================

PyWLK is a Python implementation of the Weisfeiler-Lehman Graph Kernels (WLKs). It is based on the paper by ? et al.
The main improvement over other tools is that PyWLK can be installed from PyPI and Anaconda for any current python
version, i.e. Python 3.8 and newer.

Installation
------------

PyWLK can be installed from PyPI using pip:

.. code-block:: bash

    pip install pywlk

or from Anaconda using conda:

.. code-block:: bash

    conda install -c conda-forge pywlk

Usage
-----

After installation, PyWLK can be used as follows:

.. code-block:: python

    from pywlk import wlk
    import numpy as np

    adjs = np.random.randint(0, 1, size=(2, 10, 10))
    adjs = np.array(adjs + adjs.transpose(0, 2, 1), dtype=np.int32)
    labels = np.ones((2, 10), dtype=np.int32)
    wlk(adjs, labels, k=4)

PyWLK takes as input a stack of adjacency matrices (:code:`adjs`) and a stack of node labels (:code:`labels`). The
adjacency matrices must be symmetric, whereas the labels can have any type. Additionally, one can specify a :code:`k`
to control how many iterations of the kernel will be computed.

.. toctree::
    :maxdepth: 1
    :caption: Usage

    examples/tutorial
    examples/usage
