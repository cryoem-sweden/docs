
Falcon 3EC
==========
 
.. _f3ec-specifications:

Specifications
--------------
The Falcon 3EC camera is a direct electron detector with large pixels that has electron counting capability.

- Resolution: 4096 x 4096 pixels
- Readout speed: ~40 frames per second
- Dose rate, linear mode: 10-120 e/p/s
- Dose rate, counting mode: 0.5-1 e/p/s

.. _f3ec-mode:

Linear vs counting mode
-----------------------

The F3EC has two different modes. In the standard linear (high-speed) mode, one uses a high dose-rate and a short exposure time (typically a few seconds). The number of electrons hitting a pixel is estimated by the total amount of charge in the pixel divded by the typical charge from an electron. But, since each electron depositing energy across multiple neighboring pixels, there is some loss of spatial resolution. In couting (high-sensitivity) mode, the dose rate is kept low so that the camera can perform sub-pixel location of the detection events. This gives optimal detection quantum efficiency (DQE)--in particular at high spartial frequencies--but at the cost of much longer exposure times and lower through-put. So, which mode should one use? One has to consider what parameter is limiting the resolution of the reconstruction.

- If one has a highly hetrogeneous sample, then the resolution may be limited by the low number of particles in a given class. In this case, collecting in linear mode could be better, to get more particle images.
- If one have a small sample, then the resolution may be due to the reconstruction software not being able to properly determine the alignment of individual particle images. In this case, counting mode is advisable to increase the signal-to-noise of the micrographs.

In general, linear mode works well for larger particles. Counting mode is recommended for optimal image quality, but requires grids with densly packed with particles and/or longer data collection sessions.


Dose fractioning and frame alignment
---------------------------------------
 
The read-out spead of the F3EC camera is approximately 39.85 frames per second. The total number of *elemental frames* are indicated next to the exposure time. When setting the exposure time, EPU may change the time slightly to get an allowed number of frames.

The elemental frames are subsequently binned into dose fractions.  If the number of elemental frames is not evenly divisible by the selected number of dose fractions, then the last dose fraction will contain the remaining frames (and thus have a larger total dose).

There is an option in EPU to apply *alignment* of the elemental frames within a dose fraction. If this option is enabled, groups of six elemental frames are first combined (to increase the signal), and then global motion correction is applied between these sets of six frames. For the dose fractionation scheme, this adds a constrain that the total amount of elemental frames in each dose fraction must be a multiple of six (except in the last fraction, which will have all the remaining frames).

.. note::

    Some combinations of exposure time and number of dose fraction may result in :ref:`more than half <f3ec-setup-example>` of the total dose ending up in the last dose fraction.
    

.. _f3ec-fractionation-calculation:

To calculate the number of extra elemental fractions in the last dose fraction:

1. Divide the total number of elemental frames with the number of dose fractions.
2. If using the align option, take the largest number which is a multiple of six which is less than the average. (If align is set to no, just take the largest integer which is less than the average.) This will be the number of elemntal frames in the early dose fraction.
3. The number of extra elemental frames in the last dose fraction will be the total number of elemental frames minus the number of frames per dose fraction multiplied by the number of dose fractions.


.. _f3ec-setup:
   
Exposure and dose-fractionation procedure
-----------------------------------------

1. Select :ref:`magnification <f3ec-magtables>`. Pixel size should be (significantly) less than half of the desired maximum resolution.
2. Select :ref:`camera mode <f3ec-mode>` (linear or counting)
3. Select gun lens, spot size and intensity to achieve parallel illumination with an :ref:`appropriate dose rate <f3ec-specifications>` for the camera mode
4. Measure the dose-rate in a vacuum hole
5. Calculate the exposure time to achieve a given total dose (usually, 20-80 e/|A2|), by dividing the total dose with the dose rate per second. *N.b.* EPU may adjust the time slightly when you enter it. The number of *elemental frames* will be displayed next to the time.
6. Calculate the desired number of dose fractions to get a suitable dose per movie frame (usually, ~1 e/|A2|)
7. Estimate :ref:`the number of extra frames <f3ec-fractionation-calculation>` in the last dose fraction. Make sure that this number is not too high (more thant 2-3 times of the other fractions). If this number is too high, change the exposure time or the number of dose fractions slightly.

.. |A2| replace:: Å\ :sup:`2`\

.. _f3ec-setup-example:
                  
Example
^^^^^^^
- 150k magnification gives a pixel size of 0.95 Å/pixel
- For counting mode, parallel illumination of suitable dose rate can be achieved with gun lens 3, spot 8 and intensity 0.455. This gives a dose rate on the camera of 0.95 e/pixel/s.
- For a total dose of 60 e/|A2|, one needs ~60 second exposure.
- EPU will change this to 59.99 seconds for 2,331 elemental frames
- For ~1 e/pixel/dose fraction, one should have ~60 fractions
- Dividing 2,331 in 60 gives 38.85, so 38 frames per fraction with align=No. The last dose fraction will have 2,331-(60x38) = 51 extra frames (2.3 times more dose than in the earlier frames).
- With align=Yes, then there will be 6x6=36 frames per fraction, so the last dose fraction will have 2,331-(60x36) = 171 extra frames (5.75 times more dose than the early frames).
- With align=Yes, a better dose fractionation scheme is to fractionate into 55 fractions. This gives 2,331/55=42.38, so 7x6 elemental frames per dose fraction. The last fraction will have 2,331-(55x42) = 21 extra frames (1.5 times more dose than in the early frames).
- An extreme case is 19.99 second exposure with 776 elemental frames split into 65 dose fractions and align yes. This will give 6 elemental frames in the early dose fractions and 391 elemental frames in the last fraction (which is 50.5% of the total dose).


.. |A2| replace:: Å\ :sup:`2`\
 
.. _f3ec-magtables:

Magnification table, Talso Arctica F3EC, SciLifeLab Solna
---------------------------------------------------------

=============  =========  =====================
Magnification  Pixelsize  Calibrated pixel size
=============  =========  =====================
8500            17.5
11000           13.6
13500           10.7
17500		8.5
22000		6.6
28000		5.2
36000		4.1
45000		3.2
57000		2.6
73000		2.0
92000		1.6        1.54
120000		1.2        1.23
150000		0.98       
190000		0.76
240000          0.61
310000          0.48
390000          0.37
=============  =========  =====================


Magnification table, Glacios F3EC, Uppsala University
-----------------------------------------------------

=============  =========  =====================
Magnification  Pixelsize  Calibrated pixel size
=============  =========  =====================
17500		8.5
22000		6.6
28000		5.2
36000		4.1
45000		3.2
57000		2.6
73000		2.0
92000		1.6        1.556
120000		1.2       
150000		0.98       0.952
190000		0.76
=============  =========  =====================



File compression
----------------

The F3EC camera produces MRC movie stacks. These can be compressed and saved in the TIFF format to reduce the file size to 55-60% of the original size. https://relion.readthedocs.io/en/release-3.1/Reference/MovieCompression.html#falcon-3-counting
   

*Originally written by Daniel Larsson. Last updated March 17, 2022 by Daniel Larsson.*

