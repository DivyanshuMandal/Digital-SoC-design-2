### Digital SoC design 
**Introduction to QFN-48 package,chip,pads,core,die and IPs**


Let us look in this picture-
![image](https://github.com/user-attachments/assets/11b76b2a-d925-4a33-8e9f-0c83eced59c9)

 
We all know what it is - A Arduino board. But do we know how to make this?  
The process to make this is just like this-
![Screenshot (46)](https://github.com/user-attachments/assets/30db5ddf-20ae-432b-be81-381ecf8c8e45)

But we are not here for arduino making or SoC design, we are here for chip design! So were are only going to learn(and look inside) about the bottom right corner of the Arduino.
Those just look like these (Rough implementation of that)-
![Screenshot (47)](https://github.com/user-attachments/assets/14cb53ac-9b0e-43e5-8edb-49fd4acd9849)

This is a QFN-48 (Quad Flat No-leads). Through learning, we will learn that it is called as a package ,not a chip


This is not just the end of it, there are many parts to it too! Just like this-
![Screenshot (48)](https://github.com/user-attachments/assets/dcb6f24e-4c55-467d-b989-dfddfdbc1843)

These wires are used to connect the chip to their respective pins. They are known as wire bonds.


<ins>Wire bonds</ins> - Wire bonding is a process that creates electrical connections between semiconductor chips and their packages or other chips.


There are also some other parts of a package. The're shown in the given image-
![Screenshot (49)](https://github.com/user-attachments/assets/b3d58203-9a90-4141-a196-5ef422529b19)

<ins>Pads</ins> - In chip design, "pads" refer to the metallic areas located on the edges of a semiconductor die.

<ins>Die</ins> - In chip design, a die is a small piece of semiconducting material that contains a functional circuit.

<ins>Core</ins>  - In chip design, a core is a self-contained processing unit that can perform computations and execute instructions independently.

So as, we have learnt about those words, we will look how a sample SoC or a sample chip looks like-
![Screenshot (50)](https://github.com/user-attachments/assets/ade220e7-a2d2-4836-b2e1-aca4554bab21)


The labelled parts are known as Foundry IPs

<ins>Foundry IPs</ins> - Foundry IPs are reusable design modules that are used in chip design and manufactured by foundries.Foundry IPs are a critical part of chip design. They carry the most useful things on a chip. A foundry is like a factory in a package and have a lot machines. Physical SoC designers work heavily on those machines.

There is 1 more part of a package. They are known as macros-
![Screenshot (51)](https://github.com/user-attachments/assets/a1839cbd-642b-485f-bd29-a270d6873bba)

<ins>Macros</ins> - In chip design, "macros" refer to large, pre-designed functional blocks like memory cells, analog circuits (like DACs or ADCs), or clock generators.

**Introduction to RISC-V**

<ins>ISAs (Instruction Set Architecture)</ins> - ISAs or Instruction Set Architecture are a way to talk to the computers. In brief, ISA is a model that defines how software controls a computer's CPU.

Let us delve deeper into the topic-
![Screenshot (52)](https://github.com/user-attachments/assets/be879d04-fb51-486c-bca4-5d96f4da3cd6)

Here we acually see the process of making an SoC. The process starts by writing a C program to make the SoC using Hexa-decimal format characters. Those characters have to be next translated into Binary Logic. Finally, after converting the characters into the binary form, we can now implement it on the hardware or chip that we are using. But before implementation, we have to look into one more step- Giving the specifications. To give the specs we can use any HDL, like in the image, we see that the person is using picorv32 cpu core. This architecture can be now finally implemented on the layout, which is using qflow. 

Let delve now to another related topic!-
![Screenshot (53)](https://github.com/user-attachments/assets/c95e7938-a57c-4095-99fb-c8294920f968)

This shows how some apps are implemented on the hardware. To begin with, we see the Operating System (OS). The operating system carries a lot of tasks, like-

i> Handle IO operations

ii> Handle Low level system functions

iii> Allocate memory

After that we code the software using C,C++,VB,Java etc. in the hexi-decimal format. Then, we push the code into the compiler and after that the instructions are inputted by a RTL language like picorv32 etc. The use of the compiler is to convert the program language to their respective languages. Like someone can use ARM language, or the RISC-V language in a .exe file. Then, there comes the comes the assembler, whose job is to convert the language in machine language which uses 2 logics- logic 1 and logic 0. Then, finally the binary language is fed to the hardware which recognises how to do the functions.
So, this is the flow - Apps to System Software to OS to Compiler to the Assembler and at last, to the Hardware.

Let us understand this with an example-
![Screenshot (55)](https://github.com/user-attachments/assets/28b92a4b-95ad-4765-a210-00a8e52c21e6)

This is a model of a stopwatch, but it is just to show the code of the assembler and the compiler. The compiler converts the code into the used language of the hardware, and then the assembler will convert it into binary for the hardware, and then code will be implemented on the hardware. So this is the way a stopwatch should behave, if the code is written correctly. 
In this course we have mostly focused on RISC-V, but to understand it fully, we have to understand many terms and terminologies.
Just like the ones shown here-
![Screenshot (56)](https://github.com/user-attachments/assets/1a26dafa-e3ab-46f3-b3f7-cd715a352275)

Here, we see that the instr.1 and instr.2 acts as a abstract interface between the code and the hardware. It is called as the "architecture" of the computer or the ISA.

If we try to expand this more we see this-
![Screenshot (58)](https://github.com/user-attachments/assets/94130236-ce2f-41ad-a2ac-fcf0514b31d8)

There is more to the travels between the assembler to the hardware. The hardware only understands 0 and 1. For eg:- 00000000011001010000001100110011. This performs the additions of the registers like x3,x6,x10 etc. For this the instr.2 (instructions) have told the hardware to work like this only. So to do this we have to use an RTL to put the instructions inside the hardware. Then this is converted into the netlist, which is the software implementation of the hardware. Finally after the netlist, the actual hardware is now implemented fully in the SoC.


**SoC design using OpenLANE**

For digital ASIC design we need three fundamentals-
![Screenshot (59)](https://github.com/user-attachments/assets/83a147fe-ed90-4b37-a49d-696cd2c59347)

<ins>EDA tools</ins> - Electronic design automation (EDA) tools are software programs that help design and analyze chips and other electronic systems.

<ins>RTL designs</ins> - Register-transfer-level (RTL) design is a step in the process of designing digital circuits for chips.

<ins>PDK Files</ins> - PDK data in chip design is a collection of files that describe a semiconductor process and are used to design integrated circuits (ICs). PDK stands for "process design kit".

Digital, open-source ASIC design has been a dream for many years. Open-source PDKs,RTLs and EDAs. There are hundreds of open-source RTLs, like Github.org, librecores.org, opencores.org. There are some open-source EDA tools too, like Qflow, OpenROAD, OpenLANE etc.
But before we see more open-source PDK tools, we have to learn about PDKs first.

1>What is a PDK?

Ans. i> In the "Age of Gods" the design of an IC was tightly integrated with the manufacturing process available within each company-

a> Those who controlled the physics controlled the whole creative agenda!

ii> Lynn Conway and Carver Mead envisioned the need for seperating the design from technology 

a> Pioneered the "structured" methodology based on the lambda-based rules.

iii> Since then, we started to see Pure Play Fabs and Fabless design companies.

iv> PDK = the interface between the FAB and the designers

v> PDK = Process Design Kit

vi> Collection of files used to model a fabrication process for the EDA tools used to design an IC-

a> Process design rules- DRC,LVS,PEX

b> Device modules 

c> Digital Standard Cell libraries 

d> I/O libraries

e> ...

But still open-source PDKs are still a problem - of the past. A few months ago Google and Skywater produced their first open-source PDK - FOSS 130nm Production PDK in June 30, 2020. 

But, 130nm still in use?

Ans. Yes these are still used! They have made this configuration because to make it more accesible 

Still, are 130nm fast?

Ans. Yes! Intel's P4EE (Pentium 4 Extreme Edition) has a speed of about 3.46 G.hz per clock! A more pipelined version can achieve a good 1 G.hz per clock.

The ASIC design objective is RTL to GDSII- also called as automated PnR or Physical Implementation.

**Simplified RTL2GDS flow**

Let us look at this image-

![Screenshot (60)](https://github.com/user-attachments/assets/85bd8c69-8c0d-43ec-8d72-8fef9b06388d)

Yes, you can say that this is a simplified RTL2GDS flow.

The plans to the simplified RTL to GDSII are shown as here-

a> Synthesis                  

b> Clock tree synthesis                  

c> Floor/Power Planning

d> Routing                   

e> Placement                            

f> Sign Off

a> <ins>Synthesis</ins> - Converts RTL to a circuit out of components from the standard cell library(SCL)-
![Screenshot (61)](https://github.com/user-attachments/assets/a979c348-5caf-4a20-ab11-444a27f5828b)

Standard cells have a regular layout.
![Screenshot (62)](https://github.com/user-attachments/assets/28c2b61a-41b7-4a45-8ab1-1be9ff650d1c)

Each has different views and models - 

i> Electrical, HDL, SPICE,

ii> Layout(Abstract and Detailed)

iii>...

b> <ins>Floor and Power planning</ins> - In chip design, "floor planning" refers to the initial layout of a chip, defining the placement and size of major functional blocks (like memory, logic units, I/O pads) to optimize chip area and wire length. There are 2 types of floor planning. 

i> Chip Floor Planning - Partition the chip die between different system buiding blocks and place the I/O pads.
![Screenshot (63)](https://github.com/user-attachments/assets/6bc90966-7465-4d28-9ba9-419bfd410372)

ii> Macro- Floor Planning - In this type, it defines the dimensions, pin location, and also defines the rows in the hardware.
![Screenshot (64)](https://github.com/user-attachments/assets/7b5de412-ab0b-491b-942a-8b5d120f9d71)

<ins>Power Planning</ins> - Power planning involves designing the power distribution network to ensure every part of the chip receives a stable and sufficient power supply.

c> <ins>Placement</ins> - Place the cells on floorplan rows, aligned with the sites.
![Screenshot (65)](https://github.com/user-attachments/assets/d5d13397-1f4f-43fd-89e9-03b4747fc892)

Placement can be done in 2 types - Global and Detailed

i> Global placement - Random placement like this-
![Screenshot (66)](https://github.com/user-attachments/assets/f3fe7a90-1a1d-432c-9dff-36daf7383a28)

ii> Detailed Placement - Detailed placement, like this-
![Screenshot (66)](https://github.com/user-attachments/assets/a606dcdd-a996-4e48-b307-7bb0054555ba)

d> <ins>Clock Tree synthesis</ins> - To create a clock distribution network-
i> Deliver the clock to all sequential elements (For.eg; FF)

ii> With minimum skew (0 is hard to achieve)

iii> And in a good shape.

iv> Usually in tree form.
![Screenshot (67)](https://github.com/user-attachments/assets/88effd99-c272-47b9-af89-9c43e7676220)

v> Implement the interconnect using the avaible metal layers.
![Screenshot (70)](https://github.com/user-attachments/assets/4d456333-915e-4752-b66e-1ebdaa335aef)

e> <ins>Routing</ins> - i> Metal tracks form a routing grid

ii> Routing Grid is huge

iii> Divide and Conquer

- Global routing: Generates routing guides.

- Detailed Routing: Uses the Routing guides to implement the actual wring

f> <ins>Sign Off</ins> - i> Physical verifications

- Design rules checking (DRC)

- Layout vs. Schematic (LVS)

ii> Timing Verification

- Static Timing Analysis

We have learnt the simplified terms, but the problem is tougher when using Open-source EDA.


