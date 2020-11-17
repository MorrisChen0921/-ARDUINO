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
第三個程式 功能 LED 由左至右逐一亮滅，功能如下</br>
初始狀態  ○○○○</br>
STEP1    ●○○○</br>
STEP2    ○●○○</br>
STEP3    ○○●○</br>
STEP4    ○○○●</br>
電路配置圖如下：</br>
![image](https://github.com/MorrisChen0921/-ARDUINO/blob/master/2020-09-15-102014.jpg)</br>
程式碼如下:
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
第四個程式 功能 LED 由左至右逐一亮滅，功能如下</br>
初始狀態  ○○○○○○○○</br>
STEP1    ●○○○○○○○</br>
STEP2    ○●○○○○○○</br>
STEP3    ○○●○○○○○</br>
STEP4    ○○○●○○○○</br>
STEP5    ○○○○●○○○</br>
STEP6    ○○○○○●○○</br>
STEP7    ○○○○○○●○</br>
STEP8    ○○○○○○○●</br>
STEP9    回到初始狀態</br>

加分題目
初始狀態   ○○○○○○○○</br>
STEP1     ○○○○○○○●</br>
STEP2     ○○○○○○●○</br>
STEP3     ○○○○○●○○</br>
STEP4     ○○○○●○○○</br>
STEP5     ○○○●○○○○</br>
STEP6     ○○●○○○○○</br>
STEP7     ○●○○○○○○</br>
STEP8     ●○○○○○○○</br>
STEP9    回到初始狀態</br>

<h1>類比輸出的應用</h1>
如圖 在腳位有出現~符號，代表可以做類比輸出</br>

![image](https://github.com/MorrisChen0921/-ARDUINO/blob/master/2020-09-15-132935.jpg)</br>

類比輸出的方式為 analogWrite(腳位,值)</br>
腳位必需是要有在Arduino UNO 板上有"~"符號</br>
值可填入 0-255</br>
請實作出呼吸燈的程式</br>
呼吸燈的功能從暗到亮再到暗的循環 每隔100mS變換亮度</br>
```c++
int value=255; int x=-15;
void setup() {
  // put your setup code here, to run once:
pinMode(3,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
if (value<=0 || value>=255) x=-x;
analogWrite(3,value);
delay(150);
value=value-x;
}
```

