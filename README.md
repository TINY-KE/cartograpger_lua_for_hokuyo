* hokuyo_laser.lua：https://blog.csdn.net/qq_38212787/article/details/107771684
  * 配置文件（lua文件）中，track的frame设置为laser
  * 这种方法建图，不存在base_footprint和map的变换关系，因此无法用来和 视觉slam创建的地图融合
  
* hokuyo_odom.lua：
  * 配置文件（lua文件）中，track的frame设置为base_footprint
  * 可用于和视觉地图的融合

* hokuyo_localization.lua：
  * 用于cartograpger的纯定位
  * 将"provide_odom_frame" 设置为true， 此时cartographer会通过激光匹配估计等手段，来产生并发布odom， 可用于代替导航时的里程计。