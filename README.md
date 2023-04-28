# Implementation-of-4x1-Mux-and-1x4-De-Mux-Using-Verilog-Programming-Language
FPGA Board (DIGILENT NEXYS 4) Artix - 7

## Mux
![image](https://user-images.githubusercontent.com/118730309/235054401-85ec7427-6f32-49ab-b4f6-ce55a9a87cad.png)

## Program Code:


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

![image](https://user-images.githubusercontent.com/118730309/235057659-0c8958f1-7ca5-4684-b94a-50f8ab822b26.png)




## Demux

![image](https://user-images.githubusercontent.com/118730309/235059302-49ef3c84-12e2-4483-87a6-de18ec14338b.png)



## Demux Program Code

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


## Timing Diagram

![image](https://user-images.githubusercontent.com/118730309/235059363-fa2021ae-50be-4ef5-9078-3515fe79b3b0.png)
  











