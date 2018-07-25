# 1.4 范围与局限

强化学习极其依赖于状态的概念——作为策略函数与值函数的输入, 且既作为模型的输入又作为模型的输出. 不那么正式的话, 我们可以将状态理解将一特定时间点的环境的某些方面传递给代理的信号. 我们在这里使用的状态的正式定义于[第3章](to chapter3)在马尔科夫决策过程的框架下给出. 然而, 从更宽泛的角度看, 我们鼓励读者沿用这个非正式的定义, 并将状态理解为代理可以获得的所有环境信息. 事实上, 我们假设状态信号由预处理系统产生, 而预处理系统名义上是代理所处的环境的一部分. 在本书中我们不处理关于状态信号的构建、更改与学习的内容(除了了在[17.3节](to section17.3)简短的部分). 我们之所以采取这样的方式, 不是因为我们认为状态表示不重要, 而是想将全部的注意力放到决策问题上. 换言之, 我们在本书中的关注点并非状态信号的设计, 而是决定采取什么动作, 作为能获取到的状态信号的函数. 

我们在本书中讨论的多数强化学习方法是围绕评估值函数构建的, 但对于解决强化学习问题而已这并非严格必需的. 举例来说, 例如遗传算法&lt;genetic algorithm&gt;、遗传规划&lt;genetic programming&gt;、模拟退火&lt;simulated annealing&gt;及其他优化算法的方法从不评估值函数. 这些方法在延长的时间周期中迭代, 且迭代时在不同的环境实例中应用不同的固定策略. 获得了最高奖赏的策略及其随机变体, 被保留到下一代的策略中, 并重复此过程. 我们将此称为进化方法&lt;evolutionary method&gt;, 因为其操作和生物进化类似, 生物进化中物种可以演化出特别的能力, 即使对个体而言可能终其一生也没有任何进步. 如果策略空间足够小, 或者可以构建出好策略可以很容易、普遍地找到的策略空间——或者有大量的时间用于搜索策略空间——那么进化方法是很有效的. 此外, 进化方法在面对如代理不能感知到环境的完整状态之类的问题时很有优势.

我们的关注点在于能从与环境的交互中学习的强化学习方法, 而这是进化方法做不到的. 能够利用个体的交互细节的方法在多数情况下远比进化方法高效. 进化方法没忽视了强化学习问题许多有用的结构: 其没有利用"欲搜索的策略是一个从状态到动作的函数"这一事实; 其未留意个体在生命周期中经历了哪些状态及选择了哪些动作. 在一些情况下这些信息可能会起误导作用(例如感知到了错误的状态), 但更多的情况下这些信息使得搜索更加高效. 虽然进化方法与学习有许多共同特征且能很自然地协同工作, 但我们进化方法本身特别适合于强化学习问题, 所以我们不在本书中介绍进化方法.