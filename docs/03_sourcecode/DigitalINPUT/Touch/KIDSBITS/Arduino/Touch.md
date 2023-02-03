# KidsBits Touch

R11ケーブルで簡単接続。KidsBits Touchは、接触を感知すると信号は、ローからハイに変わります。

##Arduino

KidsBits Touchを4ピンに、LEDピンを２ピンのそれぞれ接続します。基板を接触したのを感知するとLEDが光ます。

```cpp
#define LEDPIN  2
#define PIN 4

void setup() {
  pinMode(LEDPIN,OUTPUT);
  pinMode(TILTPIN,INPUT);
}

void loop() {
  if (digitalRead(TILTPIN) == 0){
    digitalWrite(LEDPIN,LOW);
    }else{
    digitalWrite(LEDPIN,HIGH);
      }
}

```
