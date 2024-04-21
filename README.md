# VLSI-LAB-EXP-4
# SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

# AIM: 
To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using VIVADO

# APPARATUS REQUIRED:
VIVADO 2023.2

**LOGIC DIAGRAM**

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)


JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)


D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)


COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)


  
# PROCEDURE:
STEP:1  Start  the Xilinx navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.

# VERILOG CODE:

# SR FLIP FLOP:
end module SRFF(s, r, clk, rst, q);

input s, r, clk, rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({s, r})

2'b00:q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=1'bx;

end

end

endmodule

# JK FLIP FLOP:
module JKFF(j, k, clk, rst, q);

input j, k, clk, rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({j, k})

2'b00:q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=~q;

endcase

end

end

endmodule

# T FLIP FLOP:
module TFF(clk, rst, t, q);

input t, clk, rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

if(t==0)

q=q;

else

q=~q;

end

end

endmodule

# D FLIP FLOP:
module DFF(d, q, clk, rst);

input d, clk, rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

q=d;

end

endmodule

# MOD 10 COUNTER:
module mod_10(clk,rst,out);

input clk,rst;

output reg[3:0]out;

always@(posedge clk)

begin

if(rst==1|out==9)

out=4'b0;

else

out=out+1;

end

endmodule

# UPDOWN COUNTER:
module updown_counter(clk,rst,ud,out);

input clk,rst,ud;

output reg[3:0]out;

always@(posedge clk) begin if(rst==1) out=4'b0; else if (ud==1) out=out+1;

else if(ud==0) out=out-1;

end endmodule



# OUTPUT WAVEFORM:

# SR FLIP FLOP:

![image](https://github.com/yuva187/VLSI-LAB-EXP-4/assets/161815961/e8e3bcaa-1f8e-4e57-b5dc-ae99c93d5210)

# JK FLIP FLOP:

![image](https://github.com/yuva187/VLSI-LAB-EXP-4/assets/161815961/b361f4fc-8e7a-4c1d-be8f-819000e2b679)

# T FLIP FLOP:

![image](https://github.com/yuva187/VLSI-LAB-EXP-4/assets/161815961/ed8a35fc-6f25-4aae-a476-be1a04c4b811)

# D FLIP FLOP:

![image](https://github.com/yuva187/VLSI-LAB-EXP-4/assets/161815961/81ef5049-4082-4d5f-b409-a09669cc5d1a)

# MOD 10 COUNTER:

![image](https://github.com/yuva187/VLSI-LAB-EXP-4/assets/162670843/dc35f7ba-64c5-4f96-b432-627ab912e63c)

# UPDOWN COUNTER:
![image](https://github.com/yuva187/VLSI-LAB-EXP-4/assets/162670843/660ea516-e7e1-4cea-9cdb-4c457d164d7e)


# RESULT:
Thus, The FlipFlops and Counter are simulated and verified Successfully


