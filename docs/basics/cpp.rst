C++11 Basics
####################
  
Preliminaries
============
All code in this section expects you to have the followoing import in the beginning of your file

.. code-block:: cpp

  #include<dqrobotics/DQ.h>
  
  using namespace DQ_robotics;

Binary Operations
============

Preliminaries
-------------

Suppose you have the dual quaternions

:math:`\dq{h_1}=1+\imi+\imj+\imk+\dual(1 + \imi + \imj + \imk)` 

and 

:math:`\dq{h_2}=2+2\imi+2\imj+2\imk+\dual(2 + 2\imi + 2\imj + 2\imk)`.

They can be declared in DQ Robotics as

.. code-block:: python

  DQ h1(1,1,1,1,1,1,1,1)
  DQ h2(2,2,2,2,2,2,2,2)

Operations
-------------

1. Sum :math:`\dq{h_3} = \dq{h_1} + \dq{h_2}`

.. code-block:: python

  DQ h3 = h1+h2
  
2. Subtraction :math:`\dq{h_3} = \dq{h_1} - \dq{h_2}`

.. code-block:: python

  DQ h3 = h1-h2
  
3. Multiplication :math:`\dq{h_3} = \dq{h_1}\dq{h_2}`

.. code-block:: python

  DQ h3 = h1*h2

.. _LGPLV3: https://choosealicense.com/licenses/lgpl-3.0/
