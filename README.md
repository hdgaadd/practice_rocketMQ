# RocketMQ DEMO:

实现步骤：

- 启动RocketMQ的Name Service服务、Broker服务
- 消息生产者传递消息对象Message对象
- 消息消费者接受消息后，解析消息，根据消息内容操作服务层实现用户财富的增加






# 先学知识
**背景**：阿里巴巴旗下产品，捐赠给Apache

RoketMQ需要下载安装包安装

**消息队列的作用：**

- 异步处理：用户执行某一请求触发多个任务，把任务保存在消息队列，先返回给用户结果，**不等**处理消息队列的任务**完成**，达到速响应用户的操作

  消息生产者发送消息后返回给用户结果，收到消息的消息消费者再根据所收到的消息一步步来处理消息队列的任务

- 解耦：以上也可实现，调用服务模块与具体执行模块之间的解耦

- 流量削减：把请求先保存在消息队列，而不是把请求直接交给服务器处理造成OOM，如果请求超过最大长度就拒绝用户的请求

**安装RocketMQ：**

- https://www.cnblogs.com/linjiqin/p/9553663.html

- 启动BROKER报错：错误: 找不到或无法加载主类 Files\Java\jdk1.8.0_152\lib;C:\Program

  关键点：C:\Program，而Java的安装路径为，说明rocketMQ无法读取有空格的文件夹

- 启动NAMESERVER
  Cmd命令框执行进入至‘MQ文件夹\bin’下，然后执行‘**start mqnamesrv.cmd**’

  启动BROKER                  broker经纪人[ˈbrəʊkə(r)]        consumer消费者[kənˈsjuːmə(r)]
  Cmd命令框执行进入至‘MQ文件夹\bin’下，然后执行‘**start mqbroker.cmd -n 127.0.0.1:9876 autoCreateTopicEnable=true**’