---
layout: default

---
<hr />

# What is DQ Robotics?

DQ Robotics is a standalone open-source ([LGPLv3](https://www.gnu.org/licenses/lgpl-3.0.html)) library for robot modelling and control. It provides [dual quaternion](http://en.wikipedia.org/wiki/Dual_quaternion) algebra and kinematic calculation algorithms in Python3, Matlab, and C++11.
- Most users will benefit from using the [Python3](#ubuntu-python3--) version at first. It is easy and computationally efficient (C++ code runs under the hood for fast performance).
- Use the [MATLAB](#matlab) version if you want to test your ideas fast while having convenient visualization tools, provided you have access to the [MathWorks software](https://www.mathworks.com/).
- Use the [C++11 version](#ubuntu-c11-) for real-time high-performance applications and if you're not afraid of [pointers](https://en.wikipedia.org/wiki/Pointer_(computer_programming)).

<hr />

# How to cite

If you use DQ Robotics in your research, please cite the [DQ Robotics introductory paper](https://arxiv.org/abs/1910.11612).

```
@article{Adorno-Marinho2020,
archivePrefix = {arXiv},
arxivId = {1910.11612},
author = {Adorno, Bruno Vilhena and  Marinho, Murilo Marques},
doi = {10.1109/MRA.2020.2997920},
eprint = {1910.11612},
issn = {1070-9932},
journal = {IEEE Robotics {\&} Automation Magazine},
pages = {1--15},
title = {{DQ} Robotics: A Library for Robot Modeling and Control},
url = {https://ieeexplore.ieee.org/document/9136790/},
year = {2020}
}

```

<hr />

# Installation [![Documentation Status](https://readthedocs.org/projects/dqroboticsgithubio/badge/?version=latest)](https://dqroboticsgithubio.readthedocs.io/en/latest/?badge=latest)

## Python3 [![Build Status](https://travis-ci.com/dqrobotics/python.svg?branch=master)](https://travis-ci.com/dqrobotics/python) [![PyPI version](https://badge.fury.io/py/dqrobotics.svg)](https://badge.fury.io/py/dqrobotics) [![Appveyor Build Status](https://ci.appveyor.com/api/projects/status/github/dqrobotics/python?branch=master&svg=true)](https://ci.appveyor.com/project/mmmarinho/python)

*Official support*: Python >=3.5 in Ubuntu 16.04/18.04/20.04 LTS

To install DQ Robotics Python3, open a terminal and type 

```bash
python3 -m pip install --user dqrobotics
```
More details at the [docs](https://dqroboticsgithubio.readthedocs.io/en/latest/installation/python.html#python3-installation).

Notes:
1. No support, but package available: Python 3.7 in MacOSX 10.13.
2. No support, but package available: Python >=3.5 in Windows 10.
3. No support for conda installations, but you might be able to install the wheel file.

## MATLAB

Assuming that you already have Matlab installed on you computer, download the most recent Matlab toolbox of DQ Robotics [here](https://github.com/dqrobotics/matlab/releases/latest).

After downloading the file dqrobotics-YY-MM.mltbx, where YY-MM stands for the year and month of release, just open it and Matlab should copy the files to the folder `Toolboxes/dqrobotics-YY-MM` in your `$HOME` folder and appropriately set the Matlab path.

More details at the [docs](https://dqroboticsgithubio.readthedocs.io/en/latest/installation/matlab.html#matlab-installation).

## C++11 [![Build Status](https://travis-ci.com/dqrobotics/cpp.svg?branch=master)](https://travis-ci.com/dqrobotics/cpp)

The official support is for Ubuntu 16.04/18.04/20.04 LTS using our [Stable PPA](https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/release).

```bash
sudo add-apt-repository ppa:dqrobotics-dev/release
sudo apt-get update
sudo apt-get install libdqrobotics
```

All library updates will be delivered together with your regular Ubuntu updates.

More details at the [docs](https://dqroboticsgithubio.readthedocs.io/en/latest/installation/cpp.html#c-11-installation).

# Remarks
1. The DQ Robotics software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfrigement.
2. Refer to the issue tracker of each programming language if you need support. Support is given in a voluntary basis.





