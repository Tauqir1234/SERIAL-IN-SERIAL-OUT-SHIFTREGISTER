# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

A Shift Register is a sequential logic circuit primarily used for storing and shifting data. It consists of a series of flip-flops (typically D Flip-Flops) connected in a chain, where the output of one flip-flop serves as the input to the next. Data is shifted one bit at a time, either to the left or right, depending on the configuration.

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**

1. Type the program in Quartus software.

2. Compile and run the program.

3. Generate the RTL schematic and save the logic diagram.

4. Create nodes for inputs and outputs to generate the timing diagram.

5. For different input combinations generate the timing diagram.

**PROGRAM**

Program for flipflops and verify its truth table in quartus using Verilog programming.

**Developed by: Tauqir Ahmed S**

**RegisterNumber: 24013512**

module Shift_Register(din, clk, rst, dout);

 input din;
 
 input clk;
 
 input rst;
 
 output dout;

reg dout;

reg [7:0]x;

always @ (posedge(clk) or posedge(rst)) begin

if (rst==1'b1)

begin


dout=8'hzz;

end

else

begin

x={x[6:0],din};

dout=x[7];

end

end

endmodule

**RTL LOGIC FOR SISO Shift Register**

![Screenshot 2024-12-17 190251](https://github.com/user-attachments/assets/9bf69b8b-6c64-43c4-8b21-c6a058e24354)


**TIMING DIGRAMS FOR SISO Shift Register**

![Screenshot 2024-12-17 190413](https://github.com/user-attachments/assets/d239302d-581c-4be6-9780-68e0eb3336ef)


**RESULTS**

The Shift Resgister was implemented successfully using Verilog, and its functionality was validated through simulation. The output matches the expected functional table of the Shift Register.
