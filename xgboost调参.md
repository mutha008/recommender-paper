## xgoost调参

python api : https://xgboost.readthedocs.io/en/latest/python/python_api.html#xgboost.DMatrix

参数说明：https://xgboost.readthedocs.io/en/latest/parameter.html

1、eta  默认 0.3，学习率，梯度下降中使用

​	1)常用[0.01, 0.2]  

​	2)值越小， 鲁棒性越强，但同时需要增大树的数量

2、min_child_weight

3、max_depth  默认6，单棵树的深度

​	1）常用 [3,10]

​	2）值越大，模型越复杂，容易过拟合

4、gamma  默认0

​	1) 用于剪枝，值越大，越容易剪枝， 鲁棒性越好，

5、subsample  默认1

​	1） 常用 [0.5, 1]

​	2)

6、colsample_bytree 默认1

​	1）[0.5, 1]

7、lambda  默认1

​	1）L2正则化项权重

8、alpha 默认1

​	1）L1正则化项权重



http://blog.csdn.net/han_xiaoyang/article/details/52665396

http://blog.csdn.net/sb19931201/article/details/52557382