Matlab Installation
####################
.. note::
  DQ Robotics Matlab is adequate if you want to test your ideas fast while having convenient visualization tools, provided you have access to the `Mathworks software <https://www.mathworks.com/>`_.
.. note::
  DQ Robotics Matlab is distributed as a LGPLV3_ licensed package. Matlab, however, is not free software and other third-party toolboxes may also not be free.
.. note::
  Had any issues? Report them at the Matlab-Issue-Tracker_.
  
Installation
============
Assuming that you already have Matlab installed on you computer, download the most recent Matlab toolbox of DQ Robotics `here <https://github.com/dqrobotics/matlab/releases/latest>`_.

After downloading the file dqrobotics-YY-MM.mltbx, where YY-MM stands for the year and month of release, just open it and Matlab should copy the files to the folder ``Toolboxes/dqrobotics-YY-MM`` in your ``$HOME`` folder and appropriately set the Matlab path.

To test if the toolbox was installed correctly, just go to the prompt and type

.. code-block:: matlab

  >> DQ
  ans = 
    0    
  
.. warning:: 
  
If you receive an error instead, it means that the toolbox was not properly installed and you should open an issue `here  <https://github.com/dqrobotics/matlab/issues>`_.


Development branch
==================

Those wanting the results of our latest developments can checkout the master branch of the `Matlab repository  <https://github.com/dqrobotics/matlab>`_. In order to use DQ Robotics on your MATLAB installation, and supposing you did the checkout at **[PATH_TO_DQ_ROBOTICS_FOLDER]**, just add

.. code-block:: matlab

  [PATH_TO_DQ_ROBOTICS_FOLDER]/matlab/

and subfolders to your MATLAB path.

Note however, that the development branch is unstable and should not be used in production environments.

Type ``help DQ`` or ``doc DQ``  to see the embedded documentation and all available functions.


.. _Matlab-Issue-Tracker: https://github.com/dqrobotics/matlab/issues
.. _LGPLV3: https://choosealicense.com/licenses/lgpl-3.0/
.. _Mathworks software: (https://www.mathworks.com/)
