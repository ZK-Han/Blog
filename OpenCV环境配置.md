# OpenCV环境配置

找到系统变量中的path变量，双击它，点击新建，将你解压的opencv文件夹中的opencv\build\x64\vc14\bin路径添加到当中

将bin目录下面的opencv_world341.dll和opencv_world341d.dll文件复制到C:\Windows\SysWOW64这个文件夹里面即可

将bin目录里面的opencv_ffmpeg341_64.dll复制到C:\Windows\System32这个文件夹里面

进入属性管理器，菜单栏->视图->其他窗口->属性管理器

3、对Debug|X64进行配置，右键点击属性

4、这里我们对属性中的 VC++目录->包含目录和VC++目录->库目录进行添加相关路径，对 链接器->输入->附加依赖项进行添加相关路径

5、包含目录中加入

..\opencv\build\include

..\opencv\build\include\opencv

..\opencv\build\include\opencv2

库目录中加入

..\opencv\build\x64\vc14\lib

6、链接器->输入->附加依赖项中加入

opencv_world341d.lib

左键调试->选项->常规 勾选启动源服务器支持

符号那一项勾上微软符号服务器

注意解决方案平台那一栏要换成X64
