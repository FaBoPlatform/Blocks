# KidsBits Knock

R11ケーブルで簡単接続。振動を検知するセンサーです。

##Arduino

###衝撃を検知

Knockセンサーを４ピンに、LEDピンを２ピンのそれぞれ接続します。
衝撃をセンサーに与えるとピンがHIGH状態になり、その立ち上がりを検知し割り込みをしてLEDが１秒間だけ光るようにします。



```cpp
#define LEDPIN 2
#define KNOCKSENSERPIN 4

volatile int item;

void attachInterrupt_fun_3(){
    item = !item;
  }

void setup() {
  item = 0;
  pinMode(KNOCKSENSERPIN,INPUT);
  attachInterrupt(digitalPinToInterrupt(KNOCKSENSERPIN),attachInterrupt_fun_3,RISING);
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
