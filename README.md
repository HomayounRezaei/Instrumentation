# 1. Digital input and output
* On PORTA, define $$X_1$$, $$X_2$$ pins as digital output as follows.
* * X1=SID%5 
* * X2=SID%5+7 
* * that the SID is the student number and % is the remaining operator.
* Connect a green LED and a red LED to the above pins. It is necessary to consider the hardware in Observing the closing of the LED circuit. Implement the simplest possible circuit and explain why.
* Define $$Y_1$$ and $$Y_2$$ pins as digital inputs on PORTB as follows.
* * Y1=SID%3 
* * Y2=SID%2+4 
* Connect two push buttons whose output is Up Pull to the $$Y_1$$ and $$Y_2$$ bases.
## Task
Write a program that by pressing the push button corresponding to the base $$Y_1$$ , the green LED turns on and the red LED turns off, and by pressing the push button corresponding to the base $$Y_2$$, the green LED turns off and the red LED turns on.

***

**Microcontroller:**

![image](https://github.com/user-attachments/assets/3d73cf30-8bf8-43c9-b8a2-2186f0a69b12)

**Microcontroller in Proteus:**

![image](https://github.com/user-attachments/assets/a785a109-7b18-4a5b-971c-3ef037765a22)

By pressing the button $$Y_1$$ :

![image](https://github.com/user-attachments/assets/ef5fa027-7964-43ee-aa15-cf705385eb7b)

By pressing the button $$Y_2$$ :


As you can see, by pressing each $$Y_1$$ key, the green LED turns on and the red one turns off, and by pressing the $$Y_2$$ key, the red LED turns on and the green one turns off.


