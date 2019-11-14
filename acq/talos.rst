
Talos Artica Operation
======================
 

Launch Scipion Session
----------------------
Before you start your microscope session you need to :ref:`start the scipion session <session-setup>`.

Vacuum and Temperature
-----------------------

Check that the column & autoloader vacuum and temperature is good.  Typical values for the vacuum are log 1 for the column, log 15-30 for the autoloader; the autoloader temperature should be below -180C.

.. image:: /images/talos/vacuum.PNG
.. image:: /images/talos/temperature_control.PNG


Cassette Loading and Inventory
------------------------------
 

Once the microscope is cold, you can :ref:`load the cassette <loading-loading-autoloader>`. After the cassette is loaded, run an inventory from the Autoloader tab, make sure that all the positions that you loaded are properly detected. Occupied positions are shown in blue, empty ones in grey.

.. image:: /images/talos/autoloader.PNG


Start EPU
---------

In case EPU is not open yet, start EPU via the Start menu. If the column valves are closed ignore the message. The window will be hiding behind the user interface software. Drag it to the second screen, minimise and maximise it again. 


.. note::

    If SerialEM is open, SerialEM must be closed before opening EPU.
    

.. note::

    TIA needs to be started for EPU to open and run. In case TIA is not open yet, start TIA via the Start menu.


Load EPU Settings
-----------------

In EPU, click on the Preparation tab, Acquisition and Optics settings. Here all the microscope conditions can be inputted to the software for the Atlas, Grid-square, Hole/Eucentric height, Data acquisition, Autofocus and Drift measurement.

To make it simple, we have predefined the most common EPU settings, which you can Import via the import tab:
 1. Navigate to computer/staging/fac/settings/EPU/general
 2. Choose the relevant file and press open
 3. Save the file in your own directory and modify if needed.
 
.. warning::

    Please take care to not overwrite the faciltity EPU settings files!
    

.. image:: /images/talos/import.PNG


Open Column Valves
-------------------

 1. Load the atlas presets.
 2. Open the column valves. You can check the valve, screen or blanking state at the top left corner of the flu-cam viewer. 
 3. Now insert the flu-screen. You can either press R1 or Press 'Insert Screen' from the FluCam Menu. 
 4. In case the beam is blanked, unblank the beam (press L3). Now there should be no more green messages at the top left corner of the flu-cam viewer.

.. image:: /images/talos/screen-screen-lift.PNG

Now you should be able to see the beam. If you still can't see the beam, you could double check that the high tension is on (yellow HT button in the FEG control tab of the microscope user interface). If the HT is on, but the beam is weak check that the operate button for the FEG is on (extraction voltage should be 4450, gun lens should be 5).

Load cartridge
---------------
      
Load the cartridge that you like by clicking on the position you want to load and then click on load in the Autoloader tab (this will take few minutes). You will notice that the column valves close automatically. 


Grid Screening
---------------

Open the column valves and insert the screen. If you can't see the beam, it could be that your ice is to thick for the current grid position. In that case, go to Stage and change the grid position (use joystick or double click in the stage map).

.. image:: /images/talos/stage1.PNG


