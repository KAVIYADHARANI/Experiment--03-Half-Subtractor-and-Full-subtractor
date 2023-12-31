# NAME: KAVIYA D
# REGISTER NUMBER: 212223040089
# Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

# PROCEDURE
1.Use module projname(input,output) to start the Verilog programmming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.Use each output to represnt onre for differnce and the other for borrow.

5.End the verilog program using keyword endmodule

## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

# PROGRAM
```
module half_sub(a,b,borrow,diff);
input a,b;
output borrow,diff;
assign borrow=~a&b;
assign diff=a^b;
endmodule
```

## RTL REALIZATION
![image](https://github.com/KAVIYADHARANI/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870680/1254f111-67b3-4028-b701-9c470611a762)

## TRUTH TABLE
![image](https://github.com/KAVIYADHARANI/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870680/48d2e708-23ab-4631-81cd-75a6734ec1cb)

## TIMING DIAGRAM
![image](https://github.com/KAVIYADHARANI/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870680/85bf448b-ef09-42b4-bdbc-c23d6048c5f5)

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Program:
```
module full_sub(a,b,bin,borrow,diff);
input a,b,bin;
output diff,borrow;
assign diff=(a^b)^bin;
assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
endmodule
```

## RTL realization
![image](https://github.com/KAVIYADHARANI/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870680/49bb7bb3-d4dd-4169-b969-8218dc6b289c)

## Truthtable
![image](https://github.com/KAVIYADHARANI/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870680/a4aefa6c-b290-4832-9fac-832ae9e10d4b)

## Timing diagram
![image](https://github.com/KAVIYADHARANI/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870680/6500ffcc-1103-44a0-a6d2-0d1884f2d9d9)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
