1.
The opcode for mystery1.bin is 0001, which represents EOR. EOR returns 1 for each individual bit that differs. The Rd in the program is 0000, so the result is stored in register 0. Furthermore x and y are stored in register 1 and 2 respectively. In this program, it is helpful to first convert the input numbers to binary, then identify which bits differ. If the bits differ, than the program returns a 1 in that position. (x^y)

	Ex. 
            x=1 y = 2
	0001^0010 = 0011
	Values in position 0 and 1 are different so 1 is returned in those positions, resulting in 3.

	Ex.
	x=1, y=1
         	0001^0001 = 0000
	Since no bits differ, the answer is 0.

	Ex.
	x=5, y=1
	0101^0001 = 0100
  Bit in position 2 differs, so 1 is returned that position. The result is 4.


The opcode for mystery2.bin is 0000, which represents AND. AND returns 1 if both bits are 1. The Rd in the program is 0000, so the result is stored in register 0. Furthermore x and y are stored in register 1 and 2 respectively. First, convert input numbers to binary, then identify which bits are the same and are both 1. If they are both 1, then the program returns 1 in that position. (x&y)

  Ex. 
  x=0,y=0
  0000&0000 = 0
  All bits are the same, but none equal 1. The answer is 0.

  Ex. 
  x=1, y=2
  0001&0010 = 0
  All bits differ, so the answer is 0.

  Ex.
  x=5, y=1
  0101&0001 = 0001
  Only bits in the first position are the same and equal 1, so result is 1.


There are two lines of instruction in mystery3.bin. The first line has an opcode of 000,
which is multiply. The first line multiplies the values in register 1 and 2 and stores it in
register 3. The second line has an opcode of 0100, which is add. The second line of
instruction adds the values in register 2 and register 3 and stores it in Rd, which is 0000.
(x*y + y)

  Ex. 
  x=1,y=1
  x*y = 1*1=1 -----> store value in register 3
  x*y + y = 1+1 = 2  -----> adds value in register 3 to register 2 
	The value in register 0 is 2.

	Ex.
	x=2,y=5
	x*y = 5*2 = 10 ---------> value in register 0 is 10
	x*y + y = 10+5 = 15 
	The value in register 0 is 15.

	Ex. 
  x=0, y=10
  x*y = 0*10 = 0  ---------> value in register 3 is 0
  x*y + y = 0 + 10 = 10
  The value in register 0 is 10.


	
2.
Because we do not want a file of binary numbers, we must convert the instructions into exactly 4 bytes with a specific order and format. First, we need to reverse the whole 32 bits because the computer reads the machine language from right to left order. Then we reverse again, this time one on each byte because we want the instruction to be in little-endian order. This is because ARM prefers using little-endian order.


3.
If we wanted to change the operand to something other than r1, in binary, positions 8-11 would change. This is because the binary instruction for register 1 and another register is different. So, if we were to change from register 1 to another register, the binary representation would change as well. 

	
	

