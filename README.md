# SA-2-MPMC
---
## AIM:
To Write an assembly language program in 8051 to generate a 250 ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5 continuously.
---
## APPARATUS REQUIRED:

- PERSONAL COMPUTER
- KEIL VISION

---
## ALGORITHM:

1. Start the program.
2. Set Port 0 as output.
3. Repeat the following steps forever:
Toggle (ON/OFF) the LED connected to P0.5.
Call the 250 ms delay subroutine.
4. In the delay subroutine:
Load register R2 = 4 (for 4 × 62.5 ms = 250 ms).
Set Timer 1 in Mode 1 (16-bit).
Load TH1 = 0BH, TL1 = 0DCH.
Start the timer.
Wait until the timer overflow flag (TF1) becomes 1.
Stop the timer and clear the flag.
Decrease R2 and repeat until it becomes zero.
Return to the main program.
5. The LED keeps blinking continuously every 250 ms.
---
## PROGRAM:





---

Would you like me to make this into a short flowchart (easy for lab record)?
