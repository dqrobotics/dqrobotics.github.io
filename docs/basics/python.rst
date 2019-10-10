Python3 Basics
####################
  
Preliminaries
============
All code in this section expects you to have the followoing import in the beginning of your file

.. code-block:: python

  from dqrobotics import *

Binary Operations
============

Preliminaries
-------------

Suppose you have the dual quaternions

:math:`\dq{h_1}=1+\imi+\imj+\imk+\dual(1 + \imi + \imj + \imk)` 

and 

:math:`h_2=2+2i+2j+2k+\epsilon(2 + 2i + 2j + 2k)`.

They can be declared in DQ Robotics as

.. code-block:: python

  h1 = DQ([1,1,1,1,1,1,1,1])
  h2 = DQ([2,2,2,2,2,2,2,2])

Operations
-------------

1. Sum :math:`h_3 = h_1 + h_2`

.. code-block:: python

  h3 = h1+h2
  
2. Subtraction :math:`h_3 = h_1 - h_2`

.. code-block:: python

  h3 = h1-h2
  
3. Multiplication :math:`h_3 = h_1 * h_2`

.. code-block:: python

  h3 = h1*h2

.. _LGPLV3: https://choosealicense.com/licenses/lgpl-3.0/
