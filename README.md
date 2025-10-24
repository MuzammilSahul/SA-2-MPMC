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
```asm
ORG 0000H
MAIN:   MOV P0, #00H        
AGAIN:  CPL P0.5            
        ACALL DELAY_250MS   
        SJMP AGAIN           
DELAY_250MS:
        MOV R2, #04          
NEXT_DELAY:
        MOV TMOD, #10H       
        MOV TH1, #0BH        
        MOV TL1, #0DCH       
        SETB TR1             

WAIT1:  JNB TF1, WAIT1       
        CLR TR1              
        CLR TF1            

        DJNZ R2, NEXT_DELAY  
        RET

END
```
---

## OUTPUT

## PROGRAM:

<img width="968" height="551" alt="Screenshot 2025-10-24 221248" src="https://github.com/user-attachments/assets/d2d65fa0-35a9-4caa-a943-af41f11631dd" />

## PERIPHERAL(PORT 0 AFTER DEBUGGING):
<img width="968" height="551" alt="Screenshot 2025-10-24 221248" src="https://github.com/user-attachments/assets/39f59dd7-64a9-4c9d-a5af-c30aeed724bf" />

## LED TOGGLING AT P0.5 AT 250MS:
# ON

<img width="830" height="797" alt="Screenshot 2025-10-24 221522" src="https://github.com/user-attachments/assets/5c8fa3b0-39dd-4d04-92fd-1a2ea7f65771" />

# OFF
<img width="1140" height="800" alt="Screenshot 2025-10-24 221649" src="https://github.com/user-attachments/assets/275d65ff-bcb8-47b5-97db-316186ce4c29" />

### YOU CAN SEE THE LED IS TOGGLING AT 250MS

---
## RESULT:

Thus The Program to generate a 250ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5 continuously is done and output is shown


Would you like me to make this into a short flowchart (easy for lab record)?
