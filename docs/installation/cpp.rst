C++11 Installation
##################

Release PPA
==================

The official support is for Ubuntu 16.04/18.04 LTS using our Stable-PPA_.

.. code-block:: bash
  
  sudo add-apt-repository ppa:dqrobotics-dev/release
  sudo apt-get update
  sudo apt-get install libdqrobotics

All library updates will be delivered together with your regular Ubuntu updates.

Including
=========
.. note::
  After installation, the DQ Robotics headers can be included without any extra configuration.

You can list up the installed headers with

.. code-block:: bash

  find /usr/include/dqrobotics
  
The headers can be added to your code in the following way

.. code-block:: cpp

  #include <dqrobotics/DQ.h>
  #include <dqrobotics/robot_modeling/DQ_Kinematics.h>
  #include <dqrobotics/robot_modeling/DQ_SerialManipulator.h>
  #include <dqrobotics/utils/DQ_Geometry.h>
  //Any other headers
  
Linking
=======
.. note::
  After installation, the DQ Robotics shared objects can be linked without any extra configuration.

For example, using CMAKE, 

.. code-block:: cmake

  target_link_libraries(my_binary dqrobotics)

Interface packages might also require linking. For instance, the V-REP interface requires:

.. code-block:: cmake

  target_link_libraries(my_binary dqrobotics dqrobotics-interface-vrep)  
  
Interface packages
==================

Interfaces of DQ Robotics with other libraries are available as separate packages in the PPA, and they can be listed with

.. code-block:: bash
  
  sudo apt-get update
  apt-cache search libdqrobotics*

For instance, the interface between DQ Robotics and V-REP_ can be downloaded with

.. code-block:: bash
  sudo apt-get install libdqrobotics-interface-vrep

and the interface between DQ Robotics and `CPLEX <https://www.ibm.com/jp-ja/products/ilog-cplex-optimization-studio>`_.

.. code-block:: bash
  sudo apt-get install libdqrobotics-interface-cplex

Each package might require extra configuration and for that refer to their individual Github pages.

Building from source in another OS
==================================

.. warning::
   There is no support for other operating systems besides Ubuntu LTS.

However, you might be able to build from source as long as you have Eigen3_, CMake_, and a C++11 compatible compiler. 

.. _Stable-PPA: https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/release
.. _V-REP: http://www.coppeliarobotics.com/
.. _Eigen3: http://eigen.tuxfamily.org/index.php?title=Main_Page
.. _CMake: https://cmake.org/
