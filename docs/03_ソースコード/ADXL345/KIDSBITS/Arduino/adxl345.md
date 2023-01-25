# KidsBits ADXL345

３つの方向XYZの加速度がわかります。

##Arduino

```c
#include <Wire.h>
#include <FaBo3Axis_ADXL345.h>

FaBo3Axis fabo3axis;

void setup()
{
  Serial.begin(9600); // シリアルの開始デバック用

  Serial.println("Checking I2C device...");

  if(fabo3axis.searchDevice()){
    Serial.println("I am ADXL345");
  }
  Serial.println("Init...");
  fabo3axis.configuration();
  fabo3axis.powerOn();
}
```
