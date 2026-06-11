# task-1
to adjust the brightness of an led using a potentiometer

Code :
int potPin = A0;
int ledPin = 9;

void setup()
{
  pinMode(ledPin, OUTPUT);
}

void loop()
{
  int potValue = analogRead(potPin);

  int brightness;

  if (potValue <= 511)
  {
    brightness = map(potValue, 0, 511, 0, 255);
  }
  else
  {
    brightness = map(potValue, 512, 1023, 255, 0);
  }

  analogWrite(ledPin, brightness);
}
