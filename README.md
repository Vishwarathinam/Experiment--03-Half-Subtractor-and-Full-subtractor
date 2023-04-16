### Experiment--03-Half-Subtractor-and-Full-subtractor
### Implementation-of-Half-subtractor-and-Full-subtractor-circuit
### AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

### Equipments Required:
### Hardware – PCs, Cyclone II , USB flasher
### Software – Quartus prime
### Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

### Half Subtractor Full Subtractor
### Half Subtractor:
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

### Full Subtractor:
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

### Procedure:

Write the detailed procedure here 


### Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Vishwa Rathinam S
RegisterNumber:  212221240063
### Half Subtractor:
```
module halfsub(A,B,diff,barrow);
input A,B;
output diff,barrow;
wire x;
xor(diff,A,B);
not(x,A);
and(barrow,x,B);

endmodule
```
### Full Subtractor:
```
module fullsub(A,B,C,diff,barrow);
input A,B,C;
output diff,barrow;
assign diff = A ^ B ^ C;
assign barrow = ~A & (B^C) | B & C;
endmodule
```
*/

### Output:

### Truthtable
Half Subtractor:
![truthsub](https://user-images.githubusercontent.com/95266350/232325243-64fdc80f-52ca-409b-beb2-fac2f32c627e.jpg)


Full Subtractor:
![truthfull (1)](https://user-images.githubusercontent.com/95266350/232325250-a55d6917-e1fe-43d0-a4d7-8d0ddc84e586.jpg)


###  RTL realization
Half Subtractor:
![halfrtl](https://user-images.githubusercontent.com/95266350/232325257-0f7f6519-9de5-4aa8-a93c-8ff6ae48c524.jpg)

Full Subtractor:
![fullrtl](https://user-images.githubusercontent.com/95266350/232325268-4daf1837-c225-4a34-9811-188a91f71d00.jpg)


### Timing diagram 
Half Subtractor:
![timehalf (1)](https://user-images.githubusercontent.com/95266350/232325274-922581da-86e0-4b9d-aa5e-cb5f34777be6.jpg)

Full Subtractor:
![timefull (1)](https://user-images.githubusercontent.com/95266350/232325276-cc7e439e-ce76-452a-8178-5bd4bf4a9ded.jpg)

### Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
