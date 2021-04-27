Python3 Installation
####################
.. note::
  DQ Robotics Python3 is recommended for most users.
.. note::
  DQ Robotics Python3 is distributed as a LGPLV3_ licensed package. Interface submodules might have additional licenses.
.. note::
  Had any issues? Report them at the Python-Issue-Tracker_.
  
Installation
============
The DQ Robotics Python3 is delivered through PyPI_. On a Ubuntu LTS (Excluding EOL_ versions) system, open a terminal and run:

.. code-block:: bash

  python3 -m pip install --user dqrobotics
  
.. warning:: 
  The installation will fail for any unsupported system, even if that system has pip.

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
  
Using with the Robot Operating System (ROS_)
=========================================

The recommended :code:`pip` installation installs the library for a given user and should be visible to any ROS_ code executed by that user.

Interface with quadprog_
===========================================
.. note::
  The quadprog_ package is a licensed under GPLv2+. Refer to their license for details. The wrapper class :code:`DQ_QuadprogSolver` is licensed under the terms of DQRobotics.

To use the :code:`DQ_QuadprogSolver` (a wrapper of quadprog_), you have to install quadprog_. To do so, open a terminal and run:

.. code-block:: bash

  python3 -m pip install quadprog --user

You can then import :code:`DQ_QuadprogSolver` as follows

.. code-block:: python

  from dqrobotics.solvers import DQ_QuadprogSolver

.. _pybind11: https://github.com/pybind/pybind11
.. _Python-Issue-Tracker: https://github.com/dqrobotics/python/issues
.. _PyPI: https://pypi.org/
.. _ROS: https://www.ros.org/
.. _LGPLV3: https://choosealicense.com/licenses/lgpl-3.0/
.. _EOL: https://endoflife.software/operating-systems/linux/ubuntu
.. _quadprog: https://pypi.org/project/quadprog/
