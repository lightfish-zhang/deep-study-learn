# 深度学习基本概念


## 一个简单的例子理解机器学习的过程

- 计算圆的面积

```py
# 代码片段 2
def learn(model,data):

    ... # 通过数据data训练模型model的代码

    return model # 已经训练好参数的模型

def test(model,x):

    ... # 将x输入模型model中得出结果y的代码

    return y # 返回计算结果--圆的面积

trained_model=learn(init_model,data) # 通过训练得到模型trained_model
y=test(trained_model,x=100) # 得到半径为100的圆的面积
```

简单解释

- `learn()` 函数的具体实现暂且不提， 它的作用是，会使用通过数据 data 训练模型 model ，当我们需要计算一个新的圆的面积时，就调用 test 函数，根据训练好的模型去计算其面积。
- 这里先把 `learn()` 视作黑盒子，我们不需要事先知道输入和输出之间的关系，也不需要手动设置任何参数，只要把数据 “喂给” 学习算法 learn , 它就会自动得出一个能够解决问题的模型。
- 在训练过程中，模型 model 其实是 “学习” 到了输入和输出之前的关系以及相关的参数。就像是一个数学家通过对圆的观察，得出了圆的面积和半径的关系，并且求出了圆周率

这就引出机器学习的基本部分

- 用来解决问题的模型model
- 学习数据（或者说训练数据）data
- 让模型model通过数据data学会解决特定问题的学习算法learn
- 用来纠正模型的test方法

## 学习算法的几个基本概念

### 回归问题与分类问题

- 回归(regression): 例如机器学会计算圆形面积的例子属于回归问题。即我们的目的是对于一个输入 x，预测其输出值 y，且这个 y 值是根据 x 连续变化的值。
- 分类(classification): 事先给定若干个类别，对于一个输入 x，判断其属于哪个类别，即输出一般是离散的。比如图片英文字母识别。

### 有监督学习与无监督学习

- 有监督学习，即在训练过程中，输入x得出y，而这个y的正确答案也事先准备好，用来纠正模型。
- 无监督学习，没有事先准备正确答案，一般用于聚类(cluster)问题，即给定一批数据，根据这批数据的特点，将其分为多个类别，虽然我并不知道这每个类别所代表的具体含义。
    + 这一点特别有趣，可以从大数据中发现人直觉难以察觉的信息，当中可能蕴含极大价值。
    + 比如网络商城的商品推荐算法可能会根据用户的使用习惯，以往的浏览历史等，将用户分为多个类别，同一类别的用户在行为模式上可能比较相似。而事先并不知道最终会划分出多少个类别，每个类别有哪些共同特点。


