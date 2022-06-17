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

Interface modules
==================

.. warning:: 
   We offer support (on a voluntary basis) for the interface modules but no support whatsoever for the third-party software they interface with. For that, refer to their vendors.
   
Interface modules for DQRobotics Python3 are installed together with the core module.


Interface with CoppeliaSim_ (Formely V-REP)
===========================================
.. note:: 
  The V-REP interface (also compatible with CoppeliaSim) module uses BSD-licensed code distributed by CoppeliaRobotics_. Refer to their license for details.

You do not need to do anything specific to make DQRobotics work with CoppeliaSim. It should work with the default configurations of CoppeliaSim. If it doe s not work out-of-the-box, be sure that the connection port is correctly configured (refer to CoppeliaSimRemoteAPI_). The standard way is to have port :code:`19997` configured in your :code:`remoteApiConnections.txt`. 

.. warning:: 
  Known issue: For MacOS users, CoppeliaSim's default remote API port :code:`19997` does not seem to open correctly on application startup. This is a CoppeliaSim side issue, not with DQRobotics. One way to open it is to (1) add the following to the main script of the scene :code:`simRemoteApi.start(19997)` and (2) start the simulation. After that, the `DQ_VrepInterface` can be used normally.

The minimal example below will obtain the pose of the `Floor` on the default scene in CoppeliaSim.

.. code-block:: python

  from dqrobotics import *
  from dqrobotics.interfaces.vrep import DQ_VrepInterface

  remote_api_port = 19997 # This port needs to be configured correctly in your CoppeliaSim!

  vi = DQ_VrepInterface()
  try:
      if not vi.connect(19997, 100, 10):
          raise RuntimeError("Unable to connect to CoppeliaSim, be sure CoppeliaSim is opened in the default scene "
                             "and that port {} is correctly opened.".format(remote_api_port))

      x_floor = vi.get_object_pose("Floor")
      print("The pose of the floor is {}".format(x_floor))
      print("The translation of the floor is {}".format(translation(x_floor)))
      print("The rotation of the floor is {}".format(rotation(x_floor)))

  except KeyboardInterrupt:
      print("Interrupted by user, finishing cleanly.")
  except Exception as e:
      print("Exception caught: {}, finishing cleanly.".format(e))
  finally:
      vi.disconnect()
      
The result will be 

.. code-block:: bash

  The pose of the floor is 1 + E*( - 0.05k)
  The translation of the floor is  - 0.1k
  The rotation of the floor is 1


Interface with quadprog_
===========================================
.. note::
  The quadprog_ package is licensed under GPLv2+. Refer to their license for details. The wrapper class :code:`DQ_QuadprogSolver` is licensed under the terms of DQRobotics.

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
.. _CoppeliaSim: https://www.coppeliarobotics.com
.. _CoppeliaRobotics: https://github.com/CoppeliaRobotics
.. _CoppeliaSimRemoteAPI: https://www.coppeliarobotics.com/helpFiles/en/remoteApiServerSide.htm
.. _quadprog: https://pypi.org/project/quadprog/
