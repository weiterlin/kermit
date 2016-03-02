# kermit
加入针对1500000波特率串口的支持
#1.下载
git clone https://github.com/weiterlin/kermit.git kermit
#2.编译
cd kermit
make linux -j4
#3.安装
sudo make install
#4.创建~/.kermrc文件，
文件内容如下：设置串口设备节点,设置串口波特率,设置抓取串口日志保存路径
set line /dev/ttyUSB0
set speed 1500000
set carrier-watch off
set handshake none
set flow-control none
robust
set file type bin
set file name lit
set rec pack 1000
set send pack 1000
set window 5
set session-log TIMESTAMPED-TEXT
log session /home/linwei/logs/\v(ndate)-\v(time).log
connect
#5.抓取串口日志，执行kermit命令
sudo kermit -c 
