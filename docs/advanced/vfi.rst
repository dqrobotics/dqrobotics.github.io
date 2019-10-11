Vector-field inequalities
########################

.. note::
   This section is based on the results presented in :cite:`Marinho2019` and uses its notation.
   
Distance Jacobians
==================

.. note::
   All the distance Jacobians were implemented as :code:`static` methods of the class :code:`DQ_Kinematics`.

To have access to these methods, use

.. code:: cpp

   #include<dqrobotics/robot_modeling/DQ_Kinematics>

.. code:: python

   from dqrobotics.robot_modeling import DQ_Kinematics

:math:`\mymatrix J_{\quat t,\quat p}`
------------------------------------
Squared-distance between a point in the manipulator and a point in the workspace.

.. code:: cpp

   MatrixXd result = DQ_Kinematics::point_to_point_distance_jacobian(translation_jacobian, robot_point, workspace_point);
   
.. code:: python

   result = DQ_Kinematics.point_to_point_distance_jacobian(translation_jacobian, robot_point, workspace_point)
   
   
References
==========

.. bibliography:: references.bib
