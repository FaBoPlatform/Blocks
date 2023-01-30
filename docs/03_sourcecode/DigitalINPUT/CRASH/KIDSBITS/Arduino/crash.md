# KidsBits CRASH

R11ケーブルで簡単接続。

##Arduino

###衝突を検知

衝突を検知するとLEDが光るようにします。
CRASHセンサーを４ピンに、LEDピンを２ピンのそれぞれ接続します。

```c
#define LEDPIN 2
#define CRASHPIN 4

volatile int value;

void setup() {
  value = 0;
  pinMode(CRASHPIN,INPUT);
  pinMode(LEDPIN,OUTPUT);
}

void loop() {
  value = digitalRead(CRASHPIN);
  if (value == 0){
    digitalWrite(LEDPIN,HIGH);
  }
  if (value == 1){
    digitalWrite(LEDPIN,LOW);
    }
}


```
