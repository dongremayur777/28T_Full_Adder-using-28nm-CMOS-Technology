# 28T_Full_Adder using 28nm CMOS Technology
  * [Abstract](#abstract)
  * [Reference Circuit Details](#reference-circuit-details)
  * [Reference Circuit Diagram](#reference-circuit-diagram)
  * [Reference Circuit Waveform](#reference-circuit-waveform)
- [Simulation in Synopsys](#simulation-in-synopsys)
  * [Schematic](#schematic)
  * [Parameters set for Voltage Source for Input A](#parameters-set-for-voltage-source-for-input-a)
  * [Parameters set for Voltage Source for Input B](#parameters-set-for-voltage-source-for-input-b)
  * [Transient Settings](#transient-settings)
  * [Netlist](#netlist)
  * [Waveform](#waveform)
- [Interchanging the outputs and inputs](#interchanging-the-outputs-and-inputs)
  * [Schematic](#schematic-1)
  * [Netlist](#netlist-1)
  * [Waveform](#waveform-1)
  * [Conclusion](#conclusion)
  * [Acknowledgement](#acknowlegement)
  * [References](#references)


## Abstract
Full adder is an essential component for the design and development of all types of processors like digital signal processors (DSP), microprocessors etc. In most of these systems adder lies in the critical path that affects the overall speed of the system.An adder is a digital circuit that performs addition of numbers and it plays an important role in today’s digital world. In processors and other kinds of computing devices, Adders are used in the arithmetic logic units. They are also utilized in other parts of the processors for calculating addresses, table indices, increment and decrement operations and other similar operations because it is the basic building block of on-chip libraries. Also, it can be used for the construction of many number representations and it is a trivial to modify an adder into an adder-subtractor. Full adder reduces circuit complexity and can be integrated in the calculators for addition and subtraction operations. At DSP oriented system and at networking side full adder is used mostly. Full adders can be cascaded (e.g.: ripple carry adder) easily so that one can make a cascade to add any number of bits that form the word- width of a system.
## Reference Circuit Details

Conventional CMOS Full Adder is the most basic full adder implementation techniques. Conventional CMOS Full Adder consists of 28 transistors. A, B and Cin are the inputs and Sum & Cout are the outputs. Static logic provides robustness against noise effects, so automatically provides a reliable operation. Pseudo NMOS pass-transistor logic and reduce the number of transistors required to implement a given logic function but these suffer from static power dissipation. On the other hand, dynamic logic requires less silicon area for implementation of complex function but charge leakage and charge refreshing are required which reduces the frequency of operation. This circuit uses both NMOS and PMOS transistors. In Conventional CMOS Full Adder, there are many leakage paths which lead to more sub threshold leakage.

## Reference Circuit Diagram
<img width="1371" alt="Reference_Ckt" src="https://user-images.githubusercontent.com/59500283/155388072-53c63be1-69c2-4d84-90e7-4cb95889fb67.png">## Reference Circuit Waveform
![image](https://user-images.githubusercontent.com/58599984/155004930-55f9993a-61f8-403f-a67d-c9c2d3c58a03.png)

# Simulation in Synopsys
## Schematic
![image](https://user-images.githubusercontent.com/58599984/155003310-dc58ccd8-5dc6-4d4b-94a0-c6d212ab88d7.png)
![image](https://user-images.githubusercontent.com/58599984/155003329-7643df8d-93fe-45a8-9809-77aa23e641ba.png)
Note: The transmission gate using M24 nad M25 is soley used to separate the input and output just for the simulation purpose, to plot input and output separately.
## Parameters set for Voltage Source for Input A
![image](https://user-images.githubusercontent.com/58599984/154890823-6743f686-9eed-4966-9420-56bd3a0ee0e2.png)
## Parameters set for Voltage Source for Input B
![image](https://user-images.githubusercontent.com/58599984/154891712-f6c4bfae-d422-4c86-8f40-9874719ed230.png)

## Transient Settings
![image](https://user-images.githubusercontent.com/58599984/154890716-35c2d360-befc-4476-9041-c360d751f378.png)

## Netlist
```


*  Generated for: PrimeSim
*  Design library name: full_adder
*  Design cell name: Carry_tb
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Wed Feb 23 18:37:06 2022

.global gnd!
********************************************************************************
* Library          : full_adder
* Cell             : Carry_Block
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt carry_block a b c gnd_1 vdd carry
xm11 carry carry_bar gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm8 net30 a gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm7 carry_bar b net30 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm2 net9 b gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm1 net9 a gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm31 carry_bar c net9 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm12 carry carry_bar vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm10 net34 a vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm9 carry_bar b net34 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm5 net23 b vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm4 net23 a vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm3 carry_bar c net23 vdd p105 w=0.1u l=0.03u nf=1 m=1
.ends carry_block

********************************************************************************
* Library          : full_adder
* Cell             : Inverter
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt inverter gnd_1 input not vdd
xm0 not input vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm1 not input gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
.ends inverter

********************************************************************************
* Library          : full_adder
* Cell             : Sum_Block
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt sum_block a b c carry_bar gnd_1 sum_bar vdd
xm29 sum_bar c net174 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm30 net174 b net178 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm31 net178 a net111 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm18 net111 c vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm19 sum_bar carry_bar net111 vdd p105 w=0.1u l=0.03u nf=1 m=1
xm20 net111 a vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm21 net111 b vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm26 sum_bar c net160 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm28 net164 b gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm27 net160 a net164 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm23 net150 a gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm22 sum_bar carry_bar net150 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm24 net150 b gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
xm25 net150 c gnd_1 gnd_1 n105 w=0.1u l=0.03u nf=1 m=1
.ends sum_block

********************************************************************************
* Library          : full_adder
* Cell             : Carry_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi24 a b c gnd! net55 carry carry_block
v1 net55 gnd! dc='1.8V'
v22 c gnd! dc=0 pulse ( 0 1.8 0 0.1u 0.1u 20u 40u )
v21 b gnd! dc=0 pulse ( 0 1.8 0 0.1u 0.1u 10u 20u )
v20 a gnd! dc=0 pulse ( 0 1.8 0 0.1u 0.1u 5u 10u )
c2 carry gnd! c=1p
c19 sum gnd! c=1p
xi23 gnd! net50 sum net55 inverter
xi9 gnd! carry net33 net55 inverter
xi15 a b c net33 gnd! net50 net55 sum_block

.tran '1u' '40u' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(a) v(b) v(c) v(carry) v(sum)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL



.end

```

## Conclusion
Thus, the addition for a single-bit is achieved using 28T full adder.
## Acknowledgement
1. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
2. Chinmay panda, IIT Hyderabad
3. Sameer Durgoji, NIT Karnataka
## References
1)Analysis and Performance Evaluation of 1-bit Full Adder Using Different Topologies
http://pnrsolution.org/Datacenter/Vol5/Issue1/26.pdf
2)Power and Delay Comparison in between Different types of Full Adder Circuits
https://www.ijareeie.com/upload/september/7_Power%20and%20Delay%20Comparison.pdf
3)Youtube Video - https://www.youtube.com/watch?v=AXU_J4wr_yA
  
