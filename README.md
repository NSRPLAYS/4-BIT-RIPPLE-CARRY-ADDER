# 4-BIT-RIPPLE-CARRY-ADDER
###  AIM:
 To implement a 4-bit Ripple Carry Adder using Verilog and validate its functionality by observing the sum and carry-out values.
### PROCEDURE:

1. Set up the Verilog environment (e.g., Quartus).
2. Write the Verilog code for a Full Adder module.
3. Use Full Adders to construct the 4-bit Ripple Carry Adder.
4. Simulate the design using a testbench to validate the outputs.
```
Devoloped by: B.Naveen sairam
Register no: 212224240103
```
```
module workshop (
    input [3:0] A, B,      
    input Cin,             
    output [3:0] Sum,      
    output Cout
);

    wire C1, C2, C3;      

    // Instantiate 4 full adders
    full_adder FA0 (A[0], B[0], Cin, Sum[0], C1);  
    full_adder FA1 (A[1], B[1], C1, Sum[1], C2);
    full_adder FA2 (A[2], B[2], C2, Sum[2], C3);
    full_adder FA3 (A[3], B[3], C3, Sum[3], Cout); 

endmodule 

module full_adder (
    input A, B, Cin,      
    output Sum, Cout       
);

    assign Sum = A ^ B ^ Cin;    
    assign Cout = (A & B) | (Cin & (A ^ B)); // Cout = (A ⋅ B) + (Cin ⋅ (A ⊕ B))

endmodule
```
### RTL schematic
![image](https://github.com/user-attachments/assets/9312f2a2-2acf-4fa0-a00c-b024d5d6d9d7)
### output timing waveform
![image](https://github.com/user-attachments/assets/d32c21fa-f192-4b5b-906a-7e4e0a4a25c6)
### Results
The Ripple Carry Adder was successfully implemented in Verilog. The simulation results showed the correct sum and carry-out values for various input combinations, confirming the functionality of the design.
