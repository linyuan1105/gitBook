# 针对新旧节点的对比的方式
一个优化：静态VNode,VNode的key一样、一次性节点；直接将VNode的实际组件实例赋值，不需要对VNode进行更新（增删改）操作；