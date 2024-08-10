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
## Tasks
Write a program that by pressing the push button corresponding to the base $$Y_1$$ , the green LED turns on and the red LED turns off, and by pressing the push button corresponding to the base $$Y_2$$, the green LED turns off and the red LED turns on.

Write a program that by pressing the push button corresponding to pin $$Y_1$$, first the green LED will blink 5 times with a time interval of 400 milliseconds, then the red LED will blink 2 times with a time interval of 100 milliseconds, and at the end, all 2 LEDs will light up. By pressing the push button corresponding to the $$Y_2$$ base, the same thing will happen in reverse for the LEDs, and in the end, both will turn off. Simulate the written program using Proteus.

***

**Microcontroller:**

![image](https://github.com/user-attachments/assets/3d73cf30-8bf8-43c9-b8a2-2186f0a69b12)

**Microcontroller in Proteus:**

![image](https://github.com/user-attachments/assets/a785a109-7b18-4a5b-971c-3ef037765a22)

By pressing the button $$Y_1$$ :

![image](https://github.com/user-attachments/assets/ef5fa027-7964-43ee-aa15-cf705385eb7b)

By pressing the button $$Y_2$$ :

![image](https://github.com/user-attachments/assets/2fb6fb19-08d5-496e-9ccf-099816d788a5)

As you can see, by pressing each $$Y_1$$ key, the green LED turns on and the red one turns off, and by pressing the $$Y_2$$ key, the red LED turns on and the green one turns off.

![image](https://github.com/user-attachments/assets/e6f20358-31f2-47cb-9eb2-cafe6a163261)

***

# 2. Connecting the display to the microcontroller 
The purpose of this section is to connect the 16x2 Alphanumeric LCD to port B of the microcontroller as shown below. Various libraries have been produced for this display.

![image](https://github.com/user-attachments/assets/a8c8b1cc-525d-4566-8081-96ce12fa4939)

i. By searching the internet, write a program that can be used in the first line of the name, and in the second line Display your student number. Simulate the written program using Proteus.

ii. Define 2 variables with arbitrary values, one int, and the other float, and write a program that displays an integer number on the first line of the LCD and a decimal number with 2 decimal places on the second line. Can you display decimal numbers on LCD? Find the solution by searching the internet. 

iii. Consider the previous question. Write a program that doubles all 2 variables every 1 second and displays them on the LCD. (x = 2*x) What do you see after the passage of time? Justify what is happening. In your opinion, how can larger numbers (for example, a 12-digit number) be displayed?

**Microcontroller in Proteus:**

![image](https://github.com/user-attachments/assets/c765fbdb-f3ef-4c00-a650-2974fb9407eb)

**Outputs:**

![image](https://github.com/user-attachments/assets/a8e1de2f-cfdd-4473-95c2-57d0ea8b7379)

![image](https://github.com/user-attachments/assets/40b7c84e-43c6-4c32-97b4-563c976eafcc)

With the itoa command, we convert the integer number to character and display it.

To convert the flute into our own character, we created a ftoa function and used it to display the flute number as a character.

With the itoa command, we convert the integer number into a character and display it as in the previous step.

To convert the flute into our own character, we created a ftoa function and used it to display the flute number as a character.

**Output:**
![image](https://github.com/user-attachments/assets/e567c737-3781-4641-b299-ac2c19cc1cc1)
