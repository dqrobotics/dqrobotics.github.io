Python3 Installation
####################
.. note::
  DQ Robotics Python3 is recommended for most users.
  
Installation
============
The DQ Robotics Python3 is delivered through PyPI_. On a Ubuntu 16.04/18.04 LTS system, open a terminal and run:

.. code-block:: bash

  python3 -m pip install --user dqrobotics
  
.. note::
  Had any issues? Report them at the Python-Issue-Tracker_.
 
.. warning:: 
  The installation will fail for any unsupported system.

Updates
=======

You can get updates with

.. code-block:: bash
  
  python3 -m pip install --user dqrobotics --upgrade
  
Import
======

All the code is under the :code:`dqrobotics` module.

.. code-block:: python

  from dqrobotics import *
  a = DQ(1,2,3,4,5,6,7,8)
  print(a)

.. _pybind11: https://github.com/pybind/pybind11
.. _Python-Issue-Tracker: https://github.com/dqrobotics/python/issues
.. _PyPI: https://pypi.org/
