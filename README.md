ECE281_Lab3
===========

Lab 3

The schematic to the nexys2_top_shelf is below (multiple copies were uploaded with different names. Github was denying my requsts to upload. However, github actually allowed the uploads to occur resulting in multiple copies):

![Scehmatic] (https://raw.github.com/John-Rios/ECE281_Lab3/master/PreLab3_Schematic_Rios.jpg)

Inputs: btw(3:0) / clk_50m / switch(7:0)
Internal Inputs: btw(3:0) which inputs nibble(0:3) to nibble_to_sseg / clk which is an input to nexys2_sseg and clk_div / sseg(0:3) which is an input to the nexys2_sseg / reset which is an input to nexys2_sseg

Outputs: SSEG_AN(3:0), SSEG(7:0), and LED(7:0)
internal outputs: nibble_to_sseg outputs sseg(0:3) to the nexys2_sseg / the nexys2_sseg outputs select to SSEG_AN(3:0) and sseg to SSEG(7:0) / clk_div outputs clkbus_sig(26downto19) to LED(7:0)

What does the code do? Eventually the program will control and track dual elevators. The LEDs will show which floor they are on. I am still unsure of the detailed functionality of this lab.

I changed four lines of code to correct syntax errors. Below is a description of the code changes made for the prelab:

Bad code:

nibble0 <= 
nibble1 <= 
nibble2 <= 
nibble3 <= 

Good Code: 

nibble0 <= "0000",
nibble1 <= "0000",
nibble2 <= "0000",
nibble3 <= "0000";

The bad code ahad undeclared signals/inputs. I corrected this error by assigning nibble(0:3) values of zero until I know what values they should be. Doing this prevented all syntax errors. I looked through the code of the nexys2_top_shell and did not spot any other immediate coding errors for the pre-lab.

