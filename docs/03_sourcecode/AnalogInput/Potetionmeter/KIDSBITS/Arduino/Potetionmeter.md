# KidsBits Potetionmeter

R11ケーブルで簡単接続。A0ポートに接続します。LEDはGP2と接続します。

##Arduino

```c
#define anglePin A0
#define ledPin 2

void setup() {
  pinMode(anglePin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  int angleValue = analogRead(anglePin);
  int outputValue = map(angleValue, 0, 1023, 0, 255);
  analogWrite(ledPin, outputValue);
}
```
