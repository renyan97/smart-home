# smart-home
 一．作品背景：随着物联网概念深入人心，传统的家居系统多依赖于触发式控制，语音控制技术的引入将使得智能家居的控制不再单调。
  二．作品简介：本作品由智能终端（两层结构），微信小程序前端和服务器端四部分构成。具体功能如下：

1.	通过微信小程序掌握室内外情况：包括室内外温度，湿度，室外PM2.5，风力，天气情况，室内光照强度，火焰强度以及空气质量（天然气，煤气浓度，一氧化碳，可燃气浓度）

2.	语音控制：通过微信小程序语音控制室内智能家居，包括:各房间灯管，客厅灯（暖黄色，粉色灯，报警灯，音乐背景灯等）以及其他智能家居设备。

3.	手动控制：用户不方便语音输入时，可通过点击微信小程序各家居对应的icon图进行相应的控制。

4.	远程控制：用户可使用微信小程序在联网的场景下对室内已经连接的智能设备进行远程操作。

5.	应用场景：该系统的智能终端主要应用与家庭，会场，餐厅等室内。微信小程序可应任何联网场景下。

一、作品原理 
    微信小程序：JavaScript作为业务逻辑，wxml是页面布局与结构。Wxss用于处理样式。
智能硬件两层结构：树莓派用作硬件的控制中心，包括数据处理，数据上传，网络请求，作为上位机与多个arduino通信等，大部分使用python脚本语言。Arduino主要用于采集传感器数据，控制继电器，处理树莓派传输的信号等，均使用c语言编写。
服务器：服务器语言采用node.js，数据库采用mysql，使用knex对数据库进行相关操作。
二、系统框图





                                       Knex数据库操作
                      返回data数据                 

    

                          


                  Wx.request                       python
网络通信层       Post请求                            reques tpost请求                   

                               返回json数据






                                                 串口通信
                                            
             蓝牙通信                                    nrf24l01通信







                     传感器数据                     继电器，led灯等其
                     采集                           他控制  

三、系统功能划分
    微信小程序：用于前端，是直接面向用户的客户端。用户可直接查看各种数据，也可以进行相应的控制操作。
智能硬件两层结构：树莓派用作硬件的控制中心，包括数据处理，数据上传，网络请求，作为上位机与多个arduino通信等，大部分使用python脚本语言。Arduino主要用于采集传感器数据，控制继电器，处理树莓派传输的信号等，均使用c语言编写。
服务器：主要用于处理小程序和树莓派的相应请求，通过操作数据库。返回各模块需要的数据。

四、整体运行效果
    微信小程序整体运行流程，无卡顿，用户界面友好。语音识别速度快，用户体验良好。各控制操作连接蓝牙情况下，硬件反应速度不超过0.5秒。远程控制网络情况良好的情况下硬件反应时间不超过2秒。


