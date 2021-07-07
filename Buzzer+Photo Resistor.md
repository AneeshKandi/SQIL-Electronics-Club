## Problem Statement

In this project, we use the Photo resistor to check the brightness of the room. We will be informed by the buzzer if the room becomes dark.

## Schematics

![image](https://user-images.githubusercontent.com/85028192/124812711-97790c80-df81-11eb-91ad-b120c5774daf.png)

## Code

1. Defining a variable 'lightread' to store the values of the photo resistor.
```
int lightread = 0;
```
2. Now let's configure pin number 12 as OUTPUT and pin 'A0' as INPUT. Pin 'A0' is an Analog Pin using which we can use for analog devices. After that we initiate the **Serial Monitor** with a baud rate of 9600.
```
void setup()
{
  pinMode(12, OUTPUT);
  pinMode(A0, INPUT);
  Serial.begin(9600);
}
```
3. Now we begin the void loop() here. We use analogRead() function to get the analog readings of the photo resistor and we print it on the serial monitor.
```
void loop()
{
  lightread = analogRead(A0);
  Serial.println(lightread);
```
4. Now we use an if statement again. Using the serial monitor we found that the analog values for the photo resistor vary from 6(dark) - 670(light). If the 'lightread' value is less than or equal to six, then it implies that the room has gone dark and it's time to ring the buzzer!
```
if (lightread<=6)
  {
  	tone(12,440,300);
  	delay(500);
  	tone(12,400,300);
  	delay(500);
  }
```

## Tinkercad simulation

https://www.tinkercad.com/things/1QvpvPMIIt8

## Bonus!

You can add an LED or some other component and modify this project!
