ECE281_CE4
==========

#A
Below is the code for the first part of the A program.
```
    	   00	   7	LDAI	9	loads value 9	N	1	Y
		   01	   9				Y	0	N
		   02	   D	STA	B0	stores to B0	N	2	Y
```
The program loads the value 9 and then loads it to the location B0.
This is repeated for the other values and locations.
The program concludes in an infinite loop as seen below
```
Loop       0F	   9	JMP	Loop		N	2	Y
		   10	   F				Y	0	N
		   11	   0				Y	0	N
```
#B
B works by first inputing the 2's complent of 4, which is C. Then it adds the value in B0 two times, essentially adding it and doubling it. 
```
           00	   7	LDAI	C		N	1	Y
		   01	   C			subtracts 4	Y	0	N
		   02	   E	ADDD	B0	loads the input	N	2	Y
		   03	   0				Y	0	N
		   04	   B				Y	0	N
		   05	   E	ADDD	B0	doubles the output	N	2	Y
```		   
#C
The C functionality works by first loading the number that is being input to port 3. Then it outputs this number to port 0. Then it subtracts 1 by adding F (the two's complement of 1) and outputs the result to port 1. This process is then repeated and the result is output to port 2. Then 1 is added to the number and the loop goes to the output to port 0, essentially subtracting 1 fromt the initial input. 
```
           00	   5	IN	3	loads input from port 3	N	1	Y
		   01	   3				Y	0	N
	Loop   02	   4	OUT	0	outputs to port 0	N	1	Y
		   03	   0				Y	0	N
		   04	   6	ADDI	F	adds -1	N	1	Y
		   05	   F				Y	0	N
		   06	   4	OUT	1	outputs to port 1	N	1	Y
		   07	   1				Y	0	N
		   08	   6	ADDI	F	adds -1	N	1	Y
		   09	   F				Y	0	N
		   0A	   4	OUT	2	outputs to port 2	N	1	Y
		   0B	   2				Y	0	N
		   0C	   6	ADDI	1	adds 1	N	1	Y
		   0D	   1				Y	0	N
		   0E	   9	JMP	Loop	loops to output port 0	N	2	Y
		   0F	   2				Y	0	N
		   10	   0				Y	0	N
```		   

The functionality was demonstrated to Captain Silva on Wednesday, April 02.
#Troubleshooting
It took me a while to figure out the hex value for negative 4 (C). By doing this, my B program was shortened to the desired length. 
