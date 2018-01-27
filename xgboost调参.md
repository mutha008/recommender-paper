## xgoost调参

python api : https://xgboost.readthedocs.io/en/latest/python/python_api.html#xgboost.DMatrix

参数说明：https://xgboost.readthedocs.io/en/latest/parameter.html

1、eta  默认 0.3，学习率，梯度下降中使用

​	1)常用[0.01, 0.2]  

​	2)值越小， 鲁棒性越强，但同时需要增大树的数量

![img](http://i.imgur.com/L7PhJwO.png)

2、min_child_weight

​	这个参数默认是 1，是每个叶子里面 h 的和至少是多少，对正负样本不均衡时的 0-1 分类而言，假设 h 在 0.01 附近，min_child_weight 为 1 意味着叶子节点中最少需要包含 100 个样本。这个参数非常影响结果，控制叶子节点中二阶导的和的最小值，该参数值越小，越容易 overfitting。 

3、max_depth  默认6，单棵树的深度

​	1）常用 [3,10]

​	2）值越大，模型越复杂，容易过拟合

4、gamma  默认0

​	1) 后剪枝时，用于控制是否后剪枝的参数。 值越大，越容易剪枝， 鲁棒性越好，

![这里写图片描述](http://img.blog.csdn.net/20180103171350288?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2IxOTkzMTIwMQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

5、subsample  默认1

​	1） 常用 [0.5, 1]

​	2) 样本随机采样，较低的值使得算法更加保守，防止过拟合，但是太小的值也会造成欠拟合。

6、colsample_bytree 默认1

​	1）[0.5, 1]

​	2）列采样，对每棵树的生成用的特征进行列采样.一般设置为： 0.5-1 

7、lambda  默认1

​	1）L2正则化项权重

8、alpha 默认1

​	1）L1正则化项权重



http://blog.csdn.net/han_xiaoyang/article/details/52665396

http://blog.csdn.net/sb19931201/article/details/52557382