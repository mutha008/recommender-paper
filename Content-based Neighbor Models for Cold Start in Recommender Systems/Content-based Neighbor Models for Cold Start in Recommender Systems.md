## Content-based Neighbor Models for Cold Start in Recommender Systems

#### 一、ACM Recommender Systems Challenge'17 

offline phase: 1.5M users 1.3M items 322M  user-item interactions four months 

interactions actions : impression, click, bookmark, reply, delete, recruiter

online phase:  online product

#### 二、输入特征

1. user content 

2. item content

3. user-item content：重叠的特征

4. user-item interaction

   ![](https://github.com/mutha008/recommender-paper/raw/master/Content-based%20Neighbor%20Models%20for%20Cold%20Start%20in%20Recommender%20Systems/QQ%E5%9B%BE%E7%89%8720171230164844.png)


   5.user-item temporal  特征同user-item interaction，但是只取最近一次的item

#### 三、模型

![QQ图片20171230170411](https://github.com/mutha008/recommender-paper/raw/master/Content-based%20Neighbor%20Models%20for%20Cold%20Start%20in%20Recommender%20Systems/QQ%E5%9B%BE%E7%89%8720171230170411.png)

##### 常用模型：

1. DNN  
2. GBMs  收敛更快  模型？

为了解决梯度过大或梯度过小的问题，采用了input normalization和 gradient clipping

1. 归一化是很重的任务， 且DNN对归一化输入的敏感性高，而GBM对于这一点要求不高
2. 梯度剪裁，主要避免梯度爆炸，每次参数更新的时候不直接用梯度g，而是跟梯度阈值比较，如果g大于梯度阈值，则变化为 g=梯度阈值/g

因此选用GBM模型，XGBoost library

##### 训练

1、语料切分

2、采样。

1. 随机正采样和负采样（去除冷启动的user和item）

2. 均衡采样

   1. 每个item采用，有效提高，降低热度偏差
   2. 每个class数量一致，容易训练

3. 目标

   ![](https://github.com/mutha008/recommender-paper/raw/master/Content-based%20Neighbor%20Models%20for%20Cold%20Start%20in%20Recommender%20Systems/QQ%E5%9B%BE%E7%89%8720171231155539.png)

4. 排序（减少排序候选集）

   1、形成top user-item pairs，并按score函数和策略排序





http://www.cs.toronto.edu/~mvolkovs/recsys2017_challenge.pdf

https://github.com/dmlc/xgboost/tree/master/demo