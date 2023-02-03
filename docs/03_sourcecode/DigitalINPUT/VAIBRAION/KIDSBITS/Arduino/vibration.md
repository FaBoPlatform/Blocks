# KidsBits Vibration

R11ケーブルで簡単接続。

##Arduino

###振動検知

振動を検知すると1秒間LEDが光るようにします。
Vibrationセンサーを４ピンに、LEDピンを２ピンのそれぞれ接続します。

```cpp
#define LEDPIN 2
#define VAIBRATIONSENSERPIN 4

volatile int item;

void attachInterrupt_fun_3(){
    item = !item;
  }

void setup() {
  item = 0;
  pinMode(VAIBRATIONSENSERPIN,INPUT);
  attachInterrupt(digitalPinToInterrupt(VAIBRATIONSENSERPIN),attachInterrupt_fun_3,RISING);
  pinMode(LEDPIN,OUTPUT);
}

void loop() {
  if (!item){
    item = 1;
    digitalWrite(LEDPIN,HIGH);
    delay(1000);
    }
    digitalWrite(LEDPIN,LOW);
}

```
