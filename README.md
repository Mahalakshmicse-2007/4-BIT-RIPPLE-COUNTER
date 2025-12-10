# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */

**PROGRAM**
```
module asynchronouscounter (
    input clk,          // clock input
    input reset,        // asynchronous reset
    output [3:0] q      // 4-bit output
);

// Internal flip-flop register
reg [3:0] q_reg;

// Output assignment
assign q = q_reg;

// FF0 toggles with external clock
always @(posedge clk or posedge reset) begin
    if (reset)
        q_reg[0] <= 1'b0;
    else
        q_reg[0] <= ~q_reg[0];
end

// FF1 toggles with Q0
always @(posedge q_reg[0] or posedge reset) begin
    if (reset)
        q_reg[1] <= 1'b0;
    else
        q_reg[1] <= ~q_reg[1];
end

// FF2 toggles with Q1
always @(posedge q_reg[1] or posedge reset) begin
    if (reset)
        q_reg[2] <= 1'b0;
    else
        q_reg[2] <= ~q_reg[2];
end

// FF3 toggles with Q2
always @(posedge q_reg[2] or posedge reset) begin
    if (reset)
        q_reg[3] <= 1'b0;
    else
        q_reg[3] <= ~q_reg[3];
end

endmodule
```
/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

 Developed by:Mahalakshmi M RegisterNumber:25015887
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="760" height="833" alt="image" src="https://github.com/user-attachments/assets/a9145075-b6ca-489f-96e1-8f64eb448ed9" />

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="1328" height="282" alt="image" src="https://github.com/user-attachments/assets/3d57150d-dbd7-4e54-9f42-b4b2fc369b42" />

**RESULTS**
thus the  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables.
