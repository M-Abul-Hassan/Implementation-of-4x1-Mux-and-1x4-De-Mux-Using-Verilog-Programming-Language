# Implementation-of-4x1-Mux-and-1x4-De-Mux-Using-Verilog-Programming-Language
FPGA Board (DIGILENT NEXYS 4) Artix - 7

## Mux
![image](https://user-images.githubusercontent.com/118730309/235054401-85ec7427-6f32-49ab-b4f6-ce55a9a87cad.png)

## Program Code:

`timescale 1ns / 1ps
//////////////////////////////////////////////////////////////////////////////////
// Company: 
// Engineer: 
// 
// Create Date: 04/28/2023 09:19:53 AM
// Design Name: 
// Module Name: mux
// Project Name: 
// Target Devices: 
// Tool Versions: 
// Description: 
// 
// Dependencies: 
// 
// Revision:
// Revision 0.01 - File Created
// Additional Comments:
// 
//////////////////////////////////////////////////////////////////////////////////


module mux(Y,I0,I1,I2,I3,S0,S1);
input I0,I1,I2,I3,S0,S1;
output Y;
reg Y;
always@(*)
begin
case({S0,S1})
2'd0:Y=I0;
2'd1:Y=I1;
2'd2:Y=I2;
2'd3:Y=I3;
default:$display("invalid");
endcase
end
endmodule












## Timing diagram:

![image](https://user-images.githubusercontent.com/118730309/235056272-4ce60e02-e854-45fa-a10c-992cdee15fe8.png)
