# Exp-6-Synchornous-counters - up counter and down counter 
## AIM: 
REF NO: 22008681 Name: A.Thiyagarajan

To implement 4 bit up and down counters and validate  functionality.
## HARDWARE REQUIRED:  
PC, Cyclone II , USB flasher
## SOFTWARE REQUIRED:  
Quartus prime
## THEORY 

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
## Procedure
1.Create module projectname(input ,output) to start the verilog programming. 
2.create a if loop condition to increase the count in counter_up function. 
3.Similarly, create another loop for the down counter.
4.End the verilog program using keyword endmodule. 
5.Get the timing diagram and RTL realization diagram for respective Counters.



## PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: A.Thiyagarajan
Register Number:  22008681


UP COUNTER

module upcount(clock,reset,up);
input clock,reset;
output reg[0:2] up;
always@(posedge clock or posedge reset)
begin
if(reset)
up=3'b 000;
else
up=up+1;
end
endmodule


DOWN COUNTER

module downcount(clock,reset,down);
input clock,reset;
output reg[2:0] down;
always@(posedge clock or posedge reset)
begin
if(reset)
down=3'b 111;
else
down=down-1;
end
endmodule

```




## RTL LOGIC UP COUNTER AND DOWN COUNTER  

### Up Counter
![up counter](https://user-images.githubusercontent.com/118707693/212560263-d12c10be-8a29-4d4b-8ea6-1735de5f4db6.png)



### Down Counter

![down counter](https://user-images.githubusercontent.com/118707693/212560273-b867e65c-39cc-4a50-aace-0372463cca62.png)


## TIMING DIGRAMS FOR COUNTER  

### Up Counter
![up counter td](https://user-images.githubusercontent.com/118707693/212560287-fec4ac61-3b6b-4654-9ee3-f23824abbbf4.png)


### Down Counter

![down counter td](https://user-images.githubusercontent.com/118707693/212560294-aa4cf631-8226-49d6-b671-0022384994f1.png)


## TRUTH TABLE 

### Up Counter

![up counter truth table](https://user-images.githubusercontent.com/118707693/212560303-90f15adb-b51f-4f97-8ba3-1ce1f177ea17.png)

### Down Counter

![down counter truth table](https://user-images.githubusercontent.com/118707693/212560315-12707cf8-7b14-4a78-8d4b-bdb58dc581f5.png)


## RESULTS 
Thus 3 bit up and down counters is implemented and its functionality is validated.
