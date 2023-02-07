# KidsBits Potetionmeter

R11ケーブルで簡単接続。A0ポートに接続します。LEDはGP2と接続します。

##Arduino

```cpp
#define anglePin A0
#define ledPin 2

void setup() {
  pinMode(anglePin, INPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(115200);
}

void loop() {
  int angleValue = analogRead(anglePin);
  int outputValue = map(angleValue, 0, 1023, 0, 255);
  Serial.println(angleValue);
  analogWrite(ledPin, outputValue);
  delay(1);
}
```
