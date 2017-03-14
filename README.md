# SmartCab
# Reinforcement Learning
## Project: Train a Smartcab How to Drive

## 项目概述
在此项目中，你将运用强化学习技术让一个自动驾驶智能车在一个简化的世界中，并且在有限时间内高效地抵达目的地。首先你需要实现一个基本功能，让这个智能车能够在这个环境中动起来。一旦你的智能车能够在这个环境中移动了，你需要确定这个智能车可能处在的状态，需要考虑的因素包括交通信号灯，每个路由的来往车辆等。当确定状态之后，你要实现 Q-Learning 算法使得智能出租车能够在规定时间内到达指定目的地。最后，你需要找到学习参数和探索参数的最佳选择，提高 Q-Learning 算法的效果，确保自动驾驶智能车能够稳定的到达终点，并伴随着正的奖励。

### 安装pygame
运行：

	anaconda search -t conda pygame
选择适合自己的版本，并运行：

	conda install -c prkrekel pygame=1.9.2a0

### 运行代码
在 terminal 或命令行界面，把当前目录切换到 smartcab/ 的最顶层 （包含这两个项目文件夹）运行下面两条命令之一：

	python smartcab/agent.py 
或者

	python -m smartcab.agent

## 了解世界
![](https://raw.githubusercontent.com/hfrommane/SmartCab/master/UI.png)

## 实现一个基本的驾驶代理程序
- None 不做任何行动
- Left 左转
- Right 右转
- Forward 前进

作为第一个实现，到'choose_action()'代理程序函数，使驾驶代理程序随机选择其中的一个动作。注意你会访问到几个类的成员变量，它们有助于你编写这个功能，比如'self.learning'和'self.valid_actions'。实现后，运行几次代理程序文件和模拟程序来确认你的驾驶代理程序每步都执行随机的动作。

	action = random.choice(self.valid_actions)

程序运行结果：
![](https://raw.githubusercontent.com/hfrommane/SmartCab/master/figure/figure_1.png)
显然，出租车的行动完全是随机的，可靠性和安全性都没有提高。

## 实现Q-Learning驾驶代理程序
具体实现见 agent.py

程序运行结果：
![](https://raw.githubusercontent.com/hfrommane/SmartCab/master/figure/figure_2.png)
从这个结果看，可靠性和安全性都有了提高，但是依然是不安全和不可靠的。

## 改进Q-Learning驾驶代理程序
选择ϵ(探索因子)衰减函数：

![](https://raw.githubusercontent.com/hfrommane/SmartCab/master/formula/%E8%A1%B0%E5%87%8F%E5%87%BD%E6%95%B0.png)

程序运行结果：
![](https://raw.githubusercontent.com/hfrommane/SmartCab/master/figure/figure_3.png)
我们的程序已经具有了较高的安全性和可靠性。




