---
title: 理解Averaging Kernel
date: 2020-06-02 21:53:08
tags: RemoteSensing
---

大气遥感仪器因为其所处的位置，对大气的不同高度层的敏感性有差异。例如，卫星通常对大气上层更敏感，而地基仪器对近地面层更敏感。**Averaging Kernel是对不同层的敏感程度差异的定量描述。**这是对Averaging Kernel的概念性理解。下图是GOME-2，OMI和AIRS三种星载仪器的Averaging Kernel（AK）。可以明显看到，三者AK都是在高空比在低空大，因为星载仪器的探测敏感性和距离直接相关。

<img src="%E7%90%86%E8%A7%A3Averaging-Kernel/image-20200602221022595.png" alt="GOME-2,OMI,AIRS三种卫星的AK" style="zoom:;" />

Averaging Kernel之所以重要，是因为遥感研究中，经常需要多个仪器探测相同的变量并互相对比，但是AK不同的仪器观测结果无法直接对比。举个类比，不同仪器是不同的人，在观察同一个东西。他们的AK差异相当于不同观察者的视力不一样，有的是远视眼，有的是近视眼。只有确保进入仪器的是相同的东西，才能确保他们观察结果的差异仅取决于仪器系统偏差。



