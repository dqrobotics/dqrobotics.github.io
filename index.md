---
layout: default

---

### …or clone the repos

```bash
git clone https://github.com/dqrobotics/matlab.git
git clone https://github.com/dqrobotics/cpp.git
git clone https://github.com/dqrobotics/python.git
```

<hr />

# What is DQ Robotics?

DQ Robotics is a standalone open-source ([LGPLv3](https://www.gnu.org/licenses/lgpl-3.0.html)) library for robot modelling and control. It provides [dual quaternion](http://en.wikipedia.org/wiki/Dual_quaternion) algebra and kinematic calculation algorithms in Python3, Matlab, and C++.
- Most users will benefit most from using the Python3 version at first.
- Use the [MATLAB](https://www.mathworks.com/) version of you have access to the MathWorks software.
- Use the C++ version for real-time high-performance applications.

## Installation

### Ubuntu/Python [![Build Status](https://travis-ci.com/dqrobotics/python.svg?branch=master)](https://travis-ci.com/dqrobotics/python) [![PyPI version](https://badge.fury.io/py/dqrobotics.svg)](https://badge.fury.io/py/dqrobotics)
(Python 2 [will retire soon](https://pythonclock.org/). We only support Python 3.)

We offer Python bindings for Ubuntu 16.04/18.04 LTS to the C++ library in order to ensure high performance and facilitate the development-to-production cycle. In order to use DQ Robotics Python 3, open a terminal and type 

```bash
python3 -m pip install --user dqrobotics
```

You can get updates with

```bash
python3 -m pip install --user dqrobotics --upgrade
```
### MATLAB

In order to use DQ Robotics on your MATLAB installation, and supposing you did the checkout at **[PATH_TO_DQ_ROBOTICS_FOLDER]**, just add

```bash
[PATH_TO_DQ_ROBOTICS_FOLDER]/matlab/
```

and subfolders to your MATLAB path.

Type `help DQ` or `doc DQ`  to see the embedded documentation and all available functions.

### Ubuntu/C++ [![Build Status](https://travis-ci.com/dqrobotics/cpp.svg?branch=master)](https://travis-ci.com/dqrobotics/cpp)

The official support is for Ubuntu 16.04/18.04 LTS using our [Stable PPA](https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/release).

```bash
sudo add-apt-repository ppa:dqrobotics-dev/release
sudo apt-get update
sudo apt-get install libdqrobotics
```

All library updates will be delivered together with your regular Ubuntu updates.

#### Interface packages

Interfaces of DQ Robotics with other libraries are available as separate packages in the PPA, and they can be listed with

```bash
sudo apt-get update
apt-cache search libdqrobotics*
```
For instance, the interface between DQ Robotics and [V-REP](http://www.coppeliarobotics.com/) can be downloaded with
```bash
sudo apt-get install libdqrobotics-interface-vrep
```
and the interface between DQ Robotics and [CPLEX](https://www.ibm.com/jp-ja/products/ilog-cplex-optimization-studio) with
```bash
sudo apt-get install libdqrobotics-interface-cplex
```
Each package might require extra configuration and for that refer to their individual Github pages.

#### Including and linking the library in your C++ projects

After installing the library through the PPA, you will have access to the headers:

```cpp
#include <dqrobotics/DQ.h>
#include <dqrobotics/robot_modeling/DQ_kinematics.h>
#include <dqrobotics/robot_modeling/DQ_SerialManipulator.h>
#include <dqrobotics/utils/DQ_Geometry.h>
...
```

Linking can be done using -ldqrobotics. For example, using CMAKE, 

```makefile
target_link_libraries(my_binary -ldqrobotics)
```
Interface packages might also require linking. For instance, the V-REP interface requires:
```makefile
target_link_libraries(my_binary -ldqrobotics -ldqrobotics-interface-vrep)
```

#### Daily builds PPA

Daily builds of the most recent version of the library are available at our [Development PPA](https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/development).

```bash
sudo add-apt-repository ppa:dqrobotics-dev/development
sudo apt-get update
sudo apt-get install libdqrobotics
```

#### Building C++ from source in your favorite OS

There is no official C++ support for other operating systems besides Ubuntu.

However, you should be able to build from source as long as you have [Eigen3](http://eigen.tuxfamily.org/index.php?title=Main_Page) and [CMake](https://cmake.org/).

# Remarks
1. The DQ Robotics software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfrigement.
2. Refer to the issue tracker of each programming language if you need support. Support is given in a voluntary basis.





