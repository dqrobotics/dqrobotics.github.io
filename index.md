---
layout: default

---
###…or download it through svn

{% highlight sh %}
svn checkout http://svn.code.sf.net/p/dqrobotics/code/trunk dqrobotics
{% endhighlight %}

<hr />

#What is DQ Robotics?

DQ Robotics is a stand alone open-source Robotics library. It provides [dual quaternion]("http://en.wikipedia.org/wiki/Dual_quaternion") algebra, kinematic calculation algorithms in MATLAB and C++ that can be applied in robot control. The library has a catkin package wrapper for use in [ROS Indigo](http://wiki.ros.org/indigo/Installation/Ubuntu), and also provides a [V-REP](http://www.coppeliarobotics.com/") interface.

Report any issues you might have with the installation and usage at the [issue tracker](http://sourceforge.net/p/dqrobotics/tickets/)

<!--There are several published research papers that used DQ robotics: [[1]](http://www.sbai2013.ufc.br/pdfs/7359.pdf), [[2]](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?reload=true&arnumber=6913799), -->
<hr />

##Installation

###MATLAB
In order to use DQ Robotics on your MATLAB installation, and supposing you did the checkout at **[PATH_TO_DQ_ROBOTICS_FOLDER]**, just add

{% highlight sh %}
[PATH_TO_DQ_ROBOTICS_FOLDER]/ROS/dq_robotics
{% endhighlight %}

and subfolders to your MATLAB path.

The library is stand alone, but some examples use the [Robotics Toolbox](http://www.petercorke.com/Robotics_Toolbox.html">Robotics Toolbox)

###C++
The official support is for Ubuntu only. However, it should work out-of-the-box in any system in which you can install [Eigen3](http://eigen.tuxfamily.org/index.php?title=Main_Page).

First install Eigen3 and create a symbolic link of Eigen3 in your user include folder:

{% highlight sh %}
sudo apt-get install libeigen3-dev
sudo ln -s /usr/include/eigen3/Eigen/ /usr/local/include/
{% endhighlight %}

Compile the examples by doing:

{% highlight sh %}
cd [PATH_TO_DQ_ROBOTICS_FOLDER]/C++/examples
make all
{% endhighlight %}

If there are no errors, you’re set to use the files in your own projects! You can also create your own files in the example folder and add them to the MAKEFILE for compilation.

###ROS

There is a catkin ROS package available in the distribution. The latest build has been tested with [ROS Indigo](http://wiki.ros.org/indigo/Installation/Ubuntu) and [Ubuntu 14.04 LTS](http://www.ubuntu.com/download/desktop).

In order to use it, copy the catkin package

{% highlight sh %}
[PATH_TO_DQ_ROBOTICS_FOLDER]/dq_robotics/ROS/dq_robotics
{% endhighlight %}

to your catkin workspace. If you installed Eigen3 as described in the last step, it should compile without problems.

There’s an example catkin package that uses the dq_robotics catkin package

{% highlight sh %}
[PATH_TO_DQ_ROBOTICS_FOLDER]/dq_robotics/ROS/dq_robotics_example
{% endhighlight %}

Use it as a reference when creating packages that depend on dq_robotics.

