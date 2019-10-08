Python3 Installation
####################

On a compatible system, open a terminal and run:

.. code-block:: bash

  python3 -m pip install --user dqrobotics
  
Updates
=======

You can get updates with

.. code-block:: bash
  
  python3 -m pip install --user dqrobotics --upgrade
  
Usage
=====

After installation, you can import and use the library in your code

.. code-block:: python

  from dqrobotics import *
  a = DQ(1,2,3,4,5,6,7,8)
  print(a)

The DQ Robotics Python3 is made of Python bindings pybind11_ to the C++11 version of the library. It provides decent performance and facilitates the development-to-production cycle. 

.. _pybind11: https://github.com/pybind/pybind11
