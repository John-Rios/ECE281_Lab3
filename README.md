ECE281_Lab3
===========

Lab 3
------------------------------------------------------------------------------
Pre-Lab:

The schematic to the nexys2_top_shelf is below (multiple copies were uploaded with different names. Github was denying my requsts to upload. However, github actually allowed the uploads to occur resulting in multiple copies):

![Scehmatic] (https://raw.github.com/John-Rios/ECE281_Lab3/master/PreLab3_Schematic.jpg)

Inputs: btw(3:0) / clk_50m / switch(7:0)
Internal Inputs: btw(3:0) which inputs nibble(0:3) to nibble_to_sseg / clk which is an input to nexys2_sseg and clk_div / sseg(0:3) which is an input to the nexys2_sseg / reset which is an input to nexys2_sseg

Outputs: SSEG_AN(3:0), SSEG(7:0), and LED(7:0)
internal outputs: nibble_to_sseg outputs sseg(0:3) to the nexys2_sseg / the nexys2_sseg outputs select to SSEG_AN(3:0) and sseg to SSEG(7:0) / clk_div outputs clkbus_sig(26downto19) to LED(7:0)

What does the code do? A functionality will control dual elevators and the LEDs will move in the direction of the moving elevator. B functionality will have 8 floors where the elevator either moves to only prime numbered floors and displays the number or allows the user to input a desired floor in binary for the elevator to move to. Required functionality is that the elevator moves between four floors with the use of a stop input and an up/down input. This functionality must be accomplished with both a moore machine and a mealy machine. The mealy machine must display the next floor. All functions must display the current floor. 
-------------------------------------------------------------------------------
Post Lab:

Errors/Debugging: The most common errors I ran into were simply syntax errors. These occured often as I re-coded and de-coded in order to accomplish and perform a single required functionality. Most syntax errors were identified for me through the syntax check function. However, one that took a while to correct was when I switched from mealy functionality to moore functionality. When I switched I copied and pasted most of the code as it was very similar. In doing so I forgot to adjust the names of the component declarations and the instantioations. This was a simple error but caused me to spend a good amount of time attempting to correct it. Another error I ran into was that I forgot to display the future floor number for the mealy machine functionality. fortunately this was a quick fix. the next state was already a variable being processed so all I had to do was display that value onto another LED sseg display. Originally I struggled to code for the functionality of the floor select function. I created a standard vector to take in the value of the 3bit floor select input but I was unsure of how to use it to control the elevator. Originally I attempted making a loop that would solve for the difference between the current floor and desired floor and then instruct the elevator to move that many floors. However, this was complicated and did not work out well. Eventually I decided that I could use the code I had with only minor adjsutments where the elevator would compare floors to the three bit input. The elevator would constantly move by comparing the floor select 3bit number to the current floor. When the floor select changed the floors would change aswell until they were equal. This solved my roblem. The most time consuming problem I had occured with git hub. Git hub would not allow me to update files so I had to upload the nexys shell and the moore shell, which were updated for more functionality, with different names. Originally git hub would simply not allow me to upload. After much research with no solution found, I decided to simply change the names. I ran into troubles with github in the prelab as well. 

-All .bit files were uploaded which demonstrate the functionalities that were accomplished in this lab. 
-------------------------------------------------------------------------------
Code Critique:

(Moore Shell) 




