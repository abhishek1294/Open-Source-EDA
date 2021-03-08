# open-source-eda
# VSD Workshop performing the Physical Design  using the open-source tool

# About the Workshop
 This workshop is basically gives me an overview of physical design using open-source tool.
It  design in such a simplified manner where I can learn concept ,take quizzes ,perform lab and bridge the learning gap through video tutorial which is really helpful.


# DAY 1
# Study and review various component of RISC-V based picoscoc
# IC design termonologies,opensource EDA tools and RISC-V based Soc design  
1-Introduction to QFN-48 package,chips,pad,core,die and IPs 

Aspect Ratio and Utilization Factor
Two key descriptions of a floorplan are utilization and aspect ratio. The amount of area of the die core the standard cells are taking up is called utilization. Normally we go for 50-70% utilization to, or utilization factor of 0.5-0.7. Keeping within this range allows for optimization of placement and realizable routing of a system. Aspect ratio can specify the shape of your chip by the height of the core area divided by the width of the core area. An aspect ratio of 1 discribes the chip as a square.

Preplaced Cells
Preplaced cells, or MACRO’s, are important to enable hierarchical PnR flow. Preplaced cells enable VLSI engineers to granularize a larger design. In floorplanning we define locations and blockages for preplaced cells. Blockages are needed to ensure no standard cells are mapped where the placeplaced cells are located.

Decoupling Capacitors
Decoupling capacitors are placed local to preplaced cells during Floorplanning. Voltage drops associated with interconnect wires can heavily affect our noise margin or put it into an indeterminate state. Decoupling capacitor is a big capacitor located next to the macros to fix this problem. The capacitor will charge up to the power supply voltage over time and it will work as a charge reservoir when a transition is needed by the circuit instead of the charge coming from the power supply. Therefore it “decouples” the circuit from the main supply. The capacitor acts like the power supply.

Power Planning
Power planning during the Floorplanning phase is essential to lower noise in digital circuits attributed to voltage droop and ground bounce. Coupling capacitance is formed between interconnect wires and the substrate which needs to be charged or discharged to represent either logic 1 or logic 0. When a transition occurs on a net, charge associated with coupling capacitors may be dumped to ground. If there are not enough ground taps charge will accumulate at the tap and the ground line will act like a large resistor, raising the ground voltage and lowering our noise margin. To bypass this problem a robust PDN with many power strap taps are needed to lower the resistance associated with the PDN.

Pin Placement
Pin placement is an essential part of floorplanning to minimize buffering and improve power consumption and timing delays. The goal of pin placement is to use the connectivity information of the HDL netlist to determine where along the I/O ring a specific pin should be placed. In many cases, optimal pin placement will be accompanied with less buffering and therefore less power consumption. After pin placement is formed we need to place logical cell blockages along the I/O ring to discriminate between the core area and I/O area.
2-INTRODUCTION TO RISC-V    
3-From software application to hardware  
4-picorv32 and picosoc review  
5-Raven Soc and Raven chip review  
6-Introduction to IC design component and open source EDA tools  
7-Step to start synthesizing picorv32,report ratio(register count)  
8-Test open source EDA tool using sample design and vsdflow utility  
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
1-Utilization factor and aspect ratio  
2-concept of pre-placed cells    
3-Decoupling capacitor and power planning    
4-Pin placement and logical cell placement blockage  
5-Pin arranagement and automatic grouping of vectors  
6-Floor planning chips and floor planning labs  
# Library binding and plcements  
1-Netlist binding and initial place design  
2-optimize placement using  estimated wire length and capacitance  
3-Final placement optimization  
4-Need for library and consideration  
# Cell design and characterization flows
1-Input for cell design  
2-Circuit design steps  
3-Layout design Steps  
4-Typical characterization flow  
# General timing characterization parameter
1-Timing threshold definiton  
2-Propagation delay and transition  


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











