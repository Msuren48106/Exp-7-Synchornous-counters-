```
Name: M.suren.
Reference Number: 23005055
```
# Exp-6 -Synchornous counters up counter and down counter 
### AIM: To implement 3 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

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

 
 

three-bit “Up” Counter
![dcount1](https://github.com/AshwinAkash24/Exp-7-Synchornous-counters-/assets/144979248/2d40c9c7-0838-413a-a5e7-8a43b105c118)


## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.

![dcount2](https://github.com/AshwinAkash24/Exp-7-Synchornous-counters-/assets/144979248/ba388b3e-cb2f-4301-a693-33674e7ce7a2)


3-bit Count Down Counter
### Procedure:
Step 1:Create a new project in Quartus2 software .
<br>
Step 2:Name the project as uc for upcounter and dc for down counter.
<br>
Step 3:Create a new verilog hdl file in the project file.
<br>
Step 4:Name the module declare as dc and uc for down counter and upcounter.
<br>
Step 5:Within the module declare input and output variables.
<br>
Step 6:Create a loop using if-else with condition parameter as reset.
<br>
Step 7:End the loop.
<br>
Step 8:End the module
### PROGRAM 
# UP COUNTER:
```
Module upcounter(clk,a);
input clk;
output reg[3:0];
always @(posedge clk)
begin
a[2]=(a[1]&a[0])^a[2];
a[1]=(a[0]^a[1]);
a[0]= ^a[0];
end
endmodule
```
# DOWN COUNTER:
```
Module downcounter(clk,a);
input clk;
output reg[3:0]a;
always @(posedge clk)
begin
a[2]=(~a[1]&~a[0])^a[2];
a[1]=(~a[0]^a[1]);
a[0]=1^a[0];
end
endmodule
```
### RTL LOGIC UP COUNTER AND DOWN COUNTER  
# UP COUNTER:
![image](https://github.com/AshwinAkash24/Exp-7-Synchornous-counters-/assets/144979248/100c0c6b-dd50-49dc-a74b-1a0e02732b23)

# DOWN COUNTER:
![image](https://github.com/AshwinAkash24/Exp-7-Synchornous-counters-/assets/144979248/2f3a9879-fa8c-4c70-9871-2882516dddd5)

### TRUTH TABLE 
# UP COUNTER:
![up](https://github.com/AshwinAkash24/Exp-7-Synchornous-counters-/assets/144979248/1f1b9b5e-f9e7-4b44-846c-e2e2882c2758)

# DOWN COUNTER:
![down](https://github.com/AshwinAkash24/Exp-7-Synchornous-counters-/assets/144979248/14915537-61b5-4e2f-8705-51b596d7c99b)

### TIMING DIGRAMS FOR COUNTER  
# UP COUNTER:
![counter](https://github.com/AshwinAkash24/Exp-7-Synchornous-counters-/assets/144979248/35e86bf8-065f-4b73-b7f5-a319d1ce8af4)

# DOWN COUNTER:
![counteras(1)](https://github.com/AshwinAkash24/Exp-7-Synchornous-counters-/assets/144979248/8ab81807-0053-469b-998a-cd14369a303f)

### RESULTS:
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different
logic gates are verified.
