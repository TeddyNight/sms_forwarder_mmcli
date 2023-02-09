# Simple SMS Forwarder 简单的短信转发脚本
## Introduction
Simply receive your sms received in ModemManager to Telegram (or any other service if you want)
转发随身WIFI一类的设备中ModemManager的短信到Telegram等平台
在我的随身WIFI(msm8916,debian系统中完成了测试)
Python3脚本，比起Openstick WIKI里的那个脚本来说，这个监听dbus信号，无需设置cron，比cron接收的更快，消息延迟会低一些
## Installation
以安装debian的随身WIFI为例:
1. 首先修改smsforwarder中的`msg_forwarder`函数部分，根据你的情况修改`<Telegram api>`,`<YOUR TOKEN>`,`<YOUR CHAT ID>`,默认是Telegram转发，需要其他平台自行修改代码，`text`是短信内容(包含号码和时间戳)
2. 安装依赖及安装主体程序
```
apt-get install python3 python3-requests python3-gi python3-dbus
chmod +x install.sh
./install.sh
```
3. 启动程序及设置开机自启
```
systemctl start smsforwarder
systemctl enable smsforwarder
```
