# 1. Setting up LM50 temperature sensor
## _For this part, you need to set up an analog-to-digital converter (ADC). First, it is necessary to start this unit by searching on the Internet. Then do the following._

### Tasks
_1. According to the datasheet of the sensor, specify the parameters of the measurement range, sensitivity, accuracy, and power supply and output bases._

_2. Write a program that measures the temperature from -20 to 60 degrees Celsius with the highest possible accuracy and shows it on the screen with two decimal places. (The ADC reference voltage should be 5 volts)_

_3. What is the accuracy and resolution of the temperature measurement system you designed, and analyze whether these two parameters are limited to the sensor or to the microcontroller?_

***
1.

Measurement range: +125 to -40 degrees Celsius

Sensitivity: 10mV/°C

Accuracy: ±2 degrees Celsius

**Power and output bases:**

Vcc: 5 volts

GND: Ground

Vout: analog output that is connected to the ADC input of the microcontroller

2.

**Convert voltage to temperature:**

The output of LM50 is analog, which can be converted to temperature using the following equation:

$$V_out=10 mV/(°C) ×T°C+500mV$$

Therefore, the temperature (T) is calculated as follows:

$$T = (V_out-500mV)/(10mV/(°C))$$


### Microcontroller:
![image](https://github.com/user-attachments/assets/f8f03242-136c-4a2e-902d-b9648a0359b9)

### Proteus:
![image](https://github.com/user-attachments/assets/97ad6f90-c59e-4aac-ba70-b7ff14987607)

### Output:
![image](https://github.com/user-attachments/assets/87f25461-c8a9-4ef6-883e-257f31cf4fb4)
![image](https://github.com/user-attachments/assets/50cb9a87-94e1-4784-9071-a7450f7344fc)
![image](https://github.com/user-attachments/assets/b646db0d-9850-45e8-afc9-8659fe8e08b5)

3.
Microcontroller accuracy with 12 bits of data:

Our voltage range is 80 volts, which the microcontroller can display with 4096 bits.

$$80/4096= 0.01953125$$

This resolution value is greater than the resolution of the sensor, so we are limited by the sensor first and then by the microcontroller.

***
# 2. Setting up NTC thermistor 
### _First, try to find the voltage output of the sensor for different inputs (if necessary, you must implement the improvement circuits related to the sensor) and report it as a table lookup. Then, try to find the relationship between voltage and temperature with the help of cftool._
### _In the working range of the sensor, try to select an area that is relatively linear, and by changing the improvement circuit, make this area be mapped between 0 and 5 volts. Next, read this voltage with the help of the microcontroller and display the temperature with 2 decimal places on the LCD with the obtained relationship between voltage and temperature._

**Lookup Table:**

| Volt | 4.96 | 4.93 | 4.87 | 4.83 | 4.77 | 4.7  | 4.6  | 4.49 | 4.35 | 4.12 | 3.88 | 3.7  | 3.41 | 3.2  | 2.89 | 2.69 | 2.43 | 2.23 |
|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
| Temp | -50  | -40  | -30  | -25  | -20  | -15  | -10  | -5   | 0    | 7    | 13   | 17   | 23   | 27   | 33   | 37   | 42   | 46   |

| 2.04 | 1.81 | 1.6  | 1.42 | 1.25 | 1.1  | 0.89 | 0.74 | 0.64 | 0.53 | 0.44 | 0.35 | 0.27 | 0.21 | 0.17 |
|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
| 50   | 55   | 60   | 65   | 70   | 75   | 83   | 90   | 96   | 103  | 110  | 120  | 130  | 140  | 150  |


**Voltage diagram according to temperature:**
![image](https://github.com/user-attachments/assets/ad4dc0b2-b468-4cc1-8149-9601014778d9)

It is almost linear from 10 degrees to 70 degrees.

We need a non-inverting op-amp to be able to do the mapping:

![image](https://github.com/user-attachments/assets/576f90e3-5337-4834-a302-e17622cff580)

$$Av=1+R_2/R_1$$ 

The voltage at a temperature of 10 degrees is approximately 1.25 volts.

The voltage at a temperature of 70 degrees is almost 4 volts.

So:

$$Av=5/(4-1.25)=1+R_2/R_1 ⟹R_2/R_1 =  0.818181$$

$$R_1=10KΩ  ,   R_2=8.18181KΩ$$

Now we also need a differential op-amp to remove the DC offset and bring the voltage from 2 to 7 volts to 0 to 5 volts:

Final shape:

![image](https://github.com/user-attachments/assets/6119bb9d-cbb4-4de7-a29f-24f4a089468f)

**Output:**

![image](https://github.com/user-attachments/assets/d2143c69-d273-47c3-a898-cf073ba00ef5)
![image](https://github.com/user-attachments/assets/e01c7cbd-3027-4a65-a8d3-32d9b3b6b471)

***
