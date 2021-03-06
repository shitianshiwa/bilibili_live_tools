# python弹幕机

## 简介

这是一个用于在命令行显示bilibili直播弹幕的程序。

程序使用python3及其标准库编写，稍作修改后使用 3to2 移植后即可在python2上使用。

特点为简单的使用方式，极低的cpu及内存占用，以及高度可定制性。

## 需求

已安装 python3

## 运行

使用python3打开danmu.py以运行，或编写平台对应的bat或sh脚本文件执行。
运行主程序danmu.py时使用命令行参数 `--help` 以查看命令行帮助。

## 配置

可配置内容包括：

* 是否显示礼物提示，默认为不显示
* 是否使用彩色字符，默认为使用
* 若使用彩色字符，设置颜色方案
* 设置默认的直播间号码，默认为在程序运行后从命令行读取
* 设置单条弹幕的显示间隔时间，默认不开启间隔
* 是否以单行方式显示单条弹幕，默认为两行
* 是否将弹幕接收时间一并输出，默认为输出时间
* 是否将弹幕消息在显示的同时保存到本地文件中，默认为不保存
* 是否屏蔽由小电视或节奏风暴引起的刷屏信息
* 是否每隔三十秒自动显示当前在线观众数

支持使用命令行选项和配置文件方式进行配置，具体配置详情见config.ini或命令行 `--help` 选项。

## 其他

### 如何改为python2版本：
* 将danmu.py第一行的shebang中的python3改为python2
* 将包含 `from __future__ import` 的注释行取消注释
* 修改python2不支持的异常类(如TimeoutError)
* `pip3 install 3to2` 后，`cd` 到程序文件夹，`python3 3to2.py -w danmu.py configParser.py utility.py`。

### 关于彩色字符
需注意，彩色是由ANSI拓展转义字符实现的，在windows上的支持并不完善，但已知通过cmd.exe可正常运作。或者在选项中将colour设为0关闭彩色字符。

### 编码问题
受不同平台终端的编码格式所限，一些字符可能无法正确输出，如，中文windows平台gkb编码下程序能正常运作，但部分不支持的字符会被替换

### 个性化
大部分平台的终端都可以调节窗口透明度以及字体等设置。
