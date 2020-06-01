# NTPClock_Esp8285

## 功能：       
>       开机先显示一段数码管自检小动画
>       然后自动连接无线网络（数码管显示[c---]），秒>点闪烁
>       如果是首次连接或者15秒内无法连接到上次使用的网络则进入自动配网状态，数码管显示[s---]，此时可以用>手机微信的安信可小程序配网
>       配网成功后显示[done]，连接成功后自动通过NTP服务器同步时间，同步成功后开始时间显示。
>       配网成功后可以记住ssid和密码，下次开机除非无法连接，否则无需重新配网。
>       NTP服务器和同步间隔时间可以自己设置，代码中为8小时，可按自己需求修改，除非使用局域网中NTP服务器，否则不建议将时间间隔设置得过小。
>       只要把钟放在家里能连接到无线网络的地方，插上USB线就可以用。常年分秒不差。（Esp8266系列仅支持2.4G网络，5G的WiFi网络是连不上的）

## 硬件：
>       Esp8266或者Esp8285（没用到什么特殊的端口，我用的是安信可的Esp-01M，主要是因为体积小，加上扩展板双列直插，方便上洞洞板罢了）
>       TM1650（数码管驱动芯片）
>       共阴4位时钟专用数码管（自带秒点）      
>       引脚连接请参考/doc/Pin_Map.txt
>       USB口使用的是淘宝买的micro USB小板，然后用1117-3.3降压以后给电路供电。
>       使用TM1650驱动数码管，无需使用限流电阻，亮度可调，发色均匀。

## 开源代码：
       https://github.com/jjbboox/NTPClock_Esp8285

如果你还在使用老掉牙的Arduino IDE，请将main.cpp改名为NTPClock_Esp8285.ino，并将其他的*.h文件和*.cpp保存到ino相同的目录中即可

## 需要添加的Arduino库：
      NTPClient
      TM1650

## 正面：
![正面](/pic/IMG_20200531_153703_s.jpg) 


## 背面（跳线比较乱）：
![背面](/pic/IMG_20200531_153719_s.jpg) 

## 视频连接
>ESP8285(Esp8266) NTP时钟
<video src="https://v.youku.com/v_show/id_XNDY5MzYzMDg1Mg==.html" controls="controls" width="500" height="300">您的浏览器不支持播放该视频！</video>

NTP Clock By Arduino

原则上Esp8285和Esp8266是一样的。
硬件选择ESP8266，代码上没有任何区别。

使用VS Code + PlatformIO环境编写，使用Arduino IDE的话，请把include目录和src目录中的文件按照ArduinoIDE的规则存放，避免由于编译环境不同而产生编译错误。同时请将main.cpp改为main.ino


引脚连接请参考
/doc/Pin_Map.txt

电路图请参考
/doc/电路图.xlsx
