Vector-field inequalities
########################

.. note::
   This section is based on the results presented in :cite:`Marinho2019` and uses its notation.
   
Distance Jacobians
==================

.. note::
   All the distance Jacobians were implemented as :code:`static` methods of the class :code:`DQ_Kinematics`.

To have access to these methods, use

.. code:: python

   # Python
   from dqrobotics.robot_modeling import DQ_Kinematics

.. code:: cpp

   //C++
   #include<dqrobotics/robot_modeling/DQ_Kinematics>


Robot-point to point distance Jacobian, :math:`\mymatrix J_{\quat t,\quat p}`
------------------------------------
.. note:: 
   Mathematically defined in Eq. (22) of :cite:`Marinho2019`.

The Jacobian relating the joint velocities with the derivative of the squared-distance between a point in the manipulator and a point in the workspace.

.. code:: python

   # Python
   result = DQ_Kinematics.point_to_point_distance_jacobian(translation_jacobian, robot_point, workspace_point)

.. code:: cpp

   //C++
   MatrixXd result = DQ_Kinematics::point_to_point_distance_jacobian(translation_jacobian, robot_point, workspace_point);
   
   
References
==========

.. bibliography:: references.bib
