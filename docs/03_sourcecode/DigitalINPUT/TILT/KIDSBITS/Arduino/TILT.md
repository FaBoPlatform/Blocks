# KidsBits TILT

R11ケーブルで簡単接続。KidsBits TILTは、傾斜を感知すると信号は、ハイからローに変わります。

##Arduino

KidsBits TILTを４ピンに、LEDピンを２ピンのそれぞれ接続します。傾斜を感知するとLEDが光ます。

```cpp
#define LEDPIN  2
#define TILTPIN 4

void setup() {
  pinMode(LEDPIN,OUTPUT);
  pinMode(TILTPIN,INPUT);
}

void loop() {
  if (digitalRead(TILTPIN) == 1){
    digitalWrite(LEDPIN,LOW);
    }else{
    digitalWrite(LEDPIN,HIGH);
      }
}

```
