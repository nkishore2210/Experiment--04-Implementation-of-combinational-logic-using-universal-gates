# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: Kishore.N
RegisterNumber:  22008365
*/
Program 1:
module expfour(a,b,c,d,f);

input a,b,c,d;

output f;

wire f1,f2,f3;

assign f1 = (~c&~b&~a);

assign f2 = (~d&~c&~a);

assign f3 = (c&~(~b)&~a);

assign f= f1&~f2&~f3;

endmodule
Program 2:
module expfourtwo(a,b,c,d,f);

input a,b,c,d;

output f;

wire f1,f2,f3,f4;

assign f1 = c&(~b)&a;

assign f2 = d&(~c)&a;

assign f3 = c&(~b)&a;

assign f4 = ~(f1|f2|f3);

not(f,f4);

endmodule

## Output:
RTL:
![image](https://user-images.githubusercontent.com/118707090/214316228-afc24258-bb2e-4658-a0e9-ab7695331009.png)
![image](https://user-images.githubusercontent.com/118707090/214316288-f8a5cb68-7b21-4ff3-895e-757be84bc10f.png)

Truth table:
![image](https://user-images.githubusercontent.com/118707090/214316398-1d489d4c-223a-4514-9602-fcefbc5a39aa.png)
![image](https://user-images.githubusercontent.com/118707090/214316471-a510fbaa-f790-4fb6-b057-6dece2146017.png)

Waveform:
![image](https://user-images.githubusercontent.com/118707090/214316549-2ddb8609-cce9-439d-9b5f-6b74ccd40caf.png)
![image](https://user-images.githubusercontent.com/118707090/214316574-d9c214f7-5322-48f1-a683-c8531092ac1b.png)



## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
