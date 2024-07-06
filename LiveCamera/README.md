# 基于QT的网络视频监控系统

### 

vs2022，qt5.15.2，

linux端作为服务器，推送监控视频

## 1.ubuntu [虚拟机](https://zhidao.baidu.com/search?word=虚拟机&fr=iknow_pc_qb_highlight)下使用摄像头

一、Windows设置

1、在Windows“[设备管理器](https://zhidao.baidu.com/search?word=设备管理器&fr=iknow_pc_qb_highlight)”->“图像设备”下确认存在设备“IntergratedCamera”

2.点击开始->运行，在对话框中输入”[services.msc](https://zhidao.baidu.com/search?word=services.msc&fr=iknow_pc_qb_highlight)”，回车，打开windows服务管理器。

3.在服务列表中选中”VMware USB Arbitration

Service”，双击打开属性对话框，再选择”启动”，就能启动VMware USB Arbitration Service服务了。

二、VMware设置

1、设置虚拟机：

在虚拟机菜单栏中选择“虚拟机（M）”->选择“可移动设备”->选择“xxxx

Camera”->选择“连接（断开与主机连接）”，设置完这项之后，虚拟机接管了笔记本摄像头。 （如果找不到USB摄像头，按照一、window的第2、3步试下）

2、在终端输入 ls /dev 就能看到 video0外设了。

3、在终端输入命令, 安装cheese

apt-get install chees

4、在终端输入命令，启动cheese查看摄像头情况

cheese

三、注意事项

如上操作都正常，cheese出来的视频窗口是[黑屏](https://zhidao.baidu.com/search?word=黑屏&fr=iknow_pc_qb_highlight)的，怎么回事？

在Vmware

Workstation的“虚拟机”->“虚拟机设置”->“USB控制器”下，查看“USB兼容性”，如果当前是“USB2.0”就修改为“USB3.0”，反之就修改为“USB2.0”。然后再在“虚拟机”->“可移动设备”下重新连接Camera，cheese就可以正常出视频了！！！



## 2.服务端开启

```
1.   make
2.   ./bin/server /dev/video0 10086
```

## 3.qt端开启



### 
