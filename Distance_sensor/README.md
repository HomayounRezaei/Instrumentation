# Setting up the distance measuring sensor CNY70
## Tasks
**1. Start the sensor with a 5V power supply and set the voltage output between 0 and 10mm.**

**2. Fit the best possible curve using cftool and get its equation.**

**3. Write a program that displays the distance in millimeters with 2 decimal places on the LCD. Display in Proteus.**

**4. How accurate is your measurement?**

***

1.

![image](https://github.com/user-attachments/assets/0324d755-7d17-446c-94b8-61b976cb530e)

Now we get the voltage output between 0 and 10 mm:

| **Volt** | 0.1400 | 0.1600 | 0.1870 | 0.2600 | 0.6200 | 1 | 1.3800 | 1.7300 | 2.0600 | 2.3700 | 2.6700 | 2.9600 | 3.2400 | 3.5100 | 3.7700 | 4.0300 | 4.2800 | 4.5200 | 4.7600 | 5 |
|----------|--------|--------|--------|--------|--------|---|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
| **Distance** | 0.5000 | 1 | 1.5000 | 2 | 2.5000 | 3 | 3.5000 | 4 | 4.5000 | 5 | 5.5000 | 6 | 6.5000 | 7 | 7.5000 | 8 | 8.5000 | 9 | 9.5000 | 10 |

2.

![image](https://github.com/user-attachments/assets/a5aa56a9-1ccc-4d0c-ac14-fb1d56ce5d8e)

The equation and its coefficients are written on the lower right side of the image.

3.
We considered the working range of the sensor from 2 to 10 mm, because it is almost linear in this range.

![image](https://github.com/user-attachments/assets/1aaa9cad-40fd-4858-ab67-bb8efcb7a581)
![image](https://github.com/user-attachments/assets/054bc69d-cdd2-493c-9e5c-cd9f5cdee22e)

4.
The accuracy of our measurement is 0.01 because it is possible to display up to two decimal places.


