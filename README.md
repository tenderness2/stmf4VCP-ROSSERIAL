# stmf4VCP-ROSSERIAL
 这个project是通过USB虚拟串口实现的rosseril_client,通过STM32F407DiscoveryBoard的micro USB 和电脑相连接，ubuntu识别为/dev/ttyACM*，如果识别不成功，可以尝试断电重启。

更改端口权限：

sudo chmod 666 /dev/ttyACM0

建立连接：

rosrun rosserial_python serial_node.py _port:=/dev/ttyACM0 _baud:=115200
   
## DEMO
如果连接成功，不会出现任何的红色提示，如果提示是lost sync可以忽略，

查看所有topic：
* 指令：rostopic list

---------------------------------------

2017/6/11:更新内容：
* 可以稳定通信
* 增加一路增量式（正交）编码器（只有A,B两相）读写（PE8 PE9），舵机控制接口2个(PA1,PA2)
* 输出/tf信息 ， 
* 蓝灯闪烁指令：rostopic pub /toggle_led std_msgs/Empty "{}" -r 100

2017/7/10:更新内容：
* 增加topic odom 和tf
* 限定了电调的输出速度
* 校准了RCcar的速度
## BUG
* 在cubeMX修改一些配置时候会出现usb识别不到的问题，并且存在大量的编译的错误
* 解决方案：编译错误参考：http://www.cnblogs.com/tomwill/p/7059679.html 
*          端口识别问题：http://www.cnblogs.com/tomwill/p/7146955.html
## 编译
 STM32CubeMX 更新到最新版本
 
 keil uvsion 5.23
## QQ 群
 636457705
# 注意：这个Project还在更新，很不稳定！！！
