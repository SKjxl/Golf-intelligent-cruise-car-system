**该项目资源仅限学习，作者能力有限 若有建议 请留言**


# 项目简介
本项目设计了一套专门应用于高尔夫球场的自动导航智能巡航系统，用户在完成预定义路径规划后于高尔夫巡航车上实现自动巡航，该系统通过RTK定位算法获取车辆当前的位置、设计基于基线约束下的姿态测量算法计算车辆航向角信息，并通过通信模块传输车辆当前的状态信息至服务器。结合A* 算法和纯追踪算法分别实现了路径规划、路径跟踪，并在服务器上研发了符合导航系统设计的GUI界面，方便实时地操作规划路径和显示自动导航效果。

<div align=center>

![adssdsdfs](https://github.com/CWORLDY/Golf-intelligent-cruise-car-system/blob/master/document/photo/5.png)  

<div align=left>             

![adssdsdfs](https://github.com/CWORLDY/Golf-intelligent-cruise-car-system/blob/master/document/photo/1.jpg)

## 主要工作
1 **RTK定位算法**  
    以空间强相关性建立差分数学模型，通过卡尔曼滤波算法求解定位和载波相位模糊度的浮点解，然后采用最小二乘模糊度降相关（MLAMBDA）算法来求取载波相位的模糊度，从而实现厘米级的定位精度，提高定位算法的实时性和准确性。  
2 **基于基线约束的姿态测量算法**  
    提出一种高精度GPS卫星导航系统姿态测量算法，在单历元情况下，采用伪距辅助载波相位求解，为了消除伪距观测量带来的误差，引入基线长度作为已知量，对整周模糊度求解进行约束，从而实现了精度在1度以内的单历元姿态测量算法。  
3 **A\*路径规划算法**  
    针对高尔夫球场环境进行栅格地图建模，采用经典的A\*算法进行路径规划；为了提高路径规划的效率和平滑性，采用分治法的思想改进A\*算法的不足，同时对地图进行抽样降低运算的时间复杂度，提高路径规划的效率。  
4 **基于运动学模型的路径跟踪算法**  
    结合运动学模型设计了一种纯追踪算法，根据路径信息求出路径弯曲度并计算出前视距离，在前视距离的基础下确定目标点，利用运动学模型的运动规律计算出下一个运动动作的车轮转角，该算法无需进行繁琐的参数调试，从而实现对预定义路径的稳定跟踪。  


# 框架原理
本算法主要由四个模块组成，分别为RTK定位模块、GPS测姿模块、路径规划模块和路径跟踪模块。

![adssdsdfs](https://github.com/CWORLDY/Golf-intelligent-cruise-car-system/blob/master/document/photo/7.jpg)


# 实验结果

 **RTK测试**
![adssdsdfs](https://github.com/CWORLDY/Golf-intelligent-cruise-car-system/blob/master/document/photo/122.png)
  
    
 **姿态测试**
![adssdsdfs](https://github.com/CWORLDY/Golf-intelligent-cruise-car-system/blob/master/document/photo/15.jpg)
  
    
 **路径规划**
![adssdsdfs](https://github.com/CWORLDY/Golf-intelligent-cruise-car-system/blob/master/document/photo/9.png)
  
 **路径跟踪**  
![adssdsdfs](https://github.com/CWORLDY/Golf-intelligent-cruise-car-system/blob/master/document/photo/实地测试.png)



