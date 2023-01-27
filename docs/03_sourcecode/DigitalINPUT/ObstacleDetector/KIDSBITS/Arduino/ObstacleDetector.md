# KidsBits Obstacle Detecotr

R11ケーブルで簡単接続。赤外線をLEDで発光して、物体に反射した赤外線を受信して障害物を検知します。

##Arduino

###障害物を検知

ObjetctDetectorセンサーモジュールを２ピンに接続して、LEDを４ピンに接続します。

```c
#define SENSORPIN 2
#define LEDPIN    4

volatile int value;

void setup() {
  value = 0;
  pinMode(SENSORPIN,INPUT);
  pinMode(LEDPIN,OUTPUT);
}

void loop() {
  value = digitalRead(SENSORPIN);
  if (value == 0){
    digitalWrite(LEDPIN,HIGH);
  }
  if (value == 1){
    digitalWrite(LEDPIN,LOW);
    }
}

```
