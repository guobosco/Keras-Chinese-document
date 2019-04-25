# 你恰好发现了 Keras  
Keras 是一个用 Python 编写的高级神经网络 API，它能够以 TensorFlow, CNTK, 或者 Theano 作为后端运行。  
## 指导原则
1. 用户友好
2. 模块化
3. 易扩展性
4. 基于 Python 实现

## 30 秒上手 Keras  
Keras 的核心数据结构是 model，一种组织网络层的方式。最**简单的模型**是 `Sequential 顺序模型`，它由多个网络层线性堆叠。对于更复杂的结构，应该使用 `Keras 函数式 API`，它允许构建任意的神经网络图。  
Sequential 模型如下所示：  

```
from keras.models import Sequential
model = Sequential()
```
可以简单地使用 `.add()` 来堆叠模型：  

```
from keras.models import Dense
model.add(Dense(units=64, activation='relu', input_dim=100))
model.add(Dense(units=10, activation='softmax'))
```
在完成模型构建后，使用`.compile()`来配置学习过程：

```
model.compile(loss='categorical_crossentropy',
              optimizer='sgd',
              metrics=['accuracy’])
```
如果需要，你还可以进一步地配置你的优化器。Keras 的核心原则是使事情变得相当简单，同时又允许用户在需要的时候能够进行完全的控制（终极的控制是源代码的易扩展性）。
