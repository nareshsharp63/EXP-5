# Factorial-of-numbers

# FACTORIAL OF A NUMBER USING 8051 (Keil)

## AIM
To write and execute an Assembly language program to perform the factorial of a number using 8051 Keil.

---

## APPARATUS REQUIRED
- Personal computer with Keil software

---

## ALGORITHM
1. **Start**
2. **Input**: Read the number `n`.
3. **Initialize**:
   - Set factorial to `1`.
   - Set `i` to `1`.
4. **Loop**: While `i` is less than or equal to `n`:
   - Multiply factorial by `i`.
   - Increment `i` by `1`.
5. **Output**: Store or print the value of factorial.
6. **End**

---

## FLOWCHART
<img width="1199" height="1312" alt="WhatsApp Image 2026-11-17 at 2 28 15 PM" src="https://github.com/user-attachments/assets/dbcf84a3-7b55-41c0-925b-7f929134fbac" />


---

## PROGRAM
```ORG 0000H

MOV DPTR,#4500H
MOVx A,@DPTR
MOV R0,A

; 16-bit result = 0001H
MOV 30H,#01H     ; Low byte
MOV 31H,#00H     ; High byte

LOOP:

; ---- Multiply Low byte ----
MOV A,30H
MOV B,R0
MUL AB
MOV 32H,A        ; Save low result
MOV 33H,B        ; Save carry

; ---- Multiply High byte ----
MOV A,31H
MOV B,R0
MUL AB

ADD A,33H        ; Add carry
MOV 31H,A

MOV 30H,32H      ; Restore low byte

DJNZ R0,LOOP

; Store result
MOV DPTR,#4501H
MOV A,30H
MOVX @DPTR,A

INC DPTR
MOV A,31H
MOVX @DPTR,A

HERE: SJMP HERE
END
```
OUTPUT

(Keil output screenshot can be inserted here)

<img width="1900" height="1062" alt="Screenshot 2026-10-24 141117" src="https://github.com/user-attachments/assets/ead0eab0-fe48-4ec0-b2bc-194f5254f935" />


---
MANUAL CALCULATIONS

![WhatsApp Image 2026-02-26 at 08 16 46](https://github.com/user-attachments/assets/d8db3ada-9057-43fe-a613-2bc0e3cda750)


---

RESULT

Thus, the factorial of a number was calculated and executed successfully using 8051 Keil.

---
