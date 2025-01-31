### Digital SoC design 
**Introduction to QFN-48 package,chip,pads,core,die and IPs**


Let us look in this picture-
![image](https://github.com/user-attachments/assets/11b76b2a-d925-4a33-8e9f-0c83eced59c9)

 
We all know what it is - A Arduino board. But do we know how to make this?  
The process to make this is just like this-
![Screenshot (46)](https://github.com/user-attachments/assets/30db5ddf-20ae-432b-be81-381ecf8c8e45)

But we are not here for arduino making or SoC design, we are here for chip design! So were are only going to learn(and look inside) about the bottom left corner of the Arduino.
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
So, this is the flow - Apps to System Software to OS to Compiler to the Assembler and at last to the Hardware.






