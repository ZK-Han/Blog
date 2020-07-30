# OpenGL环境配置

## 下载OpenGL的所需要的文件

<http://www.opengl.org/resources/libraries/glut/glutdlls37beta.zip>

然后得到5个文件：
glut.dll glut32.dll glut.lib glut32.lib glut.h

找到目录..\VC\Tools\MSVC\14.10.25017\include\gl(没有的话就建立一个)。 将glut.h放到里面。（此时应该是#include <（GL或gl）/glut>）

找到目录..\VC\Tools\MSVC\14.10.25017\lib\x86  将glut.lib，glut32.lib放到里面。

最后把glut.dll和glut32.dll放到
C:\Windows\system32文件夹内（32位系统）或‪C:\Windows\SysWOW64(64位系统）

## 出现的问题（Visual Studio 2019）

### 问题描述

MSVCRTD.lib(exe_winmain.obj) : error LNK2019: 无法解析的外部符号 WinMain，该符号在函数 "int __cdecl invoke_main(void)" (?invoke_main@@YAHXZ) 中被引用
CamShift.exe : fatal error LNK1120: 1 个无法解析的外部命令

error LNK2001: unresolved external symbol _WinMain
debug/main.exe:fatal error LNK 1120:1 unresolved externals
error executing link.exe;

### 原因及解决办法

产生这个问题的真正原因是c语言运行时找不到适当的程序入口函数，

一般情况下，如果是windows程序，那么WinMain是入口函数，在VS2017中新建项目为“win32项目”

如果是dos控制台程序，那么main是入口函数，在VS2017中新建项目为“win32控制台应用程序”

而如果入口函数指定不当，很显然c语言运行时找不到配合函数，它就会报告错误。

### 修改设置适应你的需求

如果是windows程序：

1.菜单中选择 项目->属性, 弹出属性页窗口

2.在左边栏中依次选择：配置属性->C/C++->预处理器,然后在右边栏的预处理器定义对应的项中删除_CONSOLE, 添加_WINDOWS.

3.在左边栏中依次选择：属性配置->链接器->系统,然后在右边栏的子系统对应的项改为窗口(/SUBSYSTEM:WINDOWS)

如果是控制台程序：

1.菜单中选择 项目->属性, 弹出属性页窗口

2.在左边栏中依次选择：配置属性->C/C++->预处理器,然后在右边栏的预处理器定义对应的项中删除_WINDOWS, 添加_CONSOLE.

3.在左边栏中依次选择：属性配置->链接器->系统,然后在右边栏的子系统对应的项改为CONSOLE(/SUBSYSTEM:CONSOLE)