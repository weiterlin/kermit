# kermit
加入针对1500000波特率串口的支持
#1.下载
git clone https://github.com/weiterlin/kermit.git kermit
#2.编译
cd kermit
make linux -j4
#3.安装
sudo make install
#4.创建~/.kermrc文件
<br>文件内容如下：设置串口设备节点,设置串口波特率,设置抓取串口日志保存路径
<br>cp .kermrc ~/.kermrc
- 内容如下参考配置
<br>\#设置串口设备节点
<br>set line /dev/ttyUSB0
<br>\#设置串口波特率
<br>set speed 1500000
<br>set carrier-watch off
<br>set handshake none
<br>set flow-control none
<br>robust
<br>set file type bin
<br>set file name lit
<br>set rec pack 1000
<br>set send pack 1000
<br>set window 5
<br>set session-log TIMESTAMPED-TEXT
<br>\#设置抓取串口日志保存路径
<br>log session /home/linwei/work/logs/\v(ndate)-\v(time).log
<br>connect

#5.抓取串口日志，执行kermit命令
sudo kermit -c 
