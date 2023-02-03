# KidsBits Button

R11ケーブルで簡単接続。KidsBitsButtonは、ボタン押すと接続、離すと切断されるタクトスイッチです。

##Arduino

KidsBits Buttonを４ピンに、LEDピンを２ピンのそれぞれ接続します。ボタンを押すと、Lowの状態になり、ボタンを離すとHIGHの状態になります。

```cpp
#define ledPin 2
#define buttonPin 4

void setup() {
  pinMode(buttonPin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop(){
  int buttonState  = digitalRead(buttonPin);
  if (buttonState == HIGH) {
    digitalWrite(ledPin, LOW);
  }
  else {
    digitalWrite(ledPin, HIGH);
  }
}

```
