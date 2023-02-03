# KidsBits Ultrasonic

超音波を発生させ反射する音のレベルを計測して障害物とセンサーの距離を推定します。

##Arduino

KidsBits Ultrasonic　の　ECHOを３ピンに、TRIGER２ピンのそれぞれ接続します。

```cpp
#define TRIGER 2
#define ECHO   3

volatile int distance;

float checkdistance_3_4(){
    digitalWrite(ECHO,LOW);
    delayMicroseconds(2);
    digitalWrite(ECHO,HIGH);
    delayMicroseconds(10);
    digitalWrite(ECHO,LOW);
    float distance = pulseIn(TRIGER,HIGH) / 58.00;
    delay(10);
    return distance;
  }

void setup() {
  distance = 0;
  Serial.begin(115200);
  pinMode(ECHO,OUTPUT);
  pinMode(TRIGER,INPUT);
}

void loop() {
  distance = checkdistance_3_4();
  Serial.print("The distance is : ");
  Serial.print(distance);
  Serial.println("cm");
  delay(500);
}

```
