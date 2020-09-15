# -ARDUINO
學習ARDUINO的過程</br>
void setup(){}<--只執行一次，Arduino的初使設定</br>
void loop(){}<--會重覆執行，主程式的位置</br>
第一個指令 </br>
```c++
pinMode(腳位，INPUT/OUTPUT);
```
腳位模式設定 所使用的腳位設定為輸入或輸出</br>
腳位設定成INPUT 腳位初始狀態為1</br>
腳位設定為OUTPUY 腳位初始狀態為0</br>
-----------------------------------------------------------------</br>
第一個程式 功能 LED 閃爍 亮 0.1S 暗 0.1S</br>
電路圖如下:</br>
![image](https://github.com/MorrisChen0921/-ARDUINO/blob/master/2020-09-01-141715.jpg)</br>

```c++
void setup() {
  // put your setup code here, to run once:

   pinMode(2,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:

 digitalWrite(2,HIGH);//滅
 delay(100);
digitalWrite(2,LOW);//亮
 delay(100);
｝
```
第三個程式 功能 LED 由左至右逐一亮滅，功能如下
初始狀態  ○○○○
STEP1    ●○○○
STEP2    ○●○○
STEP3    ○○●○
STEP4    ○○○●
電路配置圖如下：
![image](https://github.com/MorrisChen0921/-ARDUINO/blob/master/2020-09-15-102014.jpg）

```c++
int LED=5;
void setup() {
  for (int i=2 ;i<6;i++)
   pinMode(i,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  for(int i=5; i>1; i--)
    digitalWrite(i,HIGH);
 if (LED>=2)
      digitalWrite(LED,LOW);
   else
      LED=6;   
  LED--;      

 delay(500);
}
```
