# Linux 下安装 JMeter 

## 安装步骤

+ 下载 Linux 版本相应的 JMeter 版本

  apache-jmeter-5.3.tar

  解压 tar -zxvf apache-jmeter-5.3.tar

+ 是否安装 jdk 环境

  Java -version 

  注意：jdk 必须是 Java 8 以上版本

  如果没有安装，需要先安装，如何安装，自行百度

+ 添加到环境变量

  vi /etc/profile，在文件末尾添加以下三行：

  export JMETER_HOME=/usr/local/apache-jmeter-5.3
  export CLASSPATH=$JMETER_HOME/lib/ext/ApacheJMeter_core.jar:$JMETER_HOME/lib/jorphan.jar:$CLASSPATH
  export PATH=$JMETER_HOME/bin:$PATH

  添加完成之后，使用 source /etc/profile 命令使环境变量生效

  输入：jmeter -v 如果出现以下信息，则表示安装成功
  _    ____   _    ____ _   _ _____       _ __  __ _____ _____ _____ ____
     / \  |  _ \ / \  / ___| | | | ____|     | |  \/  | ____|_   _| ____|  _ \
    / _ \ | |_) / _ \| |   | |_| |  _|    _  | | |\/| |  _|   | | |  _| | |_) |
   / ___ \|  __/ ___ \ |___|  _  | |___  | |_| | |  | | |___  | | | |___|  _ <
  /_/   \_\_| /_/   \_\____|_| |_|_____|  \___/|_|  |_|_____| |_| |_____|_| \_\ 5.3

  Copyright (c) 1999-2020 The Apache Software Foundation

  

  ## 运行 JMeter

  + 在 windows 环境写好脚本后，将脚本上传到已安装 Jmeter 的 Linux 环境中
  
  + 执行命令：jmeter -n -t test.jmx -l test.jtl 
  
    参数解释：
  
    -h 帮助 -> 打印出有用的信息并退出
  
    -n 非 GUI 模式 -> 在非 GUI 模式下运行 JMeter
  
    -t 测试文件 -> 要运行的 JMeter 测试脚本文件
  
    -l 日志文件 -> 记录结果的文件
  
    -r 远程执行 -> 启动远程服务
  
    -H 代理主机 -> 设置 JMeter 使用的代理主机
  
    -P 代理端口 -> 设置 JMeter 使用的代理主机的端口号
  
  + 运行完成后，会在当前目录生成一个 test.jtl 的文件，可以将文件下载到 windows上的 jmeter 中查看，也可生成 html 文件下载后查看
  
    注意： 拷到windows机器，打开windows 上的 jmeter（注意：Linux上的jdk和jmeter版本必须和windows上的保持一致，包括插件也要一致 
  
    生成 html 文件需执行命令：jmeter -g -test.jtl -o report，在 report 文件夹中含有 index.html 文件，直接打开即可查看
  
  