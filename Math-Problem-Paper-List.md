# Natural-Language-Inference-Paper-List
A summary of must-read papers for **Natural Language Inference**


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
## [DataSets: 特定问题](#content)      

\#Annotation Artifacts Problem: Datasets\#

1.【】 <span id = "CommitmentBank">**Evaluating BERT for natural language inference: A case study on the CommitmentBank.**</span> EMNLP, 2019. [paper](https://www.aclweb.org/anthology/D19-1630/)

   * Jiang, Nanjiang and de Marneffe, Marie-Catherine.

    之前的自然语言推理的数据集存在标准偏见的问题,使得模型即使没有拥有推理能力也能够取得很好的效果。为了解决该问题,作者构建了一个新的数据集CommitmentBank,并用基于BERT的模型进行实验.  

 \#Datasets: About Specific Hypotheses about Invalid Heuristics\#

2.【:heart_eyes:】 <span id = "HANS">**Right for the Wrong Reasons: Diagnosing Syntactic Heuristics in Natural Language Inference.**</span> ACL, 2019. [paper](https://www.aclweb.org/anthology/P19-1334.pdf)

   * McCoy, Tom and Pavlick, Ellie and Linzen, Tal.

```   
这篇论文的作者认为预训练的语言模型的效果比较好的原因可能是依赖于某些线索，他们假设预训练的语言模型主要是依赖于三种线索，为此，他们构建了一个这三种线索不适用的数据集HANS，将BERT模型在MNLI数据集上面进行训练，将训练好的模型在他们构建的数据集上面进行测试，模型的效果很差，该结果表明了预训练的语言模型的确是依赖于某三种线索的。    

Question List:
他们构建的数据集的特点是什么，不考虑这三种线索，需要考虑什么?
```

\#Datasets: Lexical Inference\#

3.【:dizzy_face:】 <span id = "SherLIiC">**SherLIiC: A Typed Event-Focused Lexical Inference Benchmark for Evaluating Natural Language Inference.**</span> ACL, 2019. [paper](https://www.aclweb.org/anthology/P19-1086.pdf) [code](https://github.com/mnschmit/SherLIiC)

   * Martin Schmitt, Hinrich Schütze.

    这篇论文的作者认为之前的关于自然语言推理的数据集的目标并不是去评估模型是否拥有词汇推理的能力，为了解决这个问题，2018年的ACL上，有研究者提出利用   WordNet修改SNLI得到数据集来验证模型的词汇推理能力，由于WordNet主要是包含名词的，这就导致他们提出的数据集主要考虑两个文本是否存在冲突关系，相比之下，作者的提出的数据集可以认为是文本蕴含任务(文本蕴含考虑了文本间的蕴含、冲突、中立等关系)的一个特例。除此之外,在2016年的ACL上,有研究者构建了关于语法推理的数据集，但是他们对于存在二元关系的一个元组(a,c)，他们只是把WordNet中的同义词作为一边的上下文(比如动物),而另外一边仍然是用具体的表达来实例化的。而这篇论文提出的数据集，主要是在以下两个方面做出改进，第一个是同时type了两边的关系，作者认为这样子有利于消歧。举个例子来说，对于"Bezos runs Amazon",PERSON / COMPANY 这样的上下文中,"run"蕴含的是"lead"的意思,而对于"my mac runs macOS", COMPUTER / SOFTWARE 这样的上下文中,"run"蕴含的是"use"的意思。第二个方面是仅考虑命名实体之间的关系，作者认为基于非命名实体(比如动物,植物)的推理主要是发现facts，如"The sun rises from the East",而关注命名实体则更有可能捕捉像"Walmart closes gap with Amazon"这类events,而关于事件蕴含方面的知识如["A is closing gap with B" ⇒ "B is having lead over A"]是和关于facts的知识是不一样的。     

    Question List:
    1. 以前的方法只type二元关系的一边的原因是什么? 需要看2016的论文才知道了
    2. 不同的知识就需要不同的方法吗? 是否可以提出同时捕捉两种知识的模型呢?

\#迁移学习:利用在NLI训练的模型提高对话系统生成的response和context的一致性\# \# Datasets: Dialogue Natural Language Inference\#

4.【】 <span id = "">**Dialogue Natural Language Inference.**</span> ACL, 2019. [paper](https://www.aclweb.org/anthology/P19-1363.pdf)

   * Welleck, Sean and Weston, Jason and Szlam, Arthur and Cho, Kyunghyun.

    如何使得对话系统产生的回复和上下文保持一致是对话系统领域长期研究的问题。这篇论文提出了一个关于对话的自然语言推理数据集，作者在这个数据集上训练出1个模型,将其在对话系统的数据集上面进行验证,实验表明了他们提出的模型在一定程度上能够提高对话系统生成的回复的一致性。    
     Question List:   
     1. 为什么一定要构建新的? 旧的不行吗?
     2. 为什么在NLI上训练得到的模型可以在对方任务用?

  \# Datasets: 作者利用QA领域的数据集构建了一个关于qa的自然语言推理数据集\#  

5.【:tropical_fish:】 <span id = "">**Transforming Question Answering Datasets Into Natural Language Inference Datasets.**</span> arxiV, 2018. [paper](https://arxiv.org/pdf/1809.02922)

   * Demszky, Dorottya and Guu, Kelvin and Liang, Percy.


 \#Datasets: Fairness of An Evaluation Method for Generalization, NLI主要是用来验证fairness\#

6.【】 <span id = "">**Posing Fair Generalization Tasks for Natural Language Inference.**</span> EMNLP, 2019. [paper](https://www.aclweb.org/anthology/D19-1456.pdf)

   * Atticus Geiger, Ignacio Cases, Lauri Karttunen, Christopher Potts.

    目前的基于神经网络的模型在各种任务上都取得了很好的效果,而最近关于对抗学习的研究表明,训练出来的模型在和训练集很相似的数据上的效果也并不理想,从而引发了研究人员关于通用的基于神经网络的模型的泛化性的思考。这些发现暗示我们可能需要一种更为广泛的评价指标来评估现有的基于神经网络的模型，然而作者认为我们需要思考的是目前的评估过程是否是公平的,即模型是否是在能够支持模型提高泛化性的数据集上进行训练呢?在这篇论文中,作者形式化定义了评估过程的公平性,并基于该定义构建了一个关于自然语言推理的数据集。作者用该数据集验证了通用的基于神经网络的模型及和自然语言处理任务相关的模型的有效性，结果表明特定任务相关的模型取得了更高的效果,该发现引发了关于通用的基于神经网络的模型的可行性的思考。

 \# Dataset: Understanding Roles and Entities\#   \# Models: For the New Dataset \#     

7.【】 <span id = "">**Understanding Roles and Entities: Datasets and Models for Natural Language Inference.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1904.09720.pdf)

   * Mitra, Arindam and Shrivastava, Ishan and Baral, Chitt.
```   
这篇论文的作者发现之前的自然语言推理模型在处理下面的数据时,会错误地认为这两句话很有可能存在蕴含关系。       
premise: Kendall lent Peyton a bicycle.     
hypothesis: Peyton lent Kendall a bicycle.    
。基于此，他们提出了构建了2个新的数据集,现有的自然语言处理模型在这2个数据集上的实验效果不好。为此,作者设计了新的模型,并通过实验验证了该模型的有效性.     
Question List:
1. 为什么以前的模型处理上述例子时,效果会不好呢?
2. 作者为什么要构建新的数据集?
2. 作者如何解决的?
```

## [DataSets: 评估NLI模型](#content)      

  \# Datasets: NLI数据集,用于评估句子表示捕捉不同类型推理的能力\#  

1.【】 <span id = "">**Collecting Diverse Natural Language Inference Problems for Sentence Representation Evaluation.**</span> EMNLP, 2018. [paper](https://www.aclweb.org/anthology/D18-1007.pdf)

   * Poliak, Adam and Haldar, Aparajita and Rudinger, Rachel and Hu, J Edward and Pavlick, Ellie and White, Aaron Steven and Van Durme, Benjamin.   

 \# Datasets: 评估目前的NLI模型\#  

2.【】 <span id = "">**Stress Test Evaluation for Natural Language Inference.**</span> COLING, 2018. [paper](https://www.aclweb.org/anthology/C18-1198.pdf) [code](https://abhilasharavichander.github.io/NLI_StressTest/)

   * Aakanksha Naik, Abhilasha Ravichander, Norman Sadeh, Carolyn Rose, Graham Neubig.

```      
Question List:
1. 作者构建的新的压力测试数据集和之前的数据集的区别是什么? 为什么要再构建一个数据集呢?
```  

## [DataSets: 特定领域](#content)   

  \# Datasets: 基于病人的医学历史记录的医学领域的NLI数据集\#  \# 引入外部知识\#  

1.【:tropical_fish:】 <span id = "">**Lessons from Natural Language Inference in the Clinical Domain.**</span> EMNLP, 2018. [paper](https://www.aclweb.org/anthology/D18-1187.pdf)

   * Romanov, Alexey and Shivade, Chaitanya.

## [对NLI任务的思考](#content)

\# Waiting...\#    

1.【:tropical_fish:】 <span id = "">**Generating Token-Level Explanations for Natural Language Inference.**</span> EMNLP, 2019. [paper](https://www.aclweb.org/anthology/N19-1101.pdf)

   * Thorne, James and Vlachos, Andreas and Christodoulopoulos, Christos and Mittal, Arpit.

  \# Dataset: 作者为SNLI数据集提供了Explanations,验证了考虑了Explanations的NLI模型的有效性\#  

2.【:whale2: :whale2: :whale2: :whale2: :whale2:】 <span id = "">**e-SNLI: Natural Language Inference with Natural Language Explanations.**</span> NIPS, 2018. [paper](http://papers.nips.cc/paper/8163-e-snli-natural-language-inference-with-natural-language-explanations.pdf) [code](https://github.com/OanaMariaCamburu/e-SNLI)

   * Camburu, Oana-Maria and Rockt{\"a}schel, Tim and Lukasiewicz, Thomas and Blunsom, Phil.   

```   
之前的NLI工作发现目前的NLI模型只需要hypothesis,就能取得很好的效果,这说明模型并没有掌握推理能力,而是基于已有的线索。这篇论文的作者基于SNLI数据,标注了关于premise和hypothesis关系间的解释,是目前为之最大的包含解释的自然语言推理数据集,有57K条数据。
作者进行了5组实验:
1. 模型的输入只有hypothesis，分别生成label和explanations，100条测试数据,其中只有6.84条explanations可靠,而有66条的label正确。
2. 先生成label，将其作生成的explanations的第一个词,100个测试样本,80个label正确, 人工评价有34.68条explanations正确
3. 先生成explanations,再利用explanations生成label,test accuracy of labels下降了,人工评价有64.27条explanations正确,说明结果更可靠
4. 利用数据集获得更好的sentence representations,在10个任务上进行实验。
5. 将在该数据集训练得到的模型迁移到out-of-domain NLI任务中

主要基于的论文:
Annotation artifacts in natural language inference data.    (目前的NLI模型仅输入hypothesis就能取得很好的效果)
Supervised learning of universal sentence representations from natural language inference data. (迁移学习)
```     

  \# Datasets: 生成hypothesis\#  

3.【】 <span id = "">**Constructing a Natural Language Inference dataset using generative neural networks.**</span> Computer Speech \& Language, 2017. [paper](https://arxiv.org/pdf/1607.06556.pdf)

   * Janez Starc, Dunja Mladenić.

  \# 从一个句子生成另一个句子 \#  

4.【:heart_eyes:】 <span id = "">**Generating natural language inference chains.**</span> arxiV, 2016. [paper](https://arxiv.org/pdf/1606.01404)

   * Kolesnyk, Vladyslav and Rockt{\"a}schel, Tim and Riedel, Sebastian.    

  \# Datasets: multiple premises\#  

5.【】 <span id = "">**Natural Language Inference from Multiple Premises.**</span> IJCNLP, 2017. [paper](https://arxiv.org/pdf/1710.02925)

   * Lai, Alice and Bisk, Yonatan and Hockenmaier, Julia.

 \# Annotation Artifacts Problem Cross-dataset\#      

6.【】 <span id = "">**Mitigating Annotation Artifacts in Natural Language Inference Datasets to Improve Cross-dataset Generalization Ability.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1909.04242.pdf)

   * Zhang, Guanhua and Bai, Bing and Zhang, Junqi and Bai, Kun and Zhu, Conghui and Zhao, Tiejun.
```   
为了解决NLI数据集中的标注偏见问题,该论文提出在跨领域的数据中进行模型的训练,提高模型的泛化能力.
```    

## [逻辑推理](#content) 

 \# Visual Analogical Reasoning \#  
1.【】 <span id = "">**RAVEN: A Dataset for Relational and Analogical Visual Reasoning.**</span> CVPR, 2019. [paper](https://wellyzhang.github.io/attach/cvpr19zhang.pdf) [code](https://github.com/WellyZhang/RAVEN) [Supp](https://wellyzhang.github.io/attach/cvpr19zhang_supp.pdf) [DataSet](https://drive.google.com/file/d/111swnEzAY2NfZgeyAhVwQujMjRUfeyuY/view?usp=sharing) [Blog](https://wellyzhang.github.io/blog/2019/03/07/RAVEN/)

   * Zhang, Chi and Gao, Feng and Jia, Baoxiong and Zhu, Yixin and Zhu, Song-Chun. 
   
 \# Visual Reasoning \#  
2.【】 <span id = "">**Learning perceptual inference by contrasting.**</span> NIPS, 2019. [paper](https://wellyzhang.github.io/attach/neurips19zhang.pdf) [Blog](https://wellyzhang.github.io/blog/2019/11/25/CoPINet/)

   * Zhang, Chi and Jia, Baoxiong and Gao, Feng and Zhu, Yixin and Lu, Hongjing and Zhu, Song-Chun. 
  
 \# Visual Analogical Reasoning \#  
3.【】 <span id = "">**Machine Number Sense: A Dataset of Visual Arithmetic Problems for Abstract and Relational Reasoning.**</span> AAAI, 2020. [paper](https://wellyzhang.github.io/attach/aaai20zhang.pdf) [Blog](https://wellyzhang.github.io/blog/2019/11/25/CoPINet/)

   * Zhang, Wenhe and Zhang, Chi and Zhu, Yixin and Zhu, Song-Chn. 

 \# 解释CNN网络逻辑中表达的知识 把预训练好的CNN中的内容提出成1个图模型 \#  
4.【】 <span id = "">**Interpreting CNN knowledge via an Explanatory Graph.**</span> AAAI, 2018. [paper](https://www.aaai.org/ocs/index.php/AAAI/AAAI18/paper/view/17354/16757) [Blog](https://wellyzhang.github.io/blog/2019/11/25/CoPINet/)

   * Zhang, Quanshi and Cao, Ruiming and Shi, Feng and Wu, Ying Nian and Zhu, Song-Chun. 
   
 \# 理解NLP模型 \#  
5.【】 <span id = "">**Towards a deep and unified understanding of deep neural models in NLP.**</span> ICML, 2019. [paper](http://proceedings.mlr.press/v97/guan19a/guan19a.pdf) [code](https://github.com/icml2019paper2428/Towards-A-Deep-and-Unified-Understanding-of-Deep-Neural-Models-in-NLP)

   * Guan, Chaoyu and Wang, Xiting and Zhang, Quanshi and Chen, Runjin and He, Di and Xie, Xing. 
   
 \# 解释CNN网络逻辑中表达的知识 把预训练好的CNN中的内容提出成1个决策树模型  \#  
6.【】 <span id = "">**Interpreting cnns via decision trees.**</span> CVPR, 2019. [paper](http://openaccess.thecvf.com/content_CVPR_2019/papers/Zhang_Interpreting_CNNs_via_Decision_Trees_CVPR_2019_paper.pdf)

   * Zhang, Quanshi and Yang, Yu and Ma, Haotian and Wu, Ying Nian. 
   
 \# 用神经网络处理SAT问题 \#  
6.【】 <span id = "">**Learning a SAT solver from single-bit supervision.**</span> ICLR, 2018. [paper](https://openreview.net/pdf?id=HJMC_iA5tm)

   * Selsam, Daniel and Lamm, Matthew and B{\"u}nz, Benedikt and Liang, Percy and de Moura, Leonardo and Dill, David. 
   
 \# 用一阶逻辑增强神经网络 \#  
7.【】 <span id = "">**Augmenting Neural Networks with First-order Logic.**</span> ACL, 2019. [paper](https://openreview.net/pdf?id=HJMC_iA5tm)

   * Li, Tao and Srikumar, Vivek. 
   

## [高效的 NLI Models](#content)

1.【】 <span id = "">**Gaussian Transformer: A Lightweight Approach for Natural Language Inference.**</span> AAAI, 2019. [paper](https://aaai.org/ojs/index.php/AAAI/article/view/4614/4492)

   *	Maosheng Guo, Yu Zhang, Ting Liu.

## [General Models](#content)

\#预训练语言模型 小样本学习 应用于NLI任务\#    

1.【:whale2:】 <span id = "">**Exploiting Cloze Questions for Few-Shot Text Classification and Natural Language Inference.**</span> arxiV, 2020. [paper](https://arxiv.org/pdf/2001.07676.pdf)

   * Timo Schick, Hinrich Schütze.

```   
这篇论文的作者发现预训练的语言模型还没有在只有少量数据的场景中进行应用。基于此，他们提出了一种半监督的训练流程，即在少量样本的训练集上训练出1个语言模型，然后用这个语言模型给大量未标注的数据打标签，之后一个序列分类器可以在这些标注好的数据集上面进行训练，作者在文本分类和自然语言推理两个任务上面验证了他们模型的有效性。
```

2.【】 <span id = "">**Utilizing BERT Intermediate Layers for Aspect Based Sentiment Analysis and Natural Language Inference.**</span> arxiV, 2020. [paper](https://arxiv.org/pdf/2002.04815.pdf)

   * Youwei Song, Jiahai Wang, Zhiwei Liang, Zhiyue Liu, Tao Jiang.

 \#  Cross-Lingual Data Augmentation 应用于NLI任务 \#       

3.【】 <span id = "">**XLDA: Cross-Lingual Data Augmentation for Natural Language Inference and Question Answering.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1905.11471.pdf)

   * Singh, Jasdeep and McCann, Bryan and Keskar, Nitish Shirish and Xiong, Caiming and Socher, Richar.

## [Task-Specific Models: 基于神经网络的Relations Between Premises and Hypothesis建模](#content)

 \# Models: Improving Generalization Using Relations Between Premises and Hypothesis\#       

1.【】 <span id = "">**Improving Generalization by Incorporating Coverage in Natural Language Inference.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1909.08940.pdf)

   * Nafise Sadat Moosavi, Prasetya Ajie Utama, Andreas Rücklé, Iryna Gurevych.
```   
作者建模了premises和hypothesis间的关系,实验表明考虑了这种信息的NLI模型的泛化能力得到了提高.     
Question List:
1. 可不可以认为作者实际上是考虑了不同任务之间共有的特征?
```    

2.【】 <span id = "">**DR-BiLSTM: Dependent Reading Bidirectional LSTM for Natural Language Inference.**</span> NAACL, 2018. [paper](https://www.aclweb.org/anthology/N18-1132.pdf)

   * ini, Reza and Hasan, Sadid A and Datla, Vivek and Liu, Joey and Lee, Kathy and Qadir, Ashequl and Ling, Yuan and Prakash, Aaditya and Fern, Xiaoli and Farri, Oladimeji.   

3.【】 <span id = "">**Asynchronous Deep Interaction Network for Natural Language Inference.**</span> EMNLP, 2019. [paper](https://www.aclweb.org/anthology/D19-1271.pdf)

   * Liang, Di and Zhang, Fubao and Zhang, Qi and Huang, Xuan-Jing.

4.【】 <span id = "">**Attention-Fused Deep Matching Network for Natural Language Inference.**</span> IJCAI, 2018. [paper](https://www.ijcai.org/Proceedings/2018/0561.pdf) [code](https://github.com/lukecq1231/nli)

   * Duan, Chaoqun and Cui, Lei and Chen, Xinchi and Wei, Furu and Zhu, Conghui and Zhao, Tiejun.

5.【】 <span id = "">**Convolutional Interaction Network for Natural Language Inference.**</span> EMNLP, 2018. [paper](https://www.aclweb.org/anthology/D18-1186.pdf)

   * Gong, Jingjing and Qiu, Xipeng and Chen, Xinchi and Liang, Dong and Huang, Xuan-Jing.

  \# Models: 建模句子对间关系\#  

6.【】 <span id = "">**Natural Language Inference by Tree-Based Convolution and Heuristic Matching.**</span> ACL, 2016. [paper](https://www.aclweb.org/anthology/P16-2022.pdf)

   * Mou, Lili and Men, Rui and Li, Ge and Xu, Yan and Zhang, Lu and Yan, Rui and Jin, Zhi.      

7.【:heart_eyes:】 <span id = "">**Enhanced LSTM for Natural Language Inference.**</span> ACL, 2017. [paper](https://www.aclweb.org/anthology/P17-1152.pdf)

   * Chen, Qian and Zhu, Xiaodan and Ling, Zhen-Hua and Wei, Si and Jiang, Hui and Inkpen, Diana.   

      \# Models: 第一个使用LSTM\#  

8.【】 <span id = "">**Learning Natural Language Inference with LSTM.**</span> NAACL, 2016. [paper](https://www.aclweb.org/anthology/N16-1170.pdf)

   * Wang, Shuohang and Jiang, Jing.

## [Task-Specific Models: 考虑外部信息](#content)

### [Task-Specific Models: 考虑图片信息](#content)

1.【】 <span id = "">**Image-Enhanced Multi-level Sentence Representation Net for Natural Language Inference.**</span> ICDM, 2018. [paper](https://ieeexplore.ieee.org/document/8594899)

   * Zhang, Kun and Lv, Guangyi and Wu, Le and Chen, Enhong and Liu, Qi and Wu, Han and Wu, Fangzha.   

### [Task-Specific Models: 考虑知识图谱](#content)

\#Models: Knowledge Base-based Approaches\#     

1.【】 <span id = "">**Improving Natural Language Inference Using External Knowledge in the Science Questions Domain.**</span> AAAI, 2019. [paper](https://wvvw.aaai.org/ojs/index.php/AAAI/article/view/4705/4583)

   * Xiaoyan Wang, Pavan Kapanipathi, Ryan Musa, Mo Yu, Kartik Talamadupula, Ibrahim Abdelaziz, Maria Chang, Achille Fokoue, Bassem Makni, Nicholas Mattei, Michael Witbrock.

\#Models: Knowledge Base-based and Pre-training based Approaches\#

2.【:tropical_fish:】 <span id = "">**Knowledge Enhanced Attention for Robust Natural Language Inference.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1909.00102.pdf)

   * Alexander Hanbo Li, Abhinav Sethy.
```   
这篇论文结合知识图谱中的知识和BERT进行自然语言推理。
```

\#Models: WordNet-based Approaches\#

3.【:tropical_fish:】 <span id = "">**Neural Natural Language Inference Models Enhanced with External Knowledge.**</span> ACL, 2018. [paper](https://www.aclweb.org/anthology/P18-1224.pdf)

   * Chen, Qian and Zhu, Xiaodan and Ling, Zhen-Hua and Inkpen, Diana and Wei, Si.

\#Models: Knowledge Base Completion-based and Logic-based Approaches\#    

4.【:tropical_fish: :tropical_fish:】 <span id = "">**Combining Axiom Injection and Knowledge Base Completion for Efficient Natural Language Inference..**</span> AAAI, 2019. [paper](https://wvvw.aaai.org/ojs/index.php/AAAI/article/view/4730/4608)

   * Yoshikawa, Masashi and Mineshima, Koji and Noji, Hiroshi and Bekki, Daisuk.

### [Task-Specific Models: 基于Logic](#content)

\#Models: Pretraining-based and Logic-based Approaches\#        

1.【:tropical_fish:】 <span id = "">**Probing Natural Language Inference Models through Semantic Fragments.**</span> AAAI, 2020. [paper](https://arxiv.org/pdf/1909.07521.pdf) [code](https://github.com/huhailinguist/ccg2mono)

   * Richardson, Kyle and Hu, Hai and Moss, Lawrence S and Sabharwal, Ashish.    

\#Models: Monotonicity-based and Logic-based Approaches\#

2.【:tropical_fish:】 <span id = "">**MonaLog: a Lightweight System for Natural Language Inference Based on Monotonicity.**</span> SCIL, 2020. [paper](https://arxiv.org/pdf/1910.08772.pdf)

   * Hu, Hai and Chen, Qi and Richardson, Kyle and Mukherjee, Atreyee and Moss, Lawrence S and Kuebler, Sandra.

 \# 逻辑驱动的NLI模型 \#  
3.【:tropical_fish:】 <span id = "">**A Logic-Driven Framework for Consistency of Neural Models.**</span> EMNLP, 2019. [paper](https://arxiv.org/pdf/1909.00126.pdf) [code](https://github.com/utahnlp/consistency)

   * Li, Tao and Gupta, Vivek and Mehta, Maitrey and Srikumar, Vivek. 

## [Task-Specific Models: 其他](#content)

 \# Models:  Pretraining-based and Example Forgetting-based Example Selection Approaches\#       

 1.【】 <span id = "">**Robust Natural Language Inference Models with Example Forgetting.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1911.03861.pdf)

   * Yaghoobzadeh, Yadollah and Tachet, Remi and Hazen, TJ and Sordoni, Alessandro.   

```   
Example Forgetting是最近提出一种衡量样本的硬度的方法,作者将预训练的语言模型在基于该方法选择出的样本上进行训练,提高其在NLU任务上的效果.
```    

  \# Models: mutli-step reasoning\#  

2.【:tropical_fish:】 <span id = "">**Stochastic Answer Networks for Natural Language Inference.**</span> arxiV, 2018. [paper](https://arxiv.org/pdf/1804.07888)

   * Liu, Xiaodong and Duh, Kevin and Gao, Jianfeng.

 \#Annotation Artifacts Problem: Models\#  

3.【:heart_eyes:】 <span id = "">**Don't Take the Premise for Granted: Mitigating Artifacts in Natural Language Inference.**</span> ACL, 2019. [paper](https://www.aclweb.org/anthology/P19-1084.pdf) [code](https://github.com/azpoliak/robust-nli)

   * Belinkov, Yonatan and Poliak, Adam and Shieber, Stuart and Van Durme, Benjamin and Rush, Alexander Sasha.

```   
之前的自然语言推理的数据集存在标准偏见的问题,大部分工作都是去构建新的数据集,他们构建的数据集有可能会造成新的问题,而这篇论文的作者提出2种方法来训练模型,并在12个数据集上验证了提出的模型的有效性.
```   

  \# NLI模型 \#  

4.【】 <span id = "">**Compare, Compress and Propagate: Enhancing Neural Architectures with Alignment Factorization for Natural Language Inference.**</span> EMNLP, 2018. [paper](https://www.aclweb.org/anthology/D18-1185.pdf)

   * Tay, Yi and Luu, Anh Tuan and Hui, Siu Cheung.

\#Models: Discourse Marker-based Approaches\# \#Models: Reinforcement Learning\#

5.【:tropical_fish:】 <span id = "">**Discourse Marker Augmented Network with Reinforcement Learning for Natural Language Inference.**</span> ACL, 2018. [paper](https://www.aclweb.org/anthology/P18-1091.pdf)

   * Pan, Boyuan and Yang, Yazheng and Zhao, Zhou and Zhuang, Yueting and Cai, Deng and He, Xiaofe.

```   
作者发现某些连接词如"but","so"可以用来句子间的逻辑关系,在句子的表示中考虑这些连接词能够得到更好的句子表示从而提高NLI模型的效果。除此之外,他们设计了一个基于强化学习框架的模型,利用标签信息来设计强化学习框架中的奖励函数,从而提高其在NLU任务上的效果.作者的模型由2部分组成,一部分判断输入中的词语是否是连接词,另一部分预测句子间的关系.
```

\# Models: 考虑Word-Pair-Dependency-Triplets \#

6.【:tropical_fish:】 <span id = "">**Adopting the Word-Pair-Dependency-Triplets with Individual Comparison for Natural Language Inference.**</span> COLING, 2018. [paper](https://www.aclweb.org/anthology/C18-1035.pdf)

   * Du, Qianlong and Zong, Chengqing and Su, Keh-Yih.

```   
Premise: An older man sits with his orange juice at a small table in a coffee shop while employees
in bright colored shirts smile in the background.
Hypothesis: An elderly man sitting in a small shop.
由于之前的NLI模型没有能捕捉到两句话中small和shop的错误，导致他们错误地认为上面两句话存在蕴含关系.
```

 \# Models: Pretrained Dependency Parser-based Approaches \#  \# Compared with Pre-trained Models \#     

7.【】 <span id = "">**Improving Natural Language Inference with a Pretrained Parser.**</span> AAAI, 2020. [paper](https://arxiv.org/pdf/1909.08217.pdf)

   * Pang, Deric and Lin, Lucy H and Smith, Noah A.
```   
这篇论文提出了利用预训练好的句法解析器获得词语的表示,和预训练的语言模型如BERT、ELMo等在NLU的数据集上进行了对比.
```
   \# Models: 基于syntax\#  

8.【】 <span id = "">**Syntax-based attention model for natural language inference.**</span> arxiV, 2016. [paper](https://arxiv.org/pdf/1607.06556.pdf)

   * Liu, PengFei and Qiu, Xipeng and Huang, Xuanjing.     

  \# Models: 考虑词语间关系和全局的依赖关系\#  

9.【】 <span id = "">**Distance-based self-attention network for natural language inference.**</span> arxiV, 2017. [paper](https://arxiv.org/pdf/1712.02047)

   * Im, Jinbae and Cho, Sungzoon.     

   \# Models: 分解复杂的句子,从而捕捉其和简单句子的关系\#  

10.【】 <span id = "">**A Decomposable Attention Model for Natural Language Inference.**</span> EMNLP, 2016. [paper](https://www.aclweb.org/anthology/D16-1244.pdf)

   * Ankur Parikh, Oscar Täckström, Dipanjan Das, Jakob Uszkoreit.   

## [实验型论文](#content)

  \# Experiments \#  

1.【】 <span id = "">**When data permutations are pathological: the case of neural natural language inference.**</span> EMNLP, 2018. [paper](https://www.aclweb.org/anthology/D18-1534.pdf) [code](https://github.com/natschluter/nli-data-permutations)

   * Schluter, Natalie and Varab, Daniel.

 ```      
Question List:
1.  作者通过重新排列句子中的词语顺序等方式生成了新的验证集,NLI模型的效果就变差了.
```  

  \# 实验型论文:作者通过实验发现现有的NLI模型通过直接学习hypothesis中的rule都可以达到很好的效果\#  

2.【】 <span id = "">**Annotation Artifacts in Natural Language Inference Data.**</span> NAACL, 2018. [paper](https://www.aclweb.org/anthology/N18-2017.pdf)

   * Gururangan, Suchin and Swayamdipta, Swabha and Levy, Omer and Schwartz, Roy and Bowman, Samuel and Smith, Noah A.

\# Experiments: Pretraining and Knowledge-Enhanced Model  \#       

3.【:tropical_fish:】 <span id = "">**Several Experiments on Investigating Pretraining and Knowledge-Enhanced Models for Natural Language Inference.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1904.12104.pdf)

   * Li, Tianda and Zhu, Xiaodan and Liu, Quan and Chen, Qian and Chen, Zhigang and Wei, Si.
```   
这篇论文的作者比较了与预训练的语言模型和知识增强的模型在处理自然语言推理任务时的特点,并给出了他们分别正确以及错误的case.
```

## [Interpreting NLI Models](#content)

  \#分析和解释NLI模型\#    

1.【:heart_eyes:】 <span id = "">**NLIZE: A Perturbation-Driven Visual Interrogation Tool for Analyzing and Interpreting Natural Language Inference Models.**</span> IEEE transactions on visualization and computer graphic, 2018. [paper](https://ieeexplore.ieee.org/document/8454904)

   * husen Liu, Zhimin Li, Tao Li, Vivek Srikumar, Valerio Pascucci, Peer-Timo Bremer.

  \# 解释NLI模型\#  

1.【:heart_eyes:】 <span id = "">**Interpreting Recurrent and Attention-Based Neural Models: a Case Study on Natural Language Inference.**</span> EMNLP, 2018. [paper](https://www.aclweb.org/anthology/D18-1537.pdf)

   * Ghaeini, Reza and Fern, Xiaoli and Tadepalli, Prasa.

## [Applications](#content)

 \# 迁移学习: 在NLI数据集上面进行训练从而获得句子的表示\#  

1.【】 <span id = "">**InferLite: Simple Universal Sentence Representations from Natural Language Inference Data.**</span> EMNLP, 2018. [paper](https://www.aclweb.org/anthology/D18-1524.pdf) [code](https://github.com/Smerity/keras_snli)

   * Jamie Kiros, William Chan.

  \# 将从神经机器翻译(NMT)系统中获得的句子表示应用于NLI任务,验证NMT捕捉的语义信息\#  

2.【】 <span id = "">**On the Evaluation of Semantic Phenomena in Neural Machine Translation Using Natural Language Inference.**</span> NAACL, 2018. [paper](https://www.aclweb.org/anthology/N18-2082.pdf)

   * Poliak, Adam and Belinkov, Yonatan and Glass, James and Van Durme, Benjamin.

 \#迁移学习: 利用在NLI训练的模型减少abstractive summarization任务中生成的summaries中的factual error\#

3.【:heart_eyes:】 <span id = "">**Ranking Generated Summaries by Correctness: An Interesting but Challenging Application for Natural Language Inference.**</span> ACL, 2019. [paper](https://www.aclweb.org/anthology/P19-1213.pdf)

   * Tobias Falke, Leonardo F. R. Ribeiro, Prasetya Ajie Utama, Ido Dagan, Iryna Gurevych.  

 \# 基于NLI模型的提高对话系统生成的回复的一致性的模型\#  #强化学习\#  

4.【:tropical_fish::tropical_fish::tropical_fish:】 <span id = "">**Generating Persona Consistent Dialogues by Exploiting Natural Language Inference.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1911.05889.pdf)

   * Song, Haoyu and Zhang, Wei-Nan and Hu, Jingwen and Liu, Ting.

 \# 基于NLI模型的Python中的type类型预测\#  

5.【】 <span id = "">**DLTPy: Deep Learning Type Inference of Python Function Signatures using Natural Language Context.**</span> ArxiV, 2019. [paper](https://arxiv.org/pdf/1912.00680.pdf) [code](https://github.com/casperboone/dltpy/)

   * Boone, Casper and de Bruin, Niels and Langerak, Arjan and Stelmach, Fabian.

  \# 基于释义识别任务、NLI任务、句子相似性匹配任务、问答任务的对不同模型建模句子对的能力的评估\#  

6.【】 <span id = "">**Neural Network Models for Paraphrase Identification, Semantic Textual Similarity, Natural Language Inference, and Question Answering.**</span> COLING, 2018. [paper](https://www.aclweb.org/anthology/C18-1328.pdf)

   * Lan, Wuwei and Xu, Wei.

   \# 利用argument来发现有用的评论\#  

7.【:heart_eyes:】 <span id = "">**Using argument-based features to predict and analyse review helpfulness.**</span> EMNLP, 2017. [paper](https://www.aclweb.org/anthology/D17-1142.pdf)

   * Liu, Haijing and Gao, Yang and Lv, Pin and Li, Mengxue and Geng, Shiqiang and Li, Minglan and Wang, Hao.

   \# categorical propositions \#  

8.【:heart_eyes:】 <span id = "">**Argument invention from first principless.**</span> ACL, 2019. [paper](https://www.aclweb.org/anthology/P19-1097.pdf)

   * Bilu, Yonatan and Gera, Ariel and Hershcovich, Daniel and Sznajder, Benjamin and Lahav, Dan and Moshkowich, Guy and Malet, Anael and Gavron, Assaf and Slonim, Noam.

   \# 通过分解命题来挖掘argument \#  

9.【:heart_eyes:】 <span id = "">**Decompositional argument mining: A general purpose approach for argument graph construction.**</span> ACL, 2019. [paper](https://www.aclweb.org/anthology/P19-1049.pdf)

   * Gemechu, Debela and Reed, Chris.  

   \# 构建argumentation graph \#  

10.【:heart_eyes:】 <span id = "">**Solving advanced argumentation problems with answer-set programming.**</span> AAAI, 2017. [paper](https://www.aclweb.org/anthology/P19-1049.pdf)

   * Brewka, Gerhard and Diller, Martin and Heissenberger, Georg and Linsbichler, Thomas and Woltran, Stefan.

   \#  implicit argument prediction  \#  

11.【:heart_eyes:】 <span id = "">**Implicit Argument Prediction as Reading Comprehension.**</span> AAAI, 2019. [paper](https://www.aaai.org/ojs/index.php/AAAI/article/view/4589/4467) [code](https://github.com/pxch/imp_arg_rc)

   * Cheng, Pengxiang and Erk, Katrin.

```   
Predicate-argument tuples describe "who did what to whom".
Twice in the late 1980s Gillingham came close to winning promotion to the second tier of English football,
but a decline then set in.
Argument: Gillingham
predicate: decline
```

   \#  implicit argument prediction  \#  

12.【:heart_eyes:】 <span id = "">**Counting complexity for reasoning in abstract argumentation.**</span> AAAI, 2019. [paper](https://www.aaai.org/ojs/index.php/AAAI/article/view/4589/4467) [code](https://github.com/pxch/imp_arg_rc)

   * Fichte, Johannes K and Hecher, Markus and Meier, Arne.

```   
Predicate-argument tuples describe "who did what to whom".
Twice in the late 1980s Gillingham came close to winning promotion to the second tier of English football,
but a decline then set in.
Argument: Gillingham
predicate: decline
```

## [DataSets: 计算机视觉领域](#content)   

\# 我觉得本质上是在做结合文本和知识库的search. \#       

12.【:heart_eyes:】 <span id = "">**Explainable High-order Visual Question Reasoning: A New Benchmark and Knowledge-routed Network.**</span> arXiv, 2019. [paper](https://arxiv.org/pdf/1909.10128)

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









