# KidsBits Reed

R11ケーブルで簡単接続。Reedセンサーに磁気が加わるとセンサーからの出力電圧がハイからローになります。
リレーと同じような働きをします。

##Arduino

Reedセンサーを４ピンに、LEDピンを２ピンのそれぞれ接続します。

```c
#define REEDPIN   2
#define LEDPIN    4

int value;

void setup() {
  value = 0;
  pinMode(REEDPIN,INPUT);
  pinMode(LEDPIN,OUTPUT);
}

void loop() {
  value = digitalRead(REEDPIN);
  if (value == 0){
    digitalWrite(LEDPIN,HIGH);
    }else{
    digitalWrite(LEDPIN,LOW);
      }
}

```
