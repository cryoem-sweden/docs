
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
    

.. image:: /images/talos/import.png


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


Low Mag Grid Screening
----------------------

Open the column valves and insert the screen. If you can't see the beam, it could be that your ice is to thick for the current grid position. In that case, go to Stage and change the grid position (use joystick or double click in the stage map).

.. image:: /images/talos/stage1.PNG

Use the joystick to navigate to the grid squares.

.. image:: /images/talos/panel.png

Find an empty square and add its position and then find an adjacent square/area, with carbon film, to do the alignments. You can name your grid square positions accordingly.

.. image:: /images/talos/stage2.PNG


Eucentric Height
----------------

For any imaging or alignment, always bring the speciment to eucentric height (at Grid square magnification). 

1. Use the joystick to put a feature in the center of the flu-screen 
2. Go to the Stage tab.
3. Set Alpha to 30 degrees.

.. image:: /images/talos/stage1.PNG

4. Recentre the feature with the Z height.

.. image:: /images/talos/z_height.png

5. Reset the stage tilt.
6. Set the grid square presets and redo the eucentric height.
7. Set the hole-eucentric height presets, insert the objective aperture (100um) and redo the eucentric height.

.. image:: /images/talos/apertures1.PNG

.. note::

   In the status line you will see how the values for z height (Z) and alpha (A) change. It is important that you first centre your feature without tilt and use the z button when the stage is tilted.
   
.. note::

    Doing the eucentric height at diffiferent magnifications ensures that the feature does remain in the field of view. Z can be roughly set for atlas and grid square magnification and has to be exact for hole eucentric height.


Autofocus
---------

1. Navigate to a carbon area and set the 'data acquisition' presets.
2. Open the direct alignment tab (bottom right of monitor).

.. image:: /images/talos/direct_alignments.PNG

3. Press Beam shift and centre the beam using multi-function x&y.
4. Press Done when finished.

.. note::

   If you cannot see the beam lower the magnification.

5. Go to the auto-functions panel in EPU and select autofunctions-TEM, Autofocus, preset Autofocus
6. Press Start.

.. image:: /images/talos/autofocus_1.PNG

.. warning::

    Do not use the calibrations!
    
Autostigmate
------------

1. Go to the auto-functions panel in EPU and select autofunctions-TEM,  Autostigmate, preset Thon Ring
2. Press Start.

.. image:: /images/talos/stigmate_1.PNG


Grid Screening
--------------

.. note::

   The microscope is now aligned for screening. 

1. Use the atlas preset to navigate to a grid square.
2. In atlas mode always retract the objective aperture.
3. Use the grid square and hole / eucentric height presets to locate your target areas.
4. Always insert the objective aperture in  hole / eucentric height preset.
5. Redo the eucentric height.
6. Retract the flu-screen.
7. Take an image with data acquisition preset.
8. Save your images in your working directory via right click and save with overlay.

.. note::
   
   If the beam is moving into your image, centre the beam with beam shift.
   
   
Microscope alignment for EPU data collection
--------------------------------------------

1. Import your presets for either linear (short exposure with high dose) or counting mode (long exposure with low dose). 

.. note::

    The counting mode set up is more difficult, because the beam is very dim and one needs long exposure times when executing the auto-functions.

2. Set the hole-eucentric height presets.
3. Retract the objective aperture
4. Redo the eucentric height.
5. Navigate to a carbon area and set the ‘data acquisition presets.
6. Insert screen.
7. Open the direct alignment tab.
8. Centre the beam with beam shift. 	
9. Do the Autofocus routine.
10. Run the Autocoma routine as described :ref:`here <autofunctions-autocoma>`.
11. Insert the objective aperture. 
12. :ref:`centre the objective aperture <advanced-microscopy-centre-objective-aperture>`.
13. Optionally, verify :ref:`parallel illumination <advanced-microscopy-parallel-illumination>`
14. Redo the auto-focus and stigmator autofunction.

.. warning::

    Do not redo the coma-free alignment.

Check the beam dose
-------------------

1. Go to an empty square with atlas presets (or in case you saved the position in your stage map, press go).
2. Load data acquisition presets.
3. condense & centre beam.
4. Press Set again (in order to spread the beam to its original size). 
5. In the EPU panel, press measure dose. 
6. Note down the exposure dose and adjust the exposure time accordingly. For F3EC use, follow the procedure :ref:`here <f3ec-setup>`.

Atlas and EPU set up
--------------------

You can now proceed to :ref:`atlas acquisition and EPU set up <atlas-epu>`.


