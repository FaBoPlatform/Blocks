# KidsBits ADKeyboard

R11ケーブルで簡単接続。アナログ線１本より7個のボタン信号を検知できます。

##Arduino

```c
volatile int value;

void setup() {
  value = 0;
  Serial.begin(115200);
  pinMode(A0,INPUT);
}

void loop() {
  value = analogRead(A0);
  if (value > 700){
      Serial.println("S1");
  }
   if (value < 700 && value >= 600){
      Serial.println("S2");
  }
    if (value < 600 && value >= 500){
      Serial.println("S3");
  }
    if (value < 500 && value >= 400){
      Serial.println("S4");
    }
    if (value < 400 && value >= 350){
      Serial.println("S5");
    }
    if (value < 350 && value >= 330){
      Serial.println("S6");
    }
    if (value < 330 && value >= 300){
      Serial.println("S7");
    }
    delay(1);
}

```

サーミスタのB定数は3950
