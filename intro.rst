Introduction
============

This document describes the reliability analysis done on the "SPEC" card developed by the CERN in the context of the OHWR project. SPEC stand for **S**\ imple **P**\ CI-**E**\ press **C**\ arier. The final goal of this analysis is to compute the "Mean Time Between Failures" or MTBF of the whole card.


Circuit overview
----------------

.. figure:: img/spec_v1.1_top.JPG
    
    SPEC V4 board

The proposed Circuit (SPEC V4) is made of a single PCB. This PCB is a FGPA card meant to be used inside a PC connected trough the PCI-Express (PCIe) bus. The card also offers a FMC connector and SFP interface. FMC stand for "FPGA Mezzanine Connector", it is an open standard that propose an interface between a FPGA board and mezzanine cards. SFP is a generic connector for cooper and fiber based Ethernet. The :numref:`fmc-mez-example` is an example of FMC mezzanine cards:

.. _fmc-mez-example:
.. figure:: img/UMFT601X.jpg
    
    FMC mezzanine card example

This card can be also utilized stand-alone thanks to a power connector, USB to serial bridge and USB JTAG interface.

This card can be decomposed in the following blocks:

FPGA
  The Xilinx Spartan 6 FGPA is the central piece of this circuit. This block also contains all supporting passives components (Decoupling caps, line terminations resistors, etc...)
  
PCIe Bridge
  This block is converting the PCIe signals to signals that can be interfaced to the FPGA. This block is build around the Genum GN4124 IC.
  
DDR
  The RAM for the FPGA.

PSU
  Power supply for the whole circuit.
  
Clock Generation
  Quartz, oscillator and clock distributions ICs.
  
From this, the block diagram from :numref:`block-diagram` can be drawn:

.. _block-diagram:
.. figure:: img/Block_diagram.png
    :alt: Block diagram.
    
    SPEC v4 Block diagram.

