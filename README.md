**功能实现**

一、添加会飞物体：

	1、飞的实现：创建了个Fly_box_bp蓝图类，创建个Tick事件让它x轴不停的变化，达到飞的效果
	
	2、网络的同步实现：分别创立在服务器运行事件和组播事件来实现RPCs,并且在onserver时就set了需要同步的变量，用RPCS+Replication实现网络同步。

二、打击会飞的物体会加分：

	1、在子弹蓝图类里（即BP_Projectile）除了打击Hat和Character外添加了第一步的Fly_box_bp,如果判断子弹命中的组件含有Fly_box，就会施加伤害（模仿撞击Character）
	
	2、在第一步创建的Fly_box_bp里加入受到伤害事件，可以获得子弹的来源玩家，给其加分。

三、结算蓝图UI

  
    1、创建了个end—ui通过获取本地游戏状态来获取当前玩家的名字和成绩
    
    2、在关卡蓝图里设置20s结束然后播放end_UI以及暂停播放游戏
  
  
  演示视频的百度云链接：https://pan.baidu.com/s/1ExvSqJVLU1dBDbN1GDi2KA 
提取码：01o1
  
  演示视频内容：两个人联机时都可以打移动的box加分，各自经过20s游戏结束显示自己的成绩
