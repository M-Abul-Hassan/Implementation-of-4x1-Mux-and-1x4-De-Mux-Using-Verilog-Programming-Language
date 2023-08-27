# Implementation-of-4x1-Mux-and-1x4-De-Mux-Using-Verilog-Programming-Language
FPGA Board (DIGILENT NEXYS 4) Artix - 7

## Mux
![image](https://user-images.githubusercontent.com/118730309/235054401-85ec7427-6f32-49ab-b4f6-ce55a9a87cad.png)

## Program Code:


### Mux

module mux(Y,I0,I1,I2,I3,S0,S1);  <br>
input I0,I1,I2,I3,S0,S1;   <br>
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

![image](https://user-images.githubusercontent.com/118730309/235057659-0c8958f1-7ca5-4684-b94a-50f8ab822b26.png)

## Setting for hardware input output

![image](https://user-images.githubusercontent.com/118730309/235061810-011fea75-8dc3-4204-99ab-523773575ae4.png)



## Demux

![image](https://user-images.githubusercontent.com/118730309/235059302-49ef3c84-12e2-4483-87a6-de18ec14338b.png)



## Demux Program Code
### DeMux
module Demux(I0,I1,I2,I3,Y,S0,S1);  
input Y,S0,S1;  
output I0,I1,I2,I3;  

reg I0,I1,I2,I3;  
always@(*)  
begin  
case({S0,S1})  
2'd0:{I0,I1,I2,I3}={Y,3'd0};  
2'd1:{I0,I1,I2,I3}={1'd0,Y,2'd0};  
2'd2:{I0,I1,I2,I3}={2'd0,Y,1'd0};  
2'd3:{I0,I1,I2,I3}={3'd0,Y};  

default:$display("invalid");  
endcase  
end  
endmodule  

## Extra 1x8 demux code

module Demux_1x8(input Y, input [2:0] S, output [7:0] I);    
  reg [7:0] I;   
  
  always @(*) begin   
    case (S)   
      3'b000: I = {Y, 7'b0000000};   
      3'b001: I = {1'b0, Y, 6'b000000};   
      3'b010: I = {2'b00, Y, 5'b00000};   
      3'b011: I = {3'b000, Y, 4'b0000};   
      3'b100: I = {4'b0000, Y, 3'b000};   
      3'b101: I = {5'b00000, Y, 2'b00};   
      3'b110: I = {6'b000000, Y, 1'b0};   
      3'b111: I = {7'b0000000, Y};   
      default: I = 8'b0;   
    endcase   
  end   
endmodule   
  
 
## Timing Diagram 

![image](https://user-images.githubusercontent.com/118730309/235059363-fa2021ae-50be-4ef5-9078-3515fe79b3b0.png)
  




## Hardware Implementation On NEXYS 4(Artix-7 Power)

![WhatsApp Image 2023-04-28 at 10 20 23 AM](https://user-images.githubusercontent.com/118730309/235071152-9788071e-e3c3-446f-99a1-7b697cd8f40f.jpeg)


![WhatsApp Image 2023-04-28 at 10 21 01 AM](https://user-images.githubusercontent.com/118730309/235071377-4e738fb4-71b4-4cf2-89fd-8a3447b4f6ba.jpeg)


![WhatsApp Image 2023-04-28 at 10 21 48 AM](https://user-images.githubusercontent.com/118730309/235071399-e6bf4026-6721-47c2-8dad-f4cc418d9049.jpeg)







