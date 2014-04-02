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


The functionality was demonstrated to Captain Silva on Wednesday, April 02.
#Troubleshooting
