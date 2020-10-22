.. _atlas-epu:

Atlas and EPU
=============
 


Calibrate Image shifts
----------------------

Calibrate image shifts before to doing the atlas.

1. Find a recognizable feature in a grid-square you will not use. The feature should be large enough to spot at LM mode but also have smaller features that one can see at the Data acquisition mag. Something in the order of 2-4 um is usually good. 
2. Bring feature to eucentric height.
3. Center the edge of this feature at the data acquisition magnification using the fluorescent screen center.
4. Bring feature in focus.
5. In the Preparation tab click on Image Shift calibration and then Start Calibration.
6. The calibration routine starts off at the Data acquisition. Press continue. 
7. For the hole eucentric height and grid square magnifications, centre the feature via double clicking and re-acquire and if centred press continue.
8. Remove the aperture while collection with atlas presets, centre feature and re-acquire and if centred press continue. 
9. At the end of the routine, the log window will say image shift calibration finished successfully.

.. image:: /images/talos/calibrate_image_shifts.png


Atlas Acquisition
-----------------

Acquire an Atlas of the entire grid. 

1. Load the atlas presets. 
2. Check that the beam is centred or centre it.
3. Make sure you have roughly set the eucentric height of the grid and that the objective aperture is removed.
4. Click on Atlas and New sample.
5. Make sure the name is called according to your sll, dbb, or cem number that was generated via scipion, e.g. sll00214_date_gridx_atlas.
6. Choose the working directory that you created via scipion as the output folder. 
7. Hit Apply.
8. Click on 'Atlas Acquisition' and 'Acquire' to start the Atlas.


.. image:: /images/talos/atlas.PNG


The Atlas can be started from the centre of the grid or the current position. Atlas acquisition of the full grid takes around 20 minutes.

Set up EPU Session
------------------

1. Click on EPU tab and select New Session.
2. Make sure the name is called according to your sll, dbb, or cem number that was generated via scipion, e.g. sll00214_date_gridx_EPU. 
3. Choose your working directory that you created via scipion as the output folder.
4. Acquisition mode: Use fast hole centering for faster acquisition. Use accurate hole centring, if speed is not an issue and you want to centre the holes more accurate.
5. Save as MRC. 
6. Select the type of foil you are using and press apply.
7. Add your email and operator email in the recipents box.
8. Tick box: Send email on completion, etc.

.. image:: /images/talos/EPU_setup.PNG


Square Selection
----------------

1. Go to Square Selection. 
2. Click on Unselect all. 
3. Go to a square that you consider suitable by right-clicking and then selecting 'Move to grid-square' which centers the square with the stage.
4. Under the Preparation tab select the Grid-square condition from the drop-down menu and click 'Set'.
5. Adjust eucentric height. 
6. If the grid square is not broken (often breaks are only visible while tilting the stage), you can go back to the Square Selection in EPU and select the Grid Square by right clicking on it and then  on Add.
7. Selected squares will be in green. 
8. You can also see the squares more easily by opening a tile (the yellow rectangles). Right-click on a tile and click on 'Open Tile'.

.. image:: /images/talos/Bild3.png


Hole Selection
----------------

1. Click on Hole Selection or Area Selection if you are using lacey grids followed by Acquire. This records an image of the entire square and saves the X, Y and Z coordinates, which will be used to re-visit the square during the automated acquisition process.It is important that the last image you record of the Hole Selection/Area Selection has the correct Z-height values.
2. Once an image is recorded click on Measure Hole Size. This results in two yellow circles connected by a line. 
3. Drag each circle to neighboring holes and adjust the circle size to the hole size.
4. Click on Find Holes to allow the software to find the holes in the square. 
5. Adjust the ice-thickness histogram to select holes. You may also enter grey-values manually and hit apply.

