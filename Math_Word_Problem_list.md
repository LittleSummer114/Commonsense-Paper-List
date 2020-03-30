# Math-Word-Problem-Paper-List
A summary of must-read papers for Math Word Problem

- Contributed by **[Jingyun Xu, Xin Wu]**.

## Datasets

| Dataset                                          | Task                    | Language        | Size                           |
| ------------------------------------------------ | ----------------------- | --------------- | ------------------------------ |
| [Math (EMNLP 2017)](#Math)     | 只有1个变量的线性代数题      | English | 23162 questions        |

| Model                                          | DataSet                    | Performance-1        | Performance-2                           |
| ------------------------------------------------ | ----------------------- | --------------- | ------------------------------ |
| [NE (EMNLP, 2018)](#NE)             | Math    | ACC: 68.4%  |          |

## [Papers](#papers)
## [Survey papers](#content)
## [Datasets]()
1. <span id = "Math">**Deep neural solver for math word problems.** </span>. EMNLP, 2017. [paper]() [dataset]()

    *Yan Wang, Xiaojiang Liu, and Shuming Shi.*

目前最大的关于数学题的数据集,有23,162条关于线性代数的只有1个未知变量的问题。
## [Methods](#content)   
### [Seq-Seq Models](#content)
\# equation normalization \#
1. <span id = "NE">**Translating a Math Word Problem to a Expression Tree.**</span> EMNLP, 2018. [paper]() [dataset]()

    *Lei Wang, Yan Wang, Deng Cai, Dongxiang Zhang, Xiaojiang Liu.*

这篇论文要解决的问题主要是之前的模型在处理数学问题时没有考虑到等式可以是重复的(e.g., x = x<sub>1</sub>+x<sub>2</sub>也可以写成 x = x<sub>2</sub>+x<sub>1</sub>),而重复的等式会带来输出空间不确定,从而影响基于数据的模型的表现。为了解决这个问题,作者提出了2种Equation Normalization(NE)的方法,在基于三种不同的Seq-Seq模型上进行了实验。
```
我自己的理解就是需要更多的数据才能学习到同样的模式的不同的表达方式

Question List:
同样都是Seq-Seq models,为什么用Bi-LSTM作为Encoder再加上NE之后,可以提高7个点?
```
![](https://github.com/LittleSummer114/Paper-List/blob/master/images/Math_Word-1.PNG)


