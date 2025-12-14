AIM:

To implement SISO Shift Register using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

SISO shift Register

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next. Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

Procedure

/* write all the steps invloved */

PROGRAM
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming.


 Developed by: SYED RAASHID HUSAIN M


RegisterNumber: 25009038 */

module shift_register_3bit (
    input  wire clk,     // clock input
    input  wire rst,     // synchronous reset
    input  wire serial_in, // serial data input
    output reg  [2:0] q   // 3-bit register output
);

always @(posedge clk) begin
    if (rst)
        q <= 3'b000;          // reset all bits
    else
        q <= {q[1:0], serial_in}; // shift left
end

endmodule
```
RTL LOGIC FOR SISO Shift Register

[rtl.pdf](https://github.com/user-attachments/files/24151803/rtl.pdf)



TIMING DIGRAMS FOR SISO Shift Register wave.bmp

[wave.bmp](https://github.com/user-attachments/files/24151815/wave.bmp)


RESULTS

Thus,SISO Shift Register using verilog and validating their functionality using their functional tables has successful execution of the program.
