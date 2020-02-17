##### LR脚本录制

web_url：用于get请求的录制

web_submit_data：用于post请求

乱码问题：

+ 录制过程产生的乱码

  tool--》recoding option》advance》support charset，选择utf-8

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