### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: Jeshwanth Kumar

RegisterNumber: 212223240114
*/

```
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```

**RTL LOGIC UP COUNTER**

![WhatsApp Image 2024-05-06 at 22 45 49_0d02a051](https://github.com/Jeshwanthkumarpayyavula/SYNCHRONOUS-UP-COUNTER/assets/145742402/d3654dd1-81e7-4347-9375-05982245cf58)


**TIMING DIAGRAM FOR IP COUNTER**


![WhatsApp Image 2024-05-06 at 22 44 59_fe80fa32](https://github.com/Jeshwanthkumarpayyavula/SYNCHRONOUS-UP-COUNTER/assets/145742402/ac7d0ad4-3a1a-4280-82e8-6e6d725c5dee)


**TRUTH TABLE**

![Screenshot 2024-05-06 142538](https://github.com/Jeshwanthkumarpayyavula/SYNCHRONOUS-UP-COUNTER/assets/145742402/542efc22-a108-4808-82da-39123cb03b5f)



**RESULTS**

Hence a 4 bit synchronous up counter is implemented correctly
