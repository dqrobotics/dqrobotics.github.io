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

DQ Robotics is a standalone open-source ([LGPLv3](https://www.gnu.org/licenses/lgpl-3.0.html)) library for robot modelling and control. It provides [dual quaternion](http://en.wikipedia.org/wiki/Dual_quaternion) algebra and kinematic calculation algorithms in MATLAB and C++.

## Installation

### Ubuntu/C++ [![Build Status](https://travis-ci.com/dqrobotics/cpp.svg?branch=master)](https://travis-ci.com/dqrobotics/cpp)

The official support is for Ubuntu 16.04/18.04 LTS using our [Stable PPA](https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/release).

```bash
sudo add-apt-repository ppa:dqrobotics-dev/release
sudo apt-get update
sudo apt-get install libdqrobotics
```

All library updates will be delivered together with your regular Ubuntu updates.

#### Including and linking the library in your C++ projects

After installing the library through the PPA, the relevant headers are

```cpp
#include <dqrobotics/DQ.h>
#include <dqrobotics/DQ_kinematics.h>
```

Linking can be done using -ldqrobotics. For example, using CMAKE, 

```makefile
target_link_libraries(my_binary -ldqrobotics)
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

### MATLAB

In order to use DQ Robotics on your MATLAB installation, and supposing you did the checkout at **[PATH_TO_DQ_ROBOTICS_FOLDER]**, just add

```bash
[PATH_TO_DQ_ROBOTICS_FOLDER]/matlab/
```

and subfolders to your MATLAB path.

Type `help DQ` or `doc DQ`  to see the embedded documentation and all available functions.

### Ubuntu/Python [![Build Status](https://travis-ci.com/dqrobotics/python.svg?branch=master)](https://travis-ci.com/dqrobotics/python) [![PyPI version](https://badge.fury.io/py/dqrobotics.svg)](https://badge.fury.io/py/dqrobotics)

We offer Python bindings for Ubuntu 16.04/18.04 LTS to the C++ library in order to ensure high performance and facilitate the development-to-production cycle. In order to use DQ Robotics Python 3, open a terminal and type 

```bash
python3 -m pip install --user dqrobotics
```

You can get updates with

```bash
python3 -m pip install --user dqrobotics --upgrade
```

**Remarks**
1. The Python package is still experimental. It is not recommended for production yet.
2. Python 2 [will retire soon](https://pythonclock.org/). We only support Python 3.





