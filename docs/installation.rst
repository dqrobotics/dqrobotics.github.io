############
Installation
############

*******************
DQ Robotics Python3
*******************
On a compatible system, open a terminal and run:

.. code-block:: bash

  python3 -m pip install --user dqrobotics

You can get updates with

.. code-block:: bash
  
  python3 -m pip install --user dqrobotics --upgrade

After installation, you can import and use the library in your code

.. code-block:: python

  from dqrobotics import *
  a = DQ(1,2,3,4,5,6,7,8)
  print(a)

The DQ Robotics Python3 is made of Python bindings pybind11 (https://github.com/pybind/pybind11) to the C++11 version of the library. It provides decent performance and facilitates the development-to-production cycle. 

**************
DQ Robotics C++11
**************

The official support is for Ubuntu 16.04/18.04 LTS using our Stable PPA (https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/release).

.. code-block:: bash
  
  sudo add-apt-repository ppa:dqrobotics-dev/release
  sudo apt-get update
  sudo apt-get install libdqrobotics

All library updates will be delivered together with your regular Ubuntu updates.

Interface packages for C++11
============================

Interfaces of DQ Robotics with other libraries are available as separate packages in the PPA, and they can be listed with

.. code-block:: bash
  
  sudo apt-get update
  apt-cache search libdqrobotics*

For instance, the interface between DQ Robotics and [V-REP](http://www.coppeliarobotics.com/) can be downloaded with

.. code-block:: bash
  sudo apt-get install libdqrobotics-interface-vrep

and the interface between DQ Robotics and [CPLEX](https://www.ibm.com/jp-ja/products/ilog-cplex-optimization-studio) with

.. code-block:: bash
  sudo apt-get install libdqrobotics-interface-cplex

Each package might require extra configuration and for that refer to their individual Github pages.

Including and linking the library in your C++11 projects
=========================================================

After installing the library through the PPA, you will have access to the headers:

.. code-block:: cpp

  #include <dqrobotics/DQ.h>
  #include <dqrobotics/robot_modeling/DQ_kinematics.h>
  #include <dqrobotics/robot_modeling/DQ_SerialManipulator.h>
  #include <dqrobotics/utils/DQ_Geometry.h>
  
Linking can be done using -ldqrobotics. For example, using CMAKE, 

.. code-block:: makefile
  target_link_libraries(my_binary -ldqrobotics)

Interface packages might also require linking. For instance, the V-REP interface requires:

.. code-block:: makefile
  target_link_libraries(my_binary -ldqrobotics -ldqrobotics-interface-vrep)

Building C++ from source in your favorite OS
=============================================

There is no official C++ support for other operating systems besides Ubuntu.

However, you should be able to build from source as long as you have Eigen3 (http://eigen.tuxfamily.org/index.php?title=Main_Page), CMake (https://cmake.org/), and a C++11 compatible compiler. 
