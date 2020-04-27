# Text-Style-Transfer-Paper-List
A summary of must-read papers for **Text Style Transfer**

- Contributed by **[Jingyun Xu]**, from 2016-, 2020.3.12.
- :whale2: 取自静云(鲸鱼), :whale2: 的数量仅表示个人喜好的程度 :kissing_heart:, :heart_eyes: 表示想去细读的, :dizzy_face:表示看了，没有完全看懂的。

## Datasets

| Dataset                                          | Task                    | Language        | Size                           |
| ------------------------------------------------ | ----------------------- | --------------- | ------------------------------ |

## Baselines

| Model                                          | DataSet                    | Performance-1        | Performance-2                           |
| ------------------------------------------------ | ----------------------- | --------------- | ------------------------------ |

## [Papers](#papers)
## [Survey papers](#content)
## [Baselines](#content)      

## [General Models](#content)
## [Task-Specific Models](#content)

 \# Models: Improving Generalization Using Relations Between Premises and Hypothesis\#       

1.【】 <span id = "">**Improving Generalization by Incorporating Coverage in Natural Language Inference.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1909.08940.pdf)

   * Nafise Sadat Moosavi, Prasetya Ajie Utama, Andreas Rücklé, Iryna Gurevych.
```   
作者建模了premises和hypothesis间的关系,实验表明考虑了这种信息的NLI模型的泛化能力得到了提高.     
Question List:
1. 可不可以认为作者实际上是考虑了不同任务之间共有的特征?
```    

2.【:heart_eyes:】 <span id = "">**Explainable High-order Visual Question Reasoning: A New Benchmark and Knowledge-routed Network.**</span> arXiv, 2019. [paper](https://arxiv.org/pdf/1909.10128)

   * Cao, Qingxing and Li, Bailin and Liang, Xiaodan and Lin, Liang.

```   
Motivation:   
这篇论文的作者构建了一个Knowledge-based VQA的数据集,特点是在于以前的数据集涉及到的reasoning是一种first-order reasoning,而这篇论文涉及到multiple inference steps (called high-order), 具体来说,作者构建的数据集要回答的问题是:
这幅图里面那个男孩子和那个在1948年被引入的物体的关系是什么?
回答这个问题就需要涉及到2个三元组:
(1948年引入的物体,?)
(boy,??,?)    

Question List:    
1. 作者举的例子求解的是实体对间的关系? 但是实际上多个三元组(a,b,c)和(c,d,e),根据问的实体和关系在所在三元组中的位置,求解的问题可以分为4类:   
问中间实体,已知a,b,d,e,问c;问两边的实体,已知a,b,c,d,问e;问两边的关系,已知a,b,d,e,问c和a的关系;问开头和结尾的关系(知识图谱补全).
```

```   
Model:
输入是(question,image)对,作者的模型由3部分组成:   
第一部分将question解析成树的形式,获得需要求解的元素(包括间接元素(1948年引入的物体,?)和最终求解元素(boy,??,?)),已知元素及他们之间的关系;      
第二部分基于knowledge base进行搜索,得到间接元素(1948年引入的物体,?);
第三部分,基于间接元素和已知元素进行基于image的search,获得最终求解元素(boy,??,?))
```
![](https://github.com/LittleSummer114/Natural-Language-Inference-Paper-List/blob/master/images/Visual-1.PNG)
