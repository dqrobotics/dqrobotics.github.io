Vector-field inequalities
########################
.. note:: 
  For brevity, the code is shown using Python3. The other versions of the library also have the same methods.

.. note::
  This section is based on the results presented in :cite:`Marinho2019`.
   
Distance Jacobians
==================

.. note::
   All the distance Jacobians were implemented as :code:`static` methods of the class :code:`DQ_Kinematics`.

To have access to these methods, use

.. code:: python

   from dqrobotics.robot_modeling import DQ_Kinematics

As an usage example, suppose that we are using the :code:`KukaYoubot` robot

.. code:: python

   import numpy as np
   from math import pi
   from dqrobotics import *
   from dqrobotics.robot_modeling import DQ_Kinematics
   from dqrobotics.robots import KukaYoubotRobot

   # Get robot kinematics
   robot = KukaYoubotRobot.kinematics()
   
   # Define an arbirary posture
   q = np.array([0, 0, 0, 0, pi/2.0, pi/2.0, 0, 0]) # Arbitrary value
   
   # The pose of the robot can be used to retrieve robot primitives
   pose = robot.fkm(q)
   robot_point = translation(pose)
   
   # These Jacobians are used to calculate the distance Jacobians
   pose_jacobian = robot.pose_jacobian(q)
   translation_jacobian = DQ_Kinematics.translation_jacobian(pose_jacobian, pose)  
   
   # Workspace primitives are calculated with dual-quaternion algebra
   workspace_point = 0.5*i_ + 0.2*j_


Robot-point to point distance Jacobian, :math:`\mymatrix J_{\quat t,\quat p}`
------------------------------------
.. note:: 
   Mathematically defined in Eq. (22) of :cite:`Marinho2019`.

The Jacobian relating the joint velocities with the derivative of the squared-distance between a point in the manipulator and a point in the workspace.

.. code:: python

   result = DQ_Kinematics.point_to_point_distance_jacobian(translation_jacobian, robot_point, workspace_point)

   
References
==========

.. bibliography:: references.bib
