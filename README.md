# open-source-eda
# VSD W0rksh0p performing the Physical Design  using the 0pen-source t00l

# About the Workshop
 This workshop is basically gives me an overview of physical design using open-source tool.
It  design in such a simplified manner where I can learn concept ,take quizzes ,perform lab and bridge the learning gap through video tutorial which is really helpful.


# DAY 1
# Study and review various component of RISC-V based picoscoc
# IC design termonologies,opensource EDA tools and RISC-V based Soc design  
1-Introduction to QFN-48 package,chips,pad,core,die and IPs   

2-INTRODUCTION TO RISC-V 

RISC-V is an 0pen standard instructi0n set architecture based 0n established reduced instruction set c0mputer principles. It is pr0vided under 0pen-source license which gives it a huge advantage when c0mpared t0 0ther c0mmercial ISAs. It is a simple, stable, small standard base ISA with multiple standard extensi0ns. It was devel0ped in UC Berkeley.

The RISC-V ISA is defined as a base integer ISA, which must be present in any implementati0n, plus opti0nal extensi0ns t0 the base ISA. The base RISC-V ISA has a little-endian mem0ry system. The standard is maintained by the RISC-V f0undation. 

The base integer instructi0ns as represented as RV32I/RV64I and they 0perate 0n integer numbers. 0ther extensi0ns are as f0llows:

RV64M - multiply extension
RV64F and RV64D - single and d0uble precisi0n fl0ating p0int extensi0n
A c0re with all the above extensions will be represented as RV64IMFD.  

3-From software applicati0n t0 hardware  
4-picorv32 and picosoc review  
5-Raven Soc and Raven chip review 

Raven is using a very p0pular 32-bit RISC-V c0re (PicoRV32) devel0ped by Cliff0rd W0lf, a well-kn0wn 0pen s0urce champi0n. The c0re was previ0usly pr0ven with an FPGA implementati0n and Raven is the first SoC built with it. The system integrator is 0ur 0wn Tim Edwards, another champi0n in the 0pen s0urce d0main.  

6-Introduction to IC design c0mponent and 0pen s0urce EDA t00ls  
7-Step to start synthesizing picorv32,report rati0(register count)  
8-Test open source EDA t00l using sample design and vsdfl0w utility  
9-Steps to perform lab on Platform  

![Screenshot 2021-03-03 205321](https://user-images.githubusercontent.com/10924505/110203453-60400500-7e94-11eb-8717-f9b8dea6471c.png)


![Screenshot 2021-03-03 215258](https://user-images.githubusercontent.com/10924505/110203496-97aeb180-7e94-11eb-9ef6-08ec942d6cf3.png)


![Screenshot 2021-03-03 221355](https://user-images.githubusercontent.com/10924505/110203503-a09f8300-7e94-11eb-9dbf-8fe0aebd6d33.png)


![Screenshot 2021-03-03 222027](https://user-images.githubusercontent.com/10924505/110203515-a9905480-7e94-11eb-9df4-295bd62479fb.png)


![Screenshot 2021-03-03 223245](https://user-images.githubusercontent.com/10924505/110203520-aeed9f00-7e94-11eb-97f6-669e4d87f3e3.png)


![Screenshot 2021-03-03 225906](https://user-images.githubusercontent.com/10924505/110203536-c0cf4200-7e94-11eb-82ba-36630565577a.png)


# DAY 2
# Chip planning strategies and introduction to foundry library cells

# Chip floor planning consideration
# Aspect Rati0 and Utilizati0n Fact0r  
Tw0 key descripti0ns 0f a fl00rplan are utilizati0n and aspect rati0. The am0unt 0f area 0f the die c0re the standard cells are taking up is called utilizati0n. N0rmally we g0 f0r 50-70% utilizati0n t0, 0r utilizati0n fact0r 0f 0.5-0.7. Keeping within this range all0ws f0r 0ptimizati0n 0f placement and realizable r0uting 0f a system. Aspect rati0 can specify the shape 0f y0ur chip by the height 0f the c0re area divided by the width 0f the c0re area. An aspect rati0 0f 1 discribes the chip as a square.  


# Preplaced Cells  
Preplaced cells, 0r MACR0’s, are imp0rtant t0 enable hierarchical PnR fl0w. Preplaced cells enable VLSI engineers t0 granularize a larger design. In fl00rplanning we define l0cati0ns and bl0ckages f0r preplaced cells. Bl0ckages are needed t0 ensure n0 standard cells are mapped where the placeplaced cells are l0cated.

# Dec0upling Capacit0rs  
Dec0upling capacit0rs are placed l0cal t0 preplaced cells during Fl00rplanning. V0ltage dr0ps ass0ciated with interc0nnect wires can heavily affect 0ur n0ise margin 0r put it int0 an indeterminate state. Dec0upling capacit0r is a big capacit0r l0cated next t0 the macr0s t0 fix this pr0blem. The capacit0r will charge up t0 the p0wer supply v0ltage 0ver time and it will w0rk as a charge reserv0ir when a transiti0n is needed by the circuit instead 0f the charge c0ming fr0m the p0wer supply. Theref0re it “dec0uples” the circuit fr0m the main supply. The capacit0r acts like the p0wer supply.  

# P0wer Planning  
P0wer planning during the Fl00rplanning phase is essential t0 l0wer n0ise in digital circuits attributed t0 v0ltage dr00p and gr0und b0unce. C0upling capacitance is f0rmed between interc0nnect wires and the substrate which needs t0 be charged 0r discharged t0 represent either l0gic 1 0r l0gic 0. When a transiti0n 0ccurs 0n a net, charge ass0ciated with c0upling capacit0rs may be dumped t0 gr0und. If there are n0t en0ugh gr0und taps charge will accumulate at the tap and the gr0und line will act like a large resist0r, raising the gr0und v0ltage and l0wering 0ur n0ise margin. T0 bypass this pr0blem a r0bust PDN with many p0wer strap taps are needed t0 l0wer the resistance ass0ciated with the PDN.  

# Pin Placement  
Pin placement is an essential part 0f fl00rplanning t0 minimize buffering and impr0ve p0wer c0nsumpti0n and timing delays. The g0al 0f pin placement is t0 use the c0nnectivity inf0rmati0n 0f the HDL netlist t0 determine where al0ng the I/0 ring a specific pin sh0uld be placed. In many cases, 0ptimal pin placement will be acc0mpanied with less buffering and theref0re less p0wer c0nsumpti0n. After pin placement is f0rmed we need t0 place l0gical cell bl0ckages al0ng the I/0 ring t0 discriminate between the c0re area and I/0 area.

# Library binding and plcements  
1-Netlist binding and initial place design  
2-0ptimize placement using  estimated wire length and capacitance  
3-Final placement 0ptimizati0n  
4-Need f0r library and c0nsiderati0n  
# Cell design and characterizati0n fl0ws
1-Input f0r cell design  
2-Circuit design steps  
3-Lay0ut design Steps  
4-Typical characterizati0n fl0w  
# General timing characterizati0n parameter
1-Timing thresh0ld definit0n  
2-Pr0pagati0n delay and transiti0n  

 



![Screenshot 2021-03-04 221835](https://user-images.githubusercontent.com/10924505/110203753-e14bcc00-7e95-11eb-97ab-e53c7dc886b8.png)






# DAY 3
# Design and characterize one library cell using Magic layout tool and ngSpice
# Labs for CMOS inverter ngspice simulation  
1-Spice deck creation for CMOS inverter  
2-Spice simulation lab for CMOS INverter  
3-Switching threshold Vm  
4-Static and Dynamic simulation of CMOS  
# Art of layout using Euler's path plus stick diagram 
1-Pre layout simulation of test circuit  
2-Layout using only stick diagram  
3-Euler's path for Fn-input gate reordering  
4-Improved stick diagram for new input gate reordering  
5-Abstract layout from stick diagram  
# Lab for Magic and post-layout ngspice simulations
1-Derive actual dimension for Fn  
2-Script to create layout in magic  
3-Final layout and input/output labelling  
4-Post layout ngspice simulation  

# Inception of layout CMOD fabrication process
1-Create active region  
2-Formation of n-well and p-well  
3-Formation of gate  
4-LDD formation  
5-Source-drain formation  
6-Local interconnect formation  
7-Higher level metal formation  



![Screenshot 2021-03-05 170406](https://user-images.githubusercontent.com/10924505/110203794-16f0b500-7e96-11eb-85a4-c58620753da7.png)



![Screenshot 2021-03-05 172432](https://user-images.githubusercontent.com/10924505/110203803-1f48f000-7e96-11eb-8a72-9fb0c1a6072f.png)



![Screenshot 2021-03-05 181940](https://user-images.githubusercontent.com/10924505/110203813-31c32980-7e96-11eb-94f9-9b8d4fbb886f.png)


![Screenshot 2021-03-05 182346](https://user-images.githubusercontent.com/10924505/110203827-40a9dc00-7e96-11eb-9385-48e91d792527.png)


![Screenshot 2021-03-05 182841](https://user-images.githubusercontent.com/10924505/110203842-4a334400-7e96-11eb-88e9-3530384ddb60.png)




![Screenshot 2021-03-05 183559](https://user-images.githubusercontent.com/10924505/110203861-57e8c980-7e96-11eb-833b-1b370db07e34.png)


![Screenshot 2021-03-05 183720](https://user-images.githubusercontent.com/10924505/110203874-5fa86e00-7e96-11eb-9314-ce892dcf475c.png)


![Screenshot 2021-03-05 183857](https://user-images.githubusercontent.com/10924505/110203883-6636e580-7e96-11eb-9adb-66bb4e31d1eb.png)



![Screenshot 2021-03-05 184404](https://user-images.githubusercontent.com/10924505/110203889-6b943000-7e96-11eb-927e-e230304c2796.png)


# DAY 4

# Pre layout Timing-analysis and importance of good clock tree

# Timing modelling using delay table
1-Introduction to delay table  
2-Delay table usage  

# Timing analysis with ideal clock
1-Setup timing analysis and introduction to flip flop setup time  
2-Introduction to clock jitter and uncertainity  

# Clock tree synthesis and signal integrity
1-Clock tree routing and buffering using H-tree algorithm  
2-crosstalk and net shielding  

# Timing analysis with real clock

1-Setup timing analysing using real clock  
2-Hold timing analysis using real clock  


![Screenshot 2021-03-06 115330](https://user-images.githubusercontent.com/10924505/110203921-8d8db280-7e96-11eb-940c-653fcc04958d.png)

![Screenshot 2021-03-06 120110](https://user-images.githubusercontent.com/10924505/110203929-97afb100-7e96-11eb-8572-633b77642675.png)



![Screenshot 2021-03-06 121654](https://user-images.githubusercontent.com/10924505/110203939-a5fdcd00-7e96-11eb-8b4a-e5a6aec22771.png)


![Screenshot 2021-03-06 122444](https://user-images.githubusercontent.com/10924505/110203951-b0b86200-7e96-11eb-8e4d-3ecc13f8467a.png)



![Screenshot 2021-03-06 123718](https://user-images.githubusercontent.com/10924505/110203963-bada6080-7e96-11eb-9253-9f853341752e.png)

![Screenshot 2021-03-06 143340](https://user-images.githubusercontent.com/10924505/110203982-cb8ad680-7e96-11eb-87e4-89a0efc539dd.png)

![Screenshot 2021-03-06 143459](https://user-images.githubusercontent.com/10924505/110203998-d47ba800-7e96-11eb-9b3d-87845f121abe.png)

![Screenshot 2021-03-06 143845](https://user-images.githubusercontent.com/10924505/110204010-df363d00-7e96-11eb-8e56-68a41859c1f3.png)

![Screenshot 2021-03-06 144532](https://user-images.githubusercontent.com/10924505/110204018-e78e7800-7e96-11eb-9b64-111bc807cffb.png)

# DAY 5
# Routing and design rule check(DRC)
1-Introduction to maze routing  
2-Lee's algoritm conclusion  
3-Design rule check  
4-Introduction to IEEE-1481--1999 SPEF format  
5-SPEF representation of NET  
6-Distributed resistance and capacitance in SPEF  
7-SPEF header descrition  

# PNR interactive flow tutorial

1-Few tips on PIN placement and floor planning chip  
2-Placement and pre-route STA  
3-Routing and post route STA  


![Screenshot 2021-03-07 120936](https://user-images.githubusercontent.com/10924505/110232091-ac954e80-7f41-11eb-83b3-a35227695c22.png)




![Screenshot 2021-03-07 122323](https://user-images.githubusercontent.com/10924505/110232100-b74fe380-7f41-11eb-8880-c5d3859f067d.png)




![Screenshot 2021-03-07 122217](https://user-images.githubusercontent.com/10924505/110232105-c171e200-7f41-11eb-897c-c0148cade2ea.png)


![Screenshot 2021-03-07 125115](https://user-images.githubusercontent.com/10924505/110232502-0a2a9a80-7f44-11eb-9dda-70be864f974c.png)



![Screenshot 2021-03-07 123852](https://user-images.githubusercontent.com/10924505/110232505-131b6c00-7f44-11eb-9d29-cf2bc4302e11.png)


![Screenshot 2021-03-07 124632](https://user-images.githubusercontent.com/10924505/110232515-1adb1080-7f44-11eb-81c9-3061e826532e.png)


![Screenshot 2021-03-07 124814](https://user-images.githubusercontent.com/10924505/110232524-23334b80-7f44-11eb-9577-1044866132f3.png)


![Screenshot 2021-03-07 124908](https://user-images.githubusercontent.com/10924505/110232544-40681a00-7f44-11eb-9728-2c5bcbf8c72e.png)


![Screenshot 2021-03-07 125038](https://user-images.githubusercontent.com/10924505/110232549-4e1d9f80-7f44-11eb-8be1-7958db4660c5.png)




# Acknowledgement  
Kunal Ghosh -CO Founder VSD(VSD Corp.pvt.ltd)











