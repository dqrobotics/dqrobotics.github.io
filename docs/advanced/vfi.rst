Vector-field inequalities
##########################

.. note::
  This section is based on the results presented in :cite:`Marinho2019`.

.. warning:: 
  For brevity, the code is shown using Python3. The other versions of the library also have the same methods.

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
   # The end effector translation (Could be another point)
   robot_point = translation(pose)
   # Line is the z-axis of the end-effector (Could be another line)
   robot_line = Ad(rotation(pose), k_) + E_ * cross(translation(pose), Ad(rotation(pose), k_))
   # Plane is normal to the z-axis of the end-effector (Could be another plane)
   robot_plane = Ad(rotation(pose), k_) + E_ * dot(translation(pose), Ad(rotation(pose), k_))
   
   # These Jacobians are used to calculate the distance Jacobians
   pose_jacobian = robot.pose_jacobian(q)
   translation_jacobian = DQ_Kinematics.translation_jacobian(pose_jacobian, pose) 
   line_jacobian = DQ_Kinematics.line_jacobian(pose_jacobian, pose, k_)
   plane_jacobian = DQ_Kinematics.plane_jacobian(pose_jacobian, pose, k_)
   
   # Workspace primitives are calculated with dual-quaternion algebra
   workspace_point = 0.5*i_ + 0.2*j_ # A point in (0.5, 0.2, 0.0) in world-coordinates
   workspace_line = i_ # The x-axis in world-coordinates
   workspace_plane = k_ # Normal to the z-axis in world-coodinates (the x-y plane)


Robot-point to point distance Jacobian, :math:`\mymatrix J_{\quat t,\quat p}`
-----------------------------------------------------------------------------
.. note:: 
   Mathematically defined in Eq. (22) of :cite:`Marinho2019`.

The Jacobian relating the joint velocities with the derivative of the squared-distance between a point in the manipulator and a point in the workspace.

.. code:: python

   result = DQ_Kinematics.point_to_point_distance_jacobian(translation_jacobian, robot_point, workspace_point)

Robot-point to line distance Jacobian, :math:`\mymatrix J_{\quat t,\quat l}`
----------------------------------------------------------------------------
.. note:: 
   Mathematically defined in Eq. (32) of :cite:`Marinho2019`.

The Jacobian relating the joint velocities with the derivative of the squared-distance between a point in the manipulator and a line in the workspace.

.. code:: python

   result = DQ_Kinematics.point_to_line_distance_jacobian(translation_jacobian, robot_point, workspace_line)


Robot-line to point distance Jacobian, :math:`\mymatrix J_{\quat l,\quat p}`
----------------------------------------------------------------------------
.. note:: 
   This method provides a generalized version of Eq. (34) of :cite:`Marinho2019` to any line in the manipulator.

The Jacobian relating the joint velocities with the derivative of the squared-distance between a line in the manipulator and a point in the workspace.

.. code:: python

   result = DQ_Kinematics.line_to_point_distance_jacobian(line_jacobian, robot_line, workspace_point)


Robot-line to line distance Jacobian, :math:`\mymatrix J_{\quat l,\quat l}`
---------------------------------------------------------------------------
.. note:: 
   This method provides a generalized version of Eq. (48) of :cite:`Marinho2019` to any line in the manipulator.

The Jacobian relating the joint velocities with the derivative of the squared-distance between a line in the manipulator and a line in the workspace.

.. code:: python

   result = DQ_Kinematics.line_to_line_distance_jacobian(line_jacobian, robot_line, workspace_line)
   
   
Robot-plane to point distance Jacobian, :math:`\mymatrix J_{\quat \pi,\quat l}`
-------------------------------------------------------------------------------
.. note:: 
   This method provides a generalized version of Eq. (56) of :cite:`Marinho2019` to any plane in the manipulator.

The Jacobian relating the joint velocities with the derivative of the distance between a plane in the manipulator and a point in the workspace.

.. code:: python

   result = DQ_Kinematics.plane_to_point_distance_jacobian(plane_jacobian, workspace_point)
   
   
Robot-point to plane distance Jacobian, :math:`\mymatrix J_{\quat p,\quat \pi}`
-------------------------------------------------------------------------------
.. note:: 
   Mathematically defined in Eq. (59) of :cite:`Marinho2019`.

The Jacobian relating the joint velocities with the derivative of the distance between a point in the manipulator and a plane in the workspace.

.. code:: python

   result = DQ_Kinematics.point_to_plane_distance_jacobian(translation_jacobian, robot_point, workspace_plane)
