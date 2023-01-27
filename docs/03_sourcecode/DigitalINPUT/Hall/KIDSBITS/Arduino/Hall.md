# KidsBits Hall

R11ケーブルで簡単接続。

##Arduino

###磁石を検知

HALLセンサーに磁石を近づけるとLEDが光るようにします。
HALLセンサーを２ピンに、LEDを４ピンに接続します。


```c
#define INPUTPIN  2
#define LEDPIN    4

int value = 0;
void setup() {
  pinMode(LEDPIN, OUTPUT);
  pinMode(INPUTPIN, INPUT);
}
void loop(){
  value = digitalRead(INPUTPIN);
  if (value == HIGH) {
    digitalWrite(LEDPIN, LOW);
  } else {
    digitalWrite(LEDPIN, HIGH);
    }
}


```

###磁石近づけた回数を数える

```c

int summary = 0;
volatile int rotation_Count = 0;

void setup() {
  attachInterrupt(2,Counter,RISING);
  Serial.begin(115200);
}

void loop() {
  if (summary != rotation_Count){
    Serial.print(rotation_Count);
    Serial.println("rotation count");
    summary = rotation_Count;   
  }
  delay(100);
}
  void Counter(){
    rotation_Count++;
    }

```
