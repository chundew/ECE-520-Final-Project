# ECE-520-Final-Project

This project is a demonstration of how to use a Pmod LED (8) and a Pmod Switches (4) to show a binary counter. In order to begin this experiment, I first had to understand what Pmods are and how they work. Pmod's are a Digilent made line of products that work with microprocessors and FPGA boards. They are easy to use attachments that are relatively affordable and are well documented. The data sheets of the Pmods and the FPGA board are all that are needed to map the pins. After having a decent understanding of what I must do, I began my creating a module. I decided to write my code in verilog since I had created a counter beforehand. My module was filled with two inputs: one of single bit size for clock and one of 8 bit size for the switches. I also added 3 output registers: one of 8 bit size for the pmod leds, one of 7 bit size for the segments, and one of one bit size for the digit select. The digit select would determine which digit is being lit up when logic is 0 for the right digit or 1 for the left digit. I used these inputs and outputs for connecting the pmods to the fpga board. I then instantiated a case where all the numbers from 0 - 15 are displayed on the ssd. Numbers 10 - 15 are displayed in hexadecimal.

After creating my module, I was able to test it by first generating synthesis. I ran the synthesis to make sure that there are no errors and so that I can map my inputs and outputs. After assigning the inputs as stated in the data sheets of my Pmods and my Zybo Z7 10 board, I ran the implementation. Implementation will only pass if all ports are mapped and there are no overlaps. If both synthesis and implementation pass and are updated to the newest module, then I can run bitstream generation. Bitstream generation will allow me to open the hardware manager where I can connect my FPGA board as well as program my board with the bit file generated. I was successfully able to connect my board and when I ran the program, the result was exactly as I had expected. The switches acted as binary digits with up being a ‘1’ and down being a ‘0.’ It counted all the way to 15 and I mapped the onboard switches to increase the amount of leds for future implementations.


Overall, this project was pretty fun to do. Although it was unfortunate that I was unable to get my 00 to 99 counter to function originally, I was able to practice i/o mapping and get a successful binary counter using external leds and switches. Future iterations to this project can be made by fixing my binary counter, and adding more switches/leds for higher binary bits.

[Github Repository Pmod: LED/Switch](https://github.com/chundew/ECE-520-Final-Project)


![My Module](/images/Design_Code.png)

![Physical Model](/images/Design_Pic.png)

![Zybo](/images/zybo.png)

![Constraints Part 1](/images/xdc_p1.png)

![Constraints Part 2](/images/xdc_p2.png)