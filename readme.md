### 问题一：启动调试时Build报错，提示系统资源不足
解决方法： 加大Build process heap size

设置方法：
Preferences --> Build,Execution,Deployment --> Compiler，
将默认700的数值加大，比如我这里设置为1700

### 问题二：想从外层代码F7单步调试进入JDK源码内部，结果发现进不去
这是因为调试时，JDK源码受保护，一般单步调试不让进，但是可以设置。

解决方法：：

Preferences --> Build,Execution,Deployment --> Debugger 
--> Stepping --> Do not step into the classes将该选项去勾选
 
 ### 问题三：如何对JDK源码做注释？
 调试进入JDK源码以后，发现不能进行注释，每个文件上都有一个小锁的图标，
 这是因为现在关联的源码并不是我们项目里刚拷进去的源码，而是JDK安装
 目录下的src.zip只读压缩包。
 
 解决办法： 重新关联JDK源码路径为本项目路径下的这一份JDK源码。
 
 ## 源码结构和阅读顺序
 可以按照 java下面的包名
 lang --> util --> io --> nio --> time --> math --> net