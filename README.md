# Decode2
4300
Create the modules for the following:

1. Latch
   
2. Register File
  32 general purpose registers
  If regwrite == 1, then write the "writedata" value into the "write reg" location
  Else read the data from "read reg1" and "read reg2" as their respective "read data"

3. Control
  Follows the format
               Execution/Address Calculation Stage Control Line				Memory Access Stage Control Lines			WriteBack Control Lines
   Instruction	Reg Dst	ALU Op1	ALU Op0	ALU Src	                        Branch	MemRead	MemWrite	            RegWrite	MemToReg
   R-Format	   1	  1	          0	      0	                              0	      0	      0	                    1	        0
   LW          0	  0	          0       1	                              0	      1	      0	                    1           1
   SW	         X 	  0	          0	      1	                              0	      0	      1	                    0	        X
   BEQ	      X	  0	          1	      0	                              1	      0	      0	                    0	        X

4. Sign extend
   Receives 16 bit immediate values and outputs 32 bits sign extended

5. Final ID stage
