# ARIMA-DEMO
ARIMA教程学习心得，AR、MA等简单操作，原教程网址为：https://blog.csdn.net/meng_shangjy/article/details/79714747


ARIMA模型主要应用于时间序列等
ARIMA建模的步骤主要有：

1、 获取被观测系统时间序列数据；
2、 对数据绘图，观测是否为平稳时间序列；是否为平稳时间序列可以通过两种方法：
（1）观察rolling_mean等图形
（2）使用statsmodels.tsa.stattools import adfuller
3、对于非平稳时间序列要先进行d阶差分运算，化为平稳时间序列；
4、 得到平稳时间序列后，对平稳时间序列分别求得其自相关系数ACF 和偏自相关系数PACF，通过对自相关图和偏自相关图的分析，得到最佳的阶层 p 和阶数 q
5、由以上得到的d、q、p，得到ARIMA模型。
6、使用训练好的ARIMA进行预测往后时间的值，方法为model.forecast(steps=1)
注意：forecast得到的是三个数组，第一个数组为steps个预测值，第二个数组为第一个数组中steps个值分别的standard error，
第三个数组应该是第一个数组和第二个数组各个值的置信度
7、由于上面ARIMA拟合的是经过转换后的数值（如去log和差分），因而最终的实际拟合及预测值要进行相应的转换，如使用cumsum和np.exp等函数。
