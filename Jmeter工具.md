# Jmeter 工具

## Jmeter工具组成
1、测试计划-->线程组
2、线程组：断言、定时器、监听器、配置元件、后置处理器、前置处理器、sample、逻辑控制器

### 线程组界面介绍：

![线程组](\images\线程组.png)

名称：线程组名称

线程数：虚拟用户数，可以设置

Ramp-up：设置的虚拟用户数，启动的时间

循环次数：可以勾选永远，必须手动停止

调度器：可以设置启动时间和持续时间

### JDBC参数化设置

1、线程组中添加配置原件，JDBC connection configuration

![jdbc](\images\jdbc.png)

variable Name for creates pool：与后面jdbc request中的名字相同

database url(mysql):jdbc:mysql://localhost:3306/test?serverTimezone=UTC，其中，test为数据库名，serverTimezone不设置时，会报错

JDBC driver class:mysql的为com.mysql.jdbc.Driver

username:连接数据库的用户名root

password：连接数据库的密码

2、添加JDBC request

![jdbcrequest](\images\jdbcrequest.png)

variable name of pool declared in jdbc config....:与之前JDBC config中配置的一致

sql query：查询mysql的语句

parameter values:当where id = ？时，此值代替？

parameter type：parameter values值在数据库中的类型如int、varchar等

variable name：查询的结果变量

result variable name：存储查询语句查询的所有结果名

query timeout：查询超时时间

limit resuktset：最小结果集

handle resuktset：结果集类型设置

