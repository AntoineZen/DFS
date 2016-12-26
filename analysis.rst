Analysis
========

The reliablity of the circuit was determined in tree steps:
 - Lookup for manufacturer data or compute individual component reliability.
 - Compute the block reliability by summing the FITs of the components making the block.
 - Compute the circuit reliability by summit the block FITs.


Per-component failure rate
--------------------------

The following table gives the Failure rate for each component type in the circuit:

.. .. image:: img/FIT_table.png

Most FITS for the ICs have been taken from manufacturer data. In the table, the cell in orange have been determinted by annalogy, cell in blue where computed using the "MTBF calculator" This has been done for two IC. Both IC (MT41J128M16HA-15E and M25P32-VMF6P) are manufactured by *Micron Technology* that provides no reliabilty data.

The **MT41J128M16HA-15E** is a 2Gbit DRAM from Micron, organized in 16Meg * 16bits * 8 Banks. Data from *Allicance Memory* AS4C32M16D1A-5TIN where use instead. This device is a DRAM organized in 8Meg * 16bits * 4 banks. The manufacturer specify the reliabilty of this device to 11 FIT. As this device is 4 times smaller that MT41J128M16HA-15E, we can determine a equivalent FIT of 44, so that the reliabilty is proportional to the memory size.

The **M25P32-VMF6P** is a 32Mb Low-Voltage Serial NOR Flash. As no manufacturer data was available, data from a similar device has been used. Data for *Microchip* have been used. Microchip offers data from the whole 25 familiy with an FIT of 57.

The **GENNUM GN4124** i is a PCI-Express to local bus bridge. The manufacture (*Gennum*) does not provide reliablity data. As this IC is an ASIC (Application Specific IC), it is not possible to estimate a FIT from a similar component. In this case, it is mendatory to use the "MTBF calculator" program. For this device, The program compute a FIT of 50. 

Other Pasive and discret component FITs have been computed using the *MTBF calculator* program. When using this program, it is important to choose the **IEC-62380** predicition model to set the appropriate norm and the **GF** mission profile. GF mission profile stand from "Ground Fix". As our circuit is a PC card, this seems to be the appropiate profile. 


.. image:: img/FR_dist_by_type.png


Per-block failure rate
----------------------

.. image:: img/FR_dist_by_func.png

Circuit failure rate
--------------------


Conclusion
==========


