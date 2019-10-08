C++11 Installation
##################

Release PPA
==================

The official support is for Ubuntu 16.04/18.04 LTS using our Stable PPA (https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/release).

.. code-block:: bash
  
  sudo add-apt-repository ppa:dqrobotics-dev/release
  sudo apt-get update
  sudo apt-get install libdqrobotics

All library updates will be delivered together with your regular Ubuntu updates.

Interface packages
==================

Interfaces of DQ Robotics with other libraries are available as separate packages in the PPA, and they can be listed with

.. code-block:: bash
  
  sudo apt-get update
  apt-cache search libdqrobotics*

For instance, the interface between DQ Robotics and [V-REP](http://www.coppeliarobotics.com/) can be downloaded with

.. code-block:: bash
  sudo apt-get install libdqrobotics-interface-vrep

and the interface between DQ Robotics and `CPLEX <https://www.ibm.com/jp-ja/products/ilog-cplex-optimization-studio>`_.

.. code-block:: bash
  sudo apt-get install libdqrobotics-interface-cplex

Each package might require extra configuration and for that refer to their individual Github pages.

Including and linking
==================
After installing the library through the PPA, you will have access to the headers:

.. code-block:: cpp

  #include <dqrobotics/DQ.h>
  #include <dqrobotics/robot_modeling/DQ_Kinematics.h>
  #include <dqrobotics/robot_modeling/DQ_SerialManipulator.h>
  #include <dqrobotics/utils/DQ_Geometry.h>
  
Linking can be done using -ldqrobotics. For example, using CMAKE, 

.. code-block:: cmake

  target_link_libraries(my_binary dqrobotics)

Interface packages might also require linking. For instance, the V-REP interface requires:

.. code-block:: cmake

  target_link_libraries(my_binary dqrobotics dqrobotics-interface-vrep)

Building from source in another OS
==================

There is no official C++ support for other operating systems besides Ubuntu.

However, you should be able to build from source as long as you have Eigen3 (http://eigen.tuxfamily.org/index.php?title=Main_Page), CMake (https://cmake.org/), and a C++11 compatible compiler. 
