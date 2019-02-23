---
layout: default

---
### …or download it through svn

{% highlight sh %}
svn checkout http://svn.code.sf.net/p/dqrobotics/code/trunk dqrobotics
{% endhighlight %}

<hr />

# What is DQ Robotics?

DQ Robotics is a standalone open-source (LGPLv3) library for robot modelling and control. It provides [dual quaternion](http://en.wikipedia.org/wiki/Dual_quaternion) algebra and kinematic calculation algorithms in MATLAB and C++.

Report any issues you might have with the installation and usage at the [issue tracker](http://sourceforge.net/p/dqrobotics/tickets/)

## Installation

### Ubuntu/C++
The official support is for Ubuntu 16.04/18.04 LTS using our [PPA](https://launchpad.net/~dqrobotics-dev/+archive/ubuntu/release).

{% highlight sh %}
sudo add-apt-repository ppa:dqrobotics-dev/release
sudo apt-get update
sudo apt-get install libdqrobotics
{% endhighlight %}

All library updates will be delivered together with your regular Ubuntu updates.

#### Including and linking the library in your C++ projects
After installing the library through the PPA, the relevant headers are

{% highlight cpp %}
#include <dqrobotics/DQ.h>
#include <dqrobotics/DQ_kinematics.h>
{% endhighlight %}

Linking can be done using -ldqrobotics. For example, using CMAKE, 
{% highlight cmake %}
target_link_libraries(my_binary -ldqrobotics)
{% endhighlight %}

### MATLAB
In order to use DQ Robotics on your MATLAB installation, and supposing you did the checkout at **[PATH_TO_DQ_ROBOTICS_FOLDER]**, just add

{% highlight sh %}
[PATH_TO_DQ_ROBOTICS_FOLDER]/matlab/dq_robotics
{% endhighlight %}

and subfolders to your MATLAB path.

## Building from source in your favorite OS

There is no official support for other operating systems besides Ubuntu.

However, you should be able to build from source as long as you have [Eigen3](http://eigen.tuxfamily.org/index.php?title=Main_Page) and [CMake](https://cmake.org/).