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
![image](https://user-images.githubusercontent.com/58599984/155004906-3e55d52b-6090-4d4b-9f41-6f75b6e9cd37.png)
## Reference Circuit Waveform
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
*  Design library name: Feynman_gate
*  Design cell name: Feynman_gate
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Mon Feb 21 17:53:36 2022

.global gnd! vdd!
********************************************************************************
* Library          : Feynman_gate
* Cell             : Feynman_gate
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xm24 p net80 a gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm7 net74 q b gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm6 q net74 b gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm5 net74 p gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm0 q b net74 gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm25 a gnd! p vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm4 p q b vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm3 q p b vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm2 q b p vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm1 net74 p net80 vdd! p105 w=0.1u l=0.03u nf=1 m=1
v26 net80 gnd! dc=1.8
v17 b gnd! dc=0.01 pulse ( 1.8 0 0.1n 0.1n 0.1n 2u 4u )
v18 a gnd! dc=0.01 pulse ( 1.8 0 0.1n 0.1n 0.1n 1u 2u )








.tran '1u' '20u' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(a) v(b) v(p) v(q)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end
```
## Waveform
![image](https://user-images.githubusercontent.com/58599984/155003205-6933feb1-ec81-4627-8230-37746e44282a.png)
# Interchanging the outputs and inputs

## Schematic
![image](https://user-images.githubusercontent.com/58599984/155004055-dc48126a-26dd-4999-89d2-43b3a89d3ebf.png)
![image](https://user-images.githubusercontent.com/58599984/155004113-993a4526-4246-4214-a6da-bc1e19a51a54.png)
## Netlist
```
*  Generated for: PrimeSim
*  Design library name: Feynman_gate
*  Design cell name: Feynman_gate
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Mon Feb 21 17:41:35 2022

.global gnd! vdd!
********************************************************************************
* Library          : Feynman_gate
* Cell             : Feynman_gate
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xm24 p net80 a gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm7 net74 q b gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm6 q net74 b gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm5 net74 p gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm0 q b net74 gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm25 a gnd! p vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm4 p q b vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm3 q p b vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm2 q b p vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm1 net74 p net80 vdd! p105 w=0.1u l=0.03u nf=1 m=1
v26 net80 gnd! dc=1.8
v17 q gnd! dc=0.01 pulse ( 1.8 0 0.1n 0.1n 0.1n 2u 4u )
v18 p gnd! dc=0.01 pulse ( 1.8 0 0.1n 0.1n 0.1n 1u 2u )








.tran '1u' '20u' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(a) v(b) v(p) v(q)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end
```
## Waveform
![image](https://user-images.githubusercontent.com/58599984/155003970-690e6a0e-0664-4543-96f0-a0aa1cea5a87.png)
## Conclusion
Thus, the input and output can be interchanged in the Feynman Gate and the functionality of the Feynman Gate is verified using 32nm Technology node of Synopsys.
## Acknowledgement
1. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
2. Chinmay panda, IIT Hyderabad
3. Sameer Durgoji, NIT Karnataka
## References
1.	U. Kumar, L. Sahu and U. Sharma, "Performance evaluation of reversible logic gates," 2016 International Conference on ICT in Business Industry & Government (ICTBIG), 2016, pp. 1-4, doi: 10.1109/ICTBIG.2016.7892693.
2.	A. K. Rajput, S. Chouhan and M. Pattanaik, "Low Power Boolean Logic Circuits using Reversible Logic Gates," 2019 International Conference on Advances in Computing, Communication and Control (ICAC3), 2019, pp. 1-6, doi: 10.1109/ICAC347590.2019.9036799.
