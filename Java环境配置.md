# Java环境配置

安装完成后，右击"我的电脑"，点击"属性"，选择"高级系统设置"，(或Win+Q，输入env，点击编辑系统环境变量)，选择"高级"选项卡，点击"环境变量"；

变量名：JAVA_HOME

变量值：Java安装路径；

变量名：CLASSPATH

变量值：.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar; （记得前面有个"."）

变量名：Path

变量值：添加%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;

## 测试是否安装成功

"开始"->"运行"，键入"cmd"；键入命令: java -version，若出现 Java -version则成功；
