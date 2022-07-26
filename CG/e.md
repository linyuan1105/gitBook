# 计算机图形学第五课
如何实现的光栅化？有什么问题？
#### 问题
- 多个三角形遮挡问题 `z-buffer(深度缓存)`
- 光栅化怎么做？（`确定顶点值，确定范围，颜色插值、法向量计算`）
- 如何将一个三角形画在屏幕上？（`图像坐标进行归一化处理，转换到裁剪坐标`）
- 引入明暗和颜色（bling-feng反射模型）
> 通过环境光+漫反射光+高光点的到点的能量信息；    
> 其中能量信息通常与光的角度有关，也就和法向量相关，每个点法向量不一致，最后求得的能量是有差异的    
> 对于环境中的能量，使用类似等高线的圆环去描述对于距离的能量值；   
----------
- 着色
> 三角形内部使用插值的方式进行着色
> 其中内部点的法向量可根据相邻面的法向量（或者相邻线）近似求得   
> 
- 世界空间到屏幕空间；世界空间得到纹理空间；
- 三角形内部进行插值的过程时出现摩尔纹的现象
> 原因是由于远处的像素占据太多的纹理范围；    
> 解决方式使用mipmap进行查询，控制住占据的纹理范围，从而合并像素
- 关于纹理坐标和应用
> 凹凸贴图的方式主要是通过改变像素点的高度，从而改变纹理坐标点的法向量
> ，从而影响纹理坐标点的能量值，进一步影响纹理坐标的着色；    
> 在纹理坐标映射的过程中主要有隐士几何和显示几何：    
> 隐式几何：从集合面中的点，找到点的函数关系          
> 显示几何： 从已知的函数关系，在几何体的面上找到对应的点
> 
- 关于形状的过度中涉及的数学理论`平面基本图形SDF`的推导和应用