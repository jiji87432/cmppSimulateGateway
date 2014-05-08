# 更新历史  
---    
2014年5月8日下午3:06:  

* 编码解码过程放入线程池，netty主线程只负责数据读取，不再处理业务逻辑，提高吞吐量

2014年4月22日上午10:35：  
  
* 添加数据统计  

2014年4月21日下午10:10:   
 
* 流量控制已经添加，核心功能完成，可进行大批量数据压力测试  

2014年4月21日上午10:52：    

* 基本功能完成，能正常接收短信，并返回响应及状态报告，支持多号码批量发送数据
* 支持多客户端同时连接

2014年4月17日下午4:16：    

* 连接活动检测已生效  

* 链接空闲检测已生效  

2014年4月16日下午4:03：  

* 协议对象编码解码完成并通过单元测试  

# 功能列表
---  
功能    |cmpp20 |cmpp30  |说明  
-------|:-------:|:--------:|:----  
协议对象编解码|√|√|  
短信上行接收|√|√|接收客户端发送短信并返回响应
心跳处理|√|√|接收客户端心跳并返回响应，指定时间无心跳，关闭连接
状态报告|√|√|接收上行并返回状态报告
流量控制|√|√|客户端数据超过流量限制返回超流量响应
数据统计|√|√|统计系统数据量及速度
短信上行发送|||模拟手机向客户端发送短信  
响应延时模拟|||对客户端发送短信数据延迟返回响应  
登陆数据认证|||对用户生份进行验证  
定时响应故障模拟|||指定时间后不再返回响应  
定时状态报告故障模拟|||指定时间后不再返回状态报告  

# 性能数据：  
---  
1. 测试环境：MAC OS 10.9，CPU:I7 4核8线程，内存：8G
2. 数据包大小：  

 	短信包大小：280 bytes   
 	响应包大小：21 bytes   
 	状态报告大小：145 bytes 
 	状态报告响应大小：21 bytes  

3. 短信下行速度 平均1500条/s



