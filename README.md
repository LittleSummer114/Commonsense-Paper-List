# Commonsense-Paper-List
A summary of must-read papers for Commonsense

- Contributed by **[Jingyun Xu]**.

## [Content](#content)

<table>
<tr><td colspan="2"><a href="#survey-papers">1. Survey</a></td></tr> 
<tr><td colspan="2"><a href="#Commonsense Knowledge Acquisition">2. Commonsense Knowledge Acquisition</a></td></tr>
<tr>
    <td>&emsp;<a href="#Commonsense Knowledge Generation">2.1 Commonsense Knowledge Generation</a></td>
    <td>&ensp;<a href="#Commonsense Knowledge Updating">2.2 Commonsense Knowledge Updating"</a></td>
</tr>
<tr><td colspan="2"><a href="#Commonsense Making and Explanation">3. Commonsense Making and Explanation</a></td></tr> 
<tr><td>&emsp;<a href="#Direct Sense Making and Explanation">3.1 Direct Sense Making and Explanation</a></td></tr>
<tr><td>&emsp;<a href="#Indirect Sense Making">3.1 Indirect Sense Making</a></td></tr>
    <tr>
    <td>&emsp;<a href="#Representation">3.1.1 Representation</a></td>
</tr>
    <tr>
    <td>&emsp;<a href="#Pre-trained Language Models">3.1.1.1 Pre-trained Language Models</a></td>
    <td>&ensp;<a href="#Commonsense Knowledge Updating">3.1.1.2 Commonsense Knowledge Updating"</a></td>
</tr>
</table>

## [Survey papers](#content)
1. **Recent Advances in Neural Question Generation.** arxiv, 2018. [paper](https://arxiv.org/pdf/1905.08949.pdf)
    
    *Liangming Pan, Wenqiang Lei, Tat-Seng Chua, Min-Yen Kan.* 

## [Models](#content)   

### [Basic Seq2Seq Models](#basic-models)

Basic Seq2Seq models with attention to generate questions. 

1. **Learning to ask: Neural question generation for reading comprehension.** ACL, 2017. [paper](https://www.aclweb.org/anthology/P17-1123.pdf)

    *Xinya Du, Junru Shao, Claire Cardie.*


### [Encoding Answers](#answer-encoding)

Applying various techniques to encode the answer information thus allowing for better quality answer-focused questions. 

1. **Answer-focused and Position-aware Neural Question Generation.** EMNLP, 2018. [paper](https://www.aclweb.org/anthology/D18-1427)
   
   *Xingwu Sun, Jing Liu, Yajuan Lyu, Wei He, Yanjun Ma, Shi Wang*

### [Linguistic Features](#linguistic-features)

Improve QG by incorporating various linguistic features into the QG process. 

1. **Neural Generation of Diverse Questions using Answer Focus, Contextual and Linguistic Features.** INLG, 2018. [paper](https://arxiv.org/pdf/1809.02637.pdf)

    *Vrindavan Harrison, Marilyn Walker*


### [Question-specific Rewards](#RL-rewards)

Improving the training via combining supervised and reinforcement learning to maximize question-specific rewards

1. **Teaching Machines to Ask Questions.** IJCAI, 2018. [paper](https://www.ijcai.org/proceedings/2018/0632.pdf)
   
   *Kaichun Yao, Libo Zhang, Tiejian Luo, Lili Tao, Yanjun Wu*


### [Content Selection](#content-selection)

Improve QG by considering how to select question-worthy contents (content selection) before asking a question. 

1. **Identifying Where to Focus in Reading Comprehension for Neural Question Generation.** EMNLP, 2017. [paper](https://www.aclweb.org/anthology/D17-1219.pdf)
   
   *Xinya Du, Claire Cardie*

### [Question Type Modeling](#question-type-modeling)

Improve QG by explicitly modeling question types or interrogative words. 

1. **Question Generation for Question Answering.** EMNLP,2017. [paper](https://www.aclweb.org/anthology/D17-1090)
   
   *Nan Duan, Duyu Tang, Peng Chen, Ming Zhou*

### [Encode Wider Contexts](#encode-wider-contexts)

Improve QG by incorporating wider contexts in the input passage. 

1. **Harvesting paragraph-level question-answer pairs from wikipedia.** ACL, 2018. [paper](https://arxiv.org/pdf/1805.05942.pdf) [code&dataset](https://github.com/xinyadu/HarvestingQA)
    
    *Xinya Du, Claire Cardie*

### [Other Directions](#other-model)

1. **Cross-Lingual Training for Automatic Question Generation.** ACL, 2019. [paper](https://arxiv.org/pdf/1906.02525.pdf) [dataset](https://www.cse.iitb.ac.in/̃ganesh/HiQuAD/clqg/)
   
   *Vishwajeet Kumar, Nitish Joshi, Arijit Mukherjee, Ganesh Ramakrishnan, Preethi Jyothi*

## [Applications](#applications)

### [Difficulty Controllable QG](#difficulty-controllable-QG)

Endowing the model with the ability to control the difficulty of the generated questions. 

1. **Easy-to-Hard: Leveraging Simple Questions for Complex Question Generation.** arxiv, 2019. [paper](https://arxiv.org/pdf/1912.02367.pdf)

    *Jie Zhao, Xiang Deng, Huan Sun.*
    
### [Conversational QG](#conversational-QG)

Learning to generate a series of coherent questions grounded in a question answering style conversation. 

1. **Learning to Ask Questions in Open-domain Conversational Systems with Typed Decoders.** ACL, 2018. [paper](https://arxiv.org/pdf/1805.04843.pdf) [code](https://github.com/victorywys/Learning2Ask_TypedDecoder) [dataset]( http://coai.cs.tsinghua.edu.cn/hml/dataset/)
   
   *Yansen Wang, Chenyi Liu, Minlie Huang, Liqiang Nie*

### [Asking special questions](#asking-special-questions)

This direction focuses on exploring how to ask special types of questions, such as mathematical questions, open-ended questions, non-factoid questions, and clarification questions. 

1. **Are You Asking the Right Questions? Teaching Machines to Ask Clarification Questions.** ACL Workshop, 2017. [paper](https://www.aclweb.org/anthology/P17-3006.pdf)
   
   *Sudha Rao*

### [Answer-unaware QG](#answer-unaware-QG)

In answer-unaware QG, the model does not require the target answer as an input to serve as the focus of asking. Therefore, the model should automatically identify question-worthy parts within the passage to ask. 

1. **Learning to ask: Neural question generation for reading comprehension.** ACL, 2017. [paper](https://www.aclweb.org/anthology/P17-1123.pdf)

    *Xinya Du, Junru Shao, Claire Cardie.*
    
### [Unanswerable QG](#unanswerable-QG)

Learning to generate questions that cannot be answered by the input passage. 

1. **Learning to Ask Unanswerable Questions for Machine Reading Comprehension.** ACL, 2019. [paper](https://www.aclweb.org/anthology/P19-1415.pdf)
   
   *Haichao Zhu, Li Dong, Furu Wei, Wenhui Wang, Bing Qin, Ting Liu*

### [Combining QA and QG](#Combining-QA-and-QG)

This direction investigate how to combine the task of QA and QG by multi-task learning or joint training. 

1. **Question Generation for Question Answering.** EMNLP,2017. [paper](https://www.aclweb.org/anthology/D17-1090)
   
   *Nan Duan, Duyu Tang, Peng Chen, Ming Zhou*

### [QG from knowledge graphs](#QG-from-knowledge-graphs)

This direction is about generating questions from a knowledge graph. 

1. **Generating Factoid Questions With Recurrent Neural Networks: The 30M Factoid Question-Answer Corpus.** ACL, 2016. [paper](https://arxiv.org/pdf/1603.06807.pdf) [dataset](https://www.agarciaduran.org)
   
   *Iulian Vlad Serban, Alberto García-Durán, Çaglar Gülçehre, Sungjin Ahn, Sarath Chandar, Aaron C. Courville, Yoshua Bengio*

### [Visual Question Generation](#visual-question-generation)

Asking questions based on visual inputs (usually an image). 

1. **Generating Natural Questions About an Image** ACL, 2016. [paper](https://arxiv.org/pdf/1603.06059.pdf)
   
   *Nasrin Mostafazadeh, Ishan Misra, Jacob Devlin, Margaret Mitchell, Xiaodong He, Lucy Vanderwende*

### [Distractor Generation](#distractor-generation)

Learning to generate distractors for multi-choice questions. 

1. **Generating Questions and Multiple-Choice Answers using Semantic Analysis of Texts.** COLING, 2016. [paper](https://www.aclweb.org/anthology/C16-1107.pdf)

   *Jun Araki, Dheeraj Rajagopal, Sreecharan Sankaranarayanan, Susan Holm, Yukari Yamakawa, Teruko Mitamura*

## [Evaluation](#evaluation)

This direction investigates the mechanism behind question asking, and how to evaluate the quality of generated questions. 

1. **Question Asking as Program Generation.** NeurIPS, 2017. [paper](https://arxiv.org/pdf/1711.06351.pdf)
   
   *Anselm Rothe, Brenden M. Lake, Todd M. Gureckis.*


## [Resources](#resources)

QG-specific datasets and toolkits. 

1. **LearningQ: A Large-Scale Dataset for Educational Question Generation.** ICWSM, 2018. [paper](https://yangjiera.github.io/works/icwsm2018.pdf)
   
   *Guanliang Chen, Jie Yang, Claudia Hauff, Geert-Jan Houben.*



