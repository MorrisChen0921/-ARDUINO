# -ARDUINO
學習ARDUINO的過程</p>
void setup(){}<--只執行一次，Arduino的初使設定</p>
void loop(){}<--會重覆執行，主程式的位置</p>
第一個指令 </p>
pinMode(腳位，INPUT/OUTPUT);</p>
腳位模式設定 所使用的腳位設定為輸入或輸出</p>
腳位設定成INPUT 腳位初始狀態為1</p>
腳位設定為OUTPUY 腳位初始狀態為0</p>
-----------------------------------------------------------------</p>
第一個程式 功能 LED 閃爍 亮 0.5S 暗 0.5S</p>
電路圖如下:</p>
![image](https://github.com/MorrisChen0921/-ARDUINO/blob/master/2020-09-01-141715.jpg)</p>
![image](https://github.com/MorrisChen0921/-ARDUINO/blob/master/sketch_sep08a.ino)
'''Arduino
void setup() {
  // put your setup code here, to run once:
for(int i=2;i<6;i++)
   pinMode(i,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
for(int i=2;i<6;i++) 
 digitalWrite(i,HIGH);//滅
 delay(100);
 for(int i=2;i<6;i++)
   digitalWrite(i,LOW);//亮
 delay(100);
｝
'''
