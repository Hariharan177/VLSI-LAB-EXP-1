Simulate and Synthesis Logic Gates,Address and Subractors Using Vivado

AIM: To Simulate and Synthesis Logic Gates,Adders and Subtractor using Vivado Software

APPARATUS REQUIRED:Vivado™ ML 2023.2

PROCEDURE:

Open Vivado: Launch Xilinx Vivado software on your computer.

Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:
#1:-

FULL_ADDER:-

full adder(code):
```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
```



OUTPUT:

Full Adder(Simulation):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/0478f98a-81c0-40c2-9204-2596fc524a33)

Full Adder(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/a31f9efa-dfc5-4a83-9bff-c1df46f53860)


#2:-
FULL_SUBTRACTOR:-

full_subtractor(code):
```
// fullsubtractor using gate level modeling
module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
```
OUTPUT:

Full Subtractor(Simulation):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/c3d6447e-3764-4510-9bd5-2cfcb70f06e7)

Full Subtractor(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/9ee0dc43-ff8e-4eac-8181-6aed85b78779)


#3:-
Half_adder(code):
```
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; // sum and carry
or(sum,a,b);
and(carry,a,b);
endmodule
```
OUTPUT:

Half Adder(Simulation):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/d29d151a-9d3e-47cc-b36d-20faef9b7e66)

Half Adder(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/362085c4-47d2-4601-81d5-21cfdfe0b085)

#4:-
Half_Subtractor(code):
```
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule
```
OUTPUT:

Half Subtractor(Simulation):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/36c716d8-0b17-47e3-9422-c7bb83d44777)

Half Subtractor(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/6b30308f-624c-4ce0-8040-fd58930844ef)

#5:-
Logic_gates(code):
```
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b);  
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```
OUTPUT:

Logic Gates(Simulation):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/22e1a918-4f75-4847-a0bf-d57bdbbe21a4)

Logic Gates(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/0cd6e3f8-830d-4a72-87c1-8d24beff39d0)

#6:-
RIPPLE_CARRY_Adder(4-BIT):-
```
module rippe_adder(S, Cout, X, Y,Cin);
input [3:0] X, Y;// Two 4-bit inputs
input Cin;
output [3:0] S;
output Cout;
wire wl, w2, w3;

fulladder u1(S[0], w1,X[0], Y[0], Cin);
fulladder u2(S[1], w2,X[1], Y[1], w1);
fulladder u3(S[2], w3,X[2], Y[2], w2);
fulladder u4(S[3], Cout,X[3], Y[3], w3);
endmodule
module fulladder(S, Co, X, Y, Ci);
input X, Y, Ci;
output S, Co;
wire w1,w2,w3;
//Structural code for one bit full adder 
xor G1(wl, X, Y);
xor G2(S, w1, Ci);
and G3(w2, w1, Ci);
and G4(w3, X, Y);
or  G5(Co, w2, w3);
endmodule
```
OUTPUT:

RIPPLE_CARRY_Adder(4-BIT)(Simulation):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/01ba36d7-266c-42ca-b1fc-88ef2507058c)

RIPPLE_CARRY_Adder(4-BIT)(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/2a8e9170-9bfe-466c-a8fa-86441302b609)

#7:-
RIPPLE_CARRY_ADDER(8-BIT):-
```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
module rippe_adder(S,Cout,X,Y,Cin);
input [7:0] X,Y;
input Cin;
output [7:0] S;
output Cout;
wire w1,w2,w3,w4,w5,w6,w7;
fulladder u1(S[0],w1,X[0],Y[0],Cin);
fulladder u2(S[1],w2,X[1],Y[1],w1);
fulladder u3(S[2],w3,X[2],Y[2],w2);
fulladder u4(S[3],w4,X[3],Y[3],w3);
fulladder u5(S[4],w5,X[4],Y[4],w4);
fulladder u6(S[5],w6,X[5],Y[5],w5);
fulladder u7(S[6],w7,X[6],Y[6],w6);
fulladder u8(S[7],Cout,X[7],Y[7],w7);
endmodule

module fulladder(S,CO,X,Y,Ci);
input X,Y,Ci;
output S,CO;
wire w1,w2,w3;
xor G1(w1,X,Y);
xor G2(S,w1,Ci);
and G3(w2,X,Ci);
and G4(w3,X,Y);
or G5(CO,w3,w3);
endmodule
```
OUTPUT:

RIPPLE_CARRY_Adder(8-BIT)(Simulation):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/3e145895-0938-462c-84e3-8f5ccc05342b)

RIPPLE_CARRY_Adder(8-BIT)(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/65a69b7f-d91d-4e0f-a4b8-17f5d8f0ee86)

RESULT: Simulation and synthesis of Logic Gates,Adders and Subtractor are succesfully verified using Vivado Software
