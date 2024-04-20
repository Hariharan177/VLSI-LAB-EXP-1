Simulate and Synthesis Logic Gates,Address and Subractors Using Vivado
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

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
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/f0464907-7284-4643-a349-6c38d5eb2801)

Full Adder(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/6984340f-f663-4a3f-b50e-f7e25408a86a)


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
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/66c47d7e-f7f8-425e-bd20-2b5b73e54900)

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
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/13cd7926-69c1-45fb-913d-9255510c0744)

Half Adder(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/446589ff-2579-4f91-a02b-2589a107f646)

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
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/39b4d06a-77ff-4198-a9d8-2ce5544a434e)

Logic Gates(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/7982845f-6733-4365-8536-625416745ddb)

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
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/2f2b91ce-bcad-4eb3-8c96-ab53c7817d4a)

RIPPLE_CARRY_Adder(4-BIT)(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/db6a9c7c-9fd1-4eba-a794-cd0c21ac3b96)

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
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/7492e6d9-6296-4667-8268-a65b69011873)

RIPPLE_CARRY_Adder(8-BIT)(Eloborated Design):
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-1/assets/164841000/65a69b7f-d91d-4e0f-a4b8-17f5d8f0ee86)
