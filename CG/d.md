# 计算机图形学第四课
- 退关了三维空间中的平移，缩放，旋转
- 三维空间旋转，由于叉乘的影响，需要注意在沿Y轴旋转过程中的叉乘结果是x叉乘z,结果与y轴方向相反。
- 三维空间的`正交投影`不会产生近大远小的结果，三维空间的正交投影，通常是先进行标准化，然后进行平移和缩放
- 三维空间的`视图投影`会产生近大远小的效果，因此在计算三维空间的视图投影之前，需要合理转换原有的视图坐标，然后在对其做正常的平移和缩放即可；

### 定义空间
- 定义屏幕像素
- 所有像素：（0，0）-> （width-1,height-1）
- 转换为裁剪空间（0，width）->(-width/2,width/2)；（-width/2,width/2）->(-1,1)
- 高的转换同上
- 转换过程就是先平移，再缩放
### 图形再屏幕空间上的映射
- 映射三角形的三个顶点坐标到屏幕上
- 对于屏幕上的坐标，判断是否再三角形内部
- 判断方法有两种
1. `点p和另外一个顶带你在同一侧（三个顶点都要判断）`
2. `点p与三条边的叉乘，结果同向`
- 确认坐标后进行处理锯齿化
1. FXAA(快速进行抗锯齿)，找到边界，换为无锯齿边界
2. TAA，利用上一帧数据的边界

# 参考
- [GAMES101-现代计算机图形学入门-闫令琪](https://www.bilibili.com/video/BV1X7411F744?p=5&spm_id_from=pageDriver)