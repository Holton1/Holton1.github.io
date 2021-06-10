---
title: 如何滤去野火对BVOC排放反演的影响
date: 2020-04-19 11:44:26
tags: research
---
三种方法,各有优缺点。

1. 跑一组敏感性实验，用有野火的模式结果减去没有野火的模式结果,得到野火的影响。

	操作很方便，但是不合理，因为为野火的影响是非线性的。对2019年，相减后得到的仅由野火导致的HCHO VCD plume如下所示：

![GC Wildfire](image-20200419115418431.png)

可见2019年7月，野火导致在阿拉斯加中部很强的东西向延展的成片HCHO VCD信号，和TROPOMI同时观测到的HCHO VCD 空间分布很接近。这也佐证了TROPOMI在19年7月在Alaska中部的HCHOVCD有很强的野火贡献。

![TROPOMI origin and minuswildfire](image-20200419115852210.png)

用TROPOMI的HCHOVCD场，减去野火影响下的HCHO VCD场，得到滤去野火影响后的HCHO VCD场。过滤后19年6月Alaska中部的HCHO VCD峰值几乎都被消除了，7月的中部峰值也被削弱了很多，但还保留了原来的结构。这说明19年夏天，野火主要影响7月的HCHO VCD。但Alaska夏季的HCHO VCD pattern仍然是由植物排放VOC占主导的。

2. 用一氧化碳柱浓度作为野火的指标。

	实际效果不好，滤不干净。但可以和1做对比相互验证。2019年夏季，TROPOMI的CO VCD场如下所示：

	![TPM_COVCD_SupHiR_AK_1907](TPM_COVCD_SupHiR_AK_1907.png)

	可见CO VCD仅在7月出现明显超过背景值的pattern。这和1中提取的野火导致的HCHO VCD 空间分布非常相似。使用2x10^18 moles/cm^2作为筛选标准，滤除高于这个标准的数据点。得到的HCHO VCD场，空间结构没有明显变化，仅峰值强度被削弱。这与1得到的结论也是吻合的。

3. 用大气光学厚度作为指标。

	但是TROPOMI没有观测这个。用第三方数据会引入其他系统误差。还没有试过，无法评价。

总之，使用模式敏感性实验作差来滤除野火导致的影响，和用CO VCD作为标准来滤除野火影响的数据点，效果差不多，都得到了类似的结论：19年野火主要影响到7月Alaska中部的HCHO VCD, 但不影响Alaska的HCHO VCD 空间pattern，仅对峰值强度有影响。该pattern由陆地植物排放VOC主导。




