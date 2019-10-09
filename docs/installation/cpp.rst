C++11 Installation
##################
.. warning::
  If terms such as C++11, CMAKE_, PPA, and linking are unfamiliar to you, consider using the Python3 or MATLAB version of DQ Robotics instead.
.. note:: 
  DQ Robotics is a LGPLV3_ licensed package. Interface packages might have additional licenses.
.. note::
  Had any issues? Report them at the CPP-Issue-Tracker_.

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
The shared objects are installed at /usr/lib and will be found naturally by the linker on Ubuntu. For example, using CMAKE, 

.. code-block:: cmake

  target_link_libraries(my_binary dqrobotics)

Interface packages
==================

.. warning:: 
   We offer support (on a voluntary basis) for the interface packages but no support whatsoever for the third-party software they interface with. For that, refer to their vendors.

Interfaces of DQ Robotics with other libraries are available as separate packages in the PPA, and they can be listed with

.. code-block:: bash
  
  sudo apt-get update
  apt-cache search libdqrobotics*
  
V-REP_ Interface Package
------------------------
.. note:: 
  The V-REP interface package uses BSD-licensed code distributed by CoppeliaRobotics_. Refer to their license for details.

The interface between DQ Robotics and V-REP_ can be installed with

.. code-block:: bash

  sudo apt-get install libdqrobotics-interface-vrep

The following headers will be installed in your system:

.. code-block:: cpp

  #include<dqrobotics/interfaces/vrep/DQ_VrepInterface.h>
  #include<dqrobotics/interfaces/vrep/DQ_VrepRobot.h>
  #include<dqrobotics/interfaces/vrep/robots/LBR4pVrepRobot.h>
  #include<dqrobotics/interfaces/vrep/robots/YouBotVrepRobot.h>

This interface package also requires linking. Using CMAKE_, for example:

.. code-block:: cmake

  target_link_libraries(my_binary dqrobotics dqrobotics-interface-vrep)  

CPLEX_ Interface Package
------------------------

The interface between DQ Robotics and CPLEX_ is header-only and can be installed as follows:

.. code-block:: bash

  sudo apt-get install libdqrobotics-interface-cplex

The following header will be installed in your system

.. code-block:: cpp

  #include<dqrobotics/solvers/DQ_CPLEXSolver.h>

If you are using CPLEX_, you have to install, configure, and link to it according to its documentation. 

Json11_ Interface Package
-------------------------
.. note::
  The Json11 interface package uses MIT-licensed code by Dropbox_. Refer to their license for details.
  
.. warning::
  The Json11 interface package for now has limited functionality and can only import :code:`DQ_SerialManipulator` instances.

The interface between DQ Robotics and Json11_ can be installed with

.. code-block:: bash

  sudo apt-get install libdqrobotics-interface-json11

The following header will be installed in your system:

.. code-block:: cpp

  #include<dqrobotics/interfaces/json11/DQ_JsonReader.h>

This interface package also requires linking. Using CMAKE_, for example:

.. code-block:: cmake

  target_link_libraries(my_binary dqrobotics dqrobotics-interface-json11)  

Using with the Robot Operating System (ROS_)
=========================================

DQ Robotics C++11 and all interface packages install as system-wide packages, so they can be added to your ROS_ code using the CMAKE_ directives shown above.

Building from source in another OS
==================================

.. warning::
   There is no support whatosever for other operating systems besides Ubuntu LTS.

You might be able to build from source as long as you have Eigen3_, CMake_, and a C++11 compatible compiler. 

.. _Stable-PPA: https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/release
.. _V-REP: http://www.coppeliarobotics.com/
.. _Eigen3: http://eigen.tuxfamily.org/index.php?title=Main_Page
.. _CMake: https://cmake.org/
.. _CPLEX: https://www.ibm.com/en-us/products/ilog-cplex-optimization-studio
.. _CPP-Issue-Tracker: https://github.com/dqrobotics/cpp/issues
.. _ROS: https://www.ros.org/
.. _Json11: https://github.com/dropbox/json11
.. _CoppeliaRobotics: https://github.com/CoppeliaRobotics
.. _Dropbox: https://github.com/dropbox/json11
.. _LGPLV3: https://choosealicense.com/licenses/lgpl-3.0/
