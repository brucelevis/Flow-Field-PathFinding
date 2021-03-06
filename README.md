# 流场寻路算法简单实现
Flow field pathfinding algorithm implementation
* key words: `OpenGl` `Dijkstra` `Flow Field` `Path Finding`<br>
Flow field pathfinding algorithm implementation

* **当前实现的主要效果：**<br>
  1.地图上随机分布200个移动目标；<br>
  2.移动目标可绕过障碍物，沿着地图的流场找到最短路径（最小代价的路径）到达目标点；<br>
  3.可通过点击地图上的非障碍物区域，实时的更改目标地点，并更新流场；<br>
  4.可通过按着鼠标左键在地图上拖拽，实时绘制障碍物，并动态更新流场；<br>
  
* **效果图：**<br>
  蓝色点为终点，红色块为障碍物，蔚蓝色小点为移动目标，小点加线为流场方向指示箭头。这里的地图为均匀地图（即移动目标经过地图中每个网格的代价相同）  <br>
  
  1.初始地图效果：  <br>
  ![这里写图片描述](http://img.blog.csdn.net/20161014172713419)
  
  2.动态设置障碍物效果：  <br>
 ![这里写图片描述](http://img.blog.csdn.net/20161014172629950)
  
  3.重置终点效果：<br>
  ![这里写图片描述](http://img.blog.csdn.net/20161014195103285)
* **Bug：**<br>
  由于初次使用OpenGl，还有很多细节做得不到位<br>
  1.窗口大小变换后，鼠标点击的坐标转换等功能仍未实现；<br>
  2.由于效果需要导致的，移动目标在障碍物拐角处会跳到障碍物里面，然后穿过障碍物；<br>
  3.……<br>
  
* **算法步骤：**<br>
  1.初始化地图；<br>
  2.使用Dijstra算法，从终点开始，逐一对最优的邻接节点计算路径，从而计算整张网格化地图上所有点到终点的最短路；<br>
  3.根据最短路形成地图流场；<br>

* **参考文章：**<br>
	 主要参照了[这篇文章](https://gamedevelopment.tutsplus.com/tutorials/understanding-goal-based-vector-field-pathfinding--gamedev-9007)，思路很简单。
