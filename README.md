# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: 
To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED: 
PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:  
Quartus prime
### THEORY:
## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### PROCEDURE
1. Open a new project using Quartus II.
2. Declare the inputs and outputs inside module projname().
3. Set the reset value using register.
4. Use commands like begin and end to stimulate the counter.
5. For Up counter increment the count and for Down counter decrement the count.
6. End the verilog programming.

### PROGRAM (UP COUNTER)
```
Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by: Harini.B
RegisterNumber: 212221230035 

module de06(input clk,input reset,output[0:3]counter);
reg[0:3]counter_up;
always@(posedge clk or posedge reset)
begin
if (reset)
counter_up<=4'd0;
else 
counter_up<=counter_up+4'd1;
end
assign counter=counter_up;
endmodule
```
### RTL LOGIC (UP COUNTER)
![de06up](https://user-images.githubusercontent.com/93427253/169737903-7df02767-aa31-4226-abe7-d31f558853fe.png)
### TIMING DIAGRAM (UP COUNTER)
![de06re0](https://user-images.githubusercontent.com/93427253/169737973-5972c90c-6ced-45e6-9f62-8d72761fb155.png)
![DEUP1](https://user-images.githubusercontent.com/93427253/169740913-103b6498-3438-4417-821a-6e755845225e.png)
### TRUTH TABLE(UP COUNTER)
![UPCOUNTER](https://user-images.githubusercontent.com/93427253/169741491-56781ab6-e7e7-4202-8051-b2a8b5f40021.png)

### PROGRAM (DOWN COUNTER)
```
Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by: Harini.B
RegisterNumber: 212221230035 

module de06(input clk,input reset,output[0:3]counter);
reg[0:3]counter_down;
always@(posedge clk or posedge reset)
begin
if (reset)
counter_down<=4'd0;
else 
counter_down<=counter_down-4'd1;
end
assign counter=counter_down;
endmodule
```
### RTL LOGIC (DOWN COUNTER)
![de06down](https://user-images.githubusercontent.com/93427253/169740256-e2395463-943a-4248-b148-cd39ec4abe6a.png)
### TIMING DIAGRAM (DOWN COUNTER)
![dedown0](https://user-images.githubusercontent.com/93427253/169741443-684ebfb9-32cf-484a-b1b7-16deb4d6ce67.png)
![DEDOWN1](https://user-images.githubusercontent.com/93427253/169740869-f096a2d5-e108-4858-9f60-3271497ee37b.png)
### TRUTH TABLE(DOWN COUNTER)
![DOWNCOUNTER](https://user-images.githubusercontent.com/93427253/169741521-c866ed18-c598-4012-a815-ec20fd6ffca4.png)

### RESULTS 
Hence the Four bit Up counter and Down counter is implemented successfully and its functionality is validated.
