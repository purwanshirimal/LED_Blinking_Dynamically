## LED_Blinking_Dynamically

## COMPONENTS
1.Arduino UNO
2.a LED
3.220 ohm resistor
3.Jumperwires

## CONNECTIONS
A simple LED setup while the pin used for controlling is the pin 12.

## HOW IT WORKS
The programming is performed dynamically. As the time taken by the user to enter the number of blinks is not fixed, till no data is provided by the user no execution occurs due to the while loop. When the data is provided it is stored to the variable "mynum" and which then is used in a for loop for simple blinking project.

## CODE
int mynum;
int i;
String msg=" The number of blinks you want:  ";
void setup()
{
  pinMode(12,OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  Serial.println(msg);
  while(Serial.available()==0)
  {

  }
  mynum=Serial.parseInt();
  for(i=0;i<mynum;i++)
  {
  digitalWrite(12, HIGH);
  delay(500);
  digitalWrite(12,LOW);
  delay(500);
  }  

}

## CHALLENGES
As the time taken by user to provide the data isnot sure so when no data is available nothing is executed ie.a empty loop.

## FUTURE USE
It can be used to take data from the user and use it accordingly.
When the data is provided by the user again, the data is overwritten due to the last while loop using "Serial.read()" and hence no buffering occurs.
