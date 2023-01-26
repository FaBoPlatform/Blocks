# KidsBits RotaryEncorder

R11ケーブルで簡単接続。

##Arduino

```c
#define pinA 2            //CLK
#define pinB 3            //DT
#define pinSW 20          //SW
int encoderPosCount = 0;  //回転カウンタ
int pinALast;             //ピンの状態保持
int pinValue;             //ピンの状態

void setup() {
  //ピンの設定をする
  pinMode (pinA,INPUT);
  pinMode (pinB,INPUT);
  pinMode (pinSW,INPUT);
  //ピンの初期状態を調べる
  pinALast = digitalRead(pinA);
  Serial.begin (115200);
}

void loop() {
  //回転方向検出する
  pinValue = digitalRead(pinA);
  if (pinValue != pinALast){
    if (digitalRead(pinB) != pinValue) {  
      encoderPosCount ++;
      //時計回り
      Serial.println ("CW");
    } else {        
      //反時計回り
      encoderPosCount--;
      Serial.println("CCW");
    }
    Serial.println(encoderPosCount);     
  }
  pinALast = pinValue;
//ボタンが押された場合の処理
  if(digitalRead(pinSW) == 0){
    Serial.println("BUTTON PUSHED.");
  }
    delay(1);
}


```
