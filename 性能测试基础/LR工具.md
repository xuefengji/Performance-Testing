#### VUG

##### LR脚本录制

web_url：用于 get 请求的录制

web_submit_data：用于 post 请求

乱码问题：

+ 录制过程产生的乱码

  tool--》recoding option》advance》support charset，选择 utf-8

+ 运行过程编码不一致

  Vuser 》Run-Time settings 》Internet Protocol 》Preferences 》Options 》General 》Convert from/to UTF-8

web_link：依赖于上下文的

web_submit_form：依赖于上下文



##### 参数化

+ 参数化基础
  + 目的：模拟真实场景
+ 读取数据
  + 顺序取值
  + 随机取值
  + 唯一性取值：只能取一次值



##### 关联

关联函数：web_reg_save_param

关联核心原理：

+ 本质：从响应中查找，通过左右边界进行查找

关联数组常用函数：

lr_paramarr_len：获取数组长度

lr_paramarr_idx：获取对应 index 的值

lr_output_message：输出信息

lr_paramarr_random：随机输出



##### 事务

作用：

+ 统计每一个请求或者每一批请求的响应时间：评估系统处理速度

+ 统计事务的成功率：系统稳定性

lr_start_transation

lr_end_transation

##### 检查点

与事务连用

lr_auto：是根据返回状态码判断是否错误，不会根据逻辑进行判断

检查点函数：web_reg_find：从响应中查找相应的标识



##### 思考时间

+ 什么是思考时间

  用户用于思考的时间：用户暂停发请求的时间

+ 为什么需要思考时间

  模拟真实场景

+ 思考时间在 LR 中的应用

  思考时间不能设置的太长，思考时间不能设置的一样，可以随机 50%-200% 之间



##### 集合点

适用场景：并发测试，主要关注大用户量并发的时候

+ 所有用户都在发请求
+ 所有用户都在提交同一个请求
+ 集合点不能模拟真实场景





#### Controller

+ 控制虚拟用户数量

  负载生成器：需要先转换成百分比模式，添加多个负载生成器，

+ 控制性能测试场景

  RAMP UP

  RAMP DOWN

  多少虚拟用户数是合理的

  多少时间是合理的

+ 控制各种运行策略

  IP 欺骗：服务器对客户端的IP有验证要求,适用于局域网

  带宽模拟

+ 附属功能：指标监控:监控 Linux statd





#### Analysis

基础功能：

+ 图表右键功能

+ RAMP UP/DOWN：
  + 越慢越好
  + 平衡好运行时间

常用前端性能指标（从用户角度感受）：

+ 响应时间
+ 响应的吞吐率，每秒钟服务器的响应大小
  + 服务器带宽
  + 客户端带宽
+ TPS：每秒事务数，设计性能需求
+ HPS：每秒点击数，作用不太大，减少HTTP请求



常用后端性能指标：

+ CPU

  + CPU 使用率  %processor time
  +  处理器队列长度  processor queue length 2*内核数

+ 带宽

  + 每秒接收的数据量，低于下行带宽/8
  + 每秒发送的数据量.低于上行带宽/8

+ 内存

  + 内存使用率
  + 内存页交换频率  page/sec，内存和虚拟内存之间的交换频率，越低越好

+ 磁盘 I/O

  + 硬盘使用率
  + 硬盘队列长度

+ 线程池

  + 多线程
  + 线程池：用于管理多线程的一种机制
  + 线程主要消耗的是 CPU 的资源，CPU 的资源是有限的
  + 动态影响

+ 缓存

  cpu 一级、二级、三级缓存

  