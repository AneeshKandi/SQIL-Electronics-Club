## Problem Statement

Controlling an external LED using a push/tactile button.

## Schematics

![image](https://user-images.githubusercontent.com/85028192/124806466-5c270f80-df7a-11eb-9814-67104d5e9db8.png)

## Code

1. Defining a variable buttonread which will be used to store the status of Push button. Then, using pinMode(), we configure pin number 10 as OUTPUT and pin number 4 as INPUT.
```
int buttonRead = 0;
void setup()
{
  pinMode(10, OUTPUT);
  pinMode(4, INPUT);
}
```
2. Using digitalRead(), we read the status of the push button and store it in the variable 'buttonread'.
```
buttonRead = digitalRead(4);
```
3. Now we use an if statement to check if the button is pressed or not. If buttonread is HIGH or logic 1, it means that button is pressed and the LED is switched ON for 5 seconds and then it gets switched off for next 5 seconds.
```
if (buttonRead == HIGH)
  {
  	digitalWrite(10, HIGH);
  	delay(500); // Wait for 500 millisecond(s)
  	digitalWrite(10, LOW);
  	delay(500); // Wait for 500 millisecond(s)
  }
```
This is the end of void loop(). After this, the loop starts again and it checks for the value of button read once again!

## Tinkercad simulation

https://www.tinkercad.com/things/dpIH6ylzDn7
