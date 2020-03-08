# Commonsense-Paper-List
A summary of must-read papers for Commonsense

- Contributed by **[Jingyun Xu]**.

## Datasets

| Dataset                                          | Task                    | Language        | Size                           |
| ------------------------------------------------ | ----------------------- | --------------- | ------------------------------ |
| [The Winograd Schema Challenge (WSC, AAAI workshop, 2011)](#WSC)     | Pronoun Disambiguation      | English | 285 questions        |
| [Pronoun Disambiguation Problems  (PDP, AAAI workshop, 2011)](#WSC)     | Pronoun Disambiguation   | English | 60 questions        |
| [Choice of Plausible Alternatives  (COPA, AAAI workshop, 2011)](#COPA)  | Commonsense Causal Reasoning   | English | -- questions    |
| [ROCStories (NAACL, 2016)](#Story-Cloze-Test)  | Story Understanding   | English | 49255 stories |
| [JHU Ordinal Common-sense Inference (JOCI, TACL, 2017)](#JOCI)  | --   | English | -- |
| [Event2Mind (ACL, 2018)](#Event2Mind)  | Commonsense Inference on **Events, Intents, and Reactions**   | English | 24,716 events |


## Baselines

| Model                                          | DataSet                    | Performance-1        | Performance-2                           |
| ------------------------------------------------ | ----------------------- | --------------- | ------------------------------ |
| [UDSSM (NAACL, 2019)](#UDSSM)     | WSC       | 59.2% (ensemble: 62.4% ) |                        |
| [UDSSM (NAACL, 2019)](#UDSSM)                         | PDP         | 75% (ensemble: 78.3% ) |                        |
| [IE+MSA(CA) (AAAI, 2019)](#IE+MSA(CA))             | ROCStories    | BLEU-1:0.2682, BLEU-2: 0.0327  |Logic.: 1.26             |
| [ConvNet (ACL, 2018)](#Event2Mind)             | Event2Mind (baseline)    | Average Cross-Ent: 4.25  |         |

Event2Mind
 
## [Papers](#papers)

<table>
<tr><td colspan="2"><a href="#survey-papers">1. Survey</a></td></tr> 
<tr><td colspan="2"><a href="#commonsense-knowledge-Acquisition">2. Commonsense Knowledge Acquisition</a></td></tr>
<tr>
    <td>&emsp;<a href="#Commonsense-Knowledge-Generation">2.1 Commonsense Knowledge Generation</a></td>
    <td><a href="#Commonsense-Knowledge-Updating">2.2 Commonsense Knowledge Updating</a></td>
</tr>
<tr><td colspan="2"><a href="#Commonsense-Making-and-Explanation">3. Commonsense Making and Explanation</a></td></tr> 
<tr><td colspan="2">&emsp;<a href="#Direct-Sense-Making-and-Explanation">3.1 Direct Sense Making and Explanation</a></td></tr>
<tr><td colspan="2">&emsp;<a href="#Indirect-Sense-Making">3.2 Indirect Sense Making</a></td></tr>
    <tr>
    <td colspan="2">&emsp;&emsp;<a href="#Representation">3.2.1 Representation</a></td>
</tr>
    <tr>
    <td>&emsp;&emsp;&emsp;<a href="#Pre-trained-Language-Models">3.2.1.1 Pre-trained Language Models</a></td>
    <td><a href="#Event-Representation">3.2.1.2 Event Representation</a></td>
</tr>
        <tr>
    <td colspan="2">&emsp;&emsp;<a href="#Specific-Task">3.2.2 Specific Tasks</a></td>
</tr>
    <tr>
    <td colspan="2">&emsp;&emsp;&emsp;<a href="#Commonsense-Reasoning">3.2.2.1 Commonsense Reasoning</a></td>
</tr>
        <tr>
    <td>&emsp;&emsp;&emsp;<a href="#Textual-Commonsense-Reasoning">3.2.2.1.1 Textual Commonsense Reasoning</a></td>
    <td><a href="#Visual-Commonsense-Reasoning">3.2.2.1.2 Visual Commonsense Reasoning</a></td>
</tr>
    <tr><td>&emsp;&emsp;&emsp;<a href="#Commonsense-Question-Answering">3.2.2.2 Commonsense Question Answering</a></td>
    <td><a href="#Commonsense-Reading-Comprehension">3.2.2.3 Commonsense Reading Comprehension</a></td></tr>
        <tr><td>&emsp;&emsp;&emsp;<a href="#Understanding-of-Commonsense-Stories">3.2.2.4 Understanding of Commonsense Stories</a></td>
            <td><a href="#Sentiment-Analysis">3.2.2.5 Sentiment Analysis</a></tr>
       <tr><td>&emsp;&emsp;&emsp;<a href="#Dialogue">3.2.2.6 Dialogue </a></td>
       <td><a href="#Abstractive-Summarization">3.2.2.7 Abstractive Summarization</a></td></tr>
     <tr><td colspan="2">&emsp;&emsp;&emsp;<a href="#Text-Generation">3.2.2.8 Text Generation</a></td>
</tr>
   <tr>  <td colspan="2">&emsp;&emsp;&emsp;<a href="#Others">3.2.2.9 Others</a></td></tr>
        <tr>
    <td>&emsp;&emsp;&emsp;<a href="#Textual Taks">3.2.2.9.1 Textual Tasks</a></td>
    <td><a href="#Visual Tasks">3.2.2.9.2 Visual Tasks</a></td>
</tr>
</table>

## [Survey papers](#content)

## [Commonsense Knowledge Acquisition](#content)   
How to generate knowledge, from scratch (Commonsense Knowledge Generation) ? or based on existed ones (Commonsense Knowledge Updating) ?
### [Commonsense Knowledge Generation](#content)
1. **ATOMIC: An Atlas of Machine Commonsense for If-Then Reasoning.** AAAI, 2019. [paper](https://aaai.org/ojs/index.php/AAAI/article/view/4160) [dataset](https://homes.cs.washington.edu/~msap/atomic/)
    
    *Maarten Sap, Ronan Le Bras, Emily Allaway, Chandra Bhagavatula, Nicholas Lourie, Hannah Rashkin, Brendan Roof, Noah A. Smith, Yejin Choi.* 

This is a commonsense knowledge base, which cares about the If-Then relations.
    
2. **Commonsense Properties from Query Logs and Question Answering Forums.** CIKM, 2019. [paper](https://dl.acm.org/doi/10.1145/3357384.33579559) [dataset&code](https://github.com/Aunsiels/CSK)
    
    *Julien Romero, Simon Razniewski, Koninika Pal, Jeff Z. Pan, Archit Sakhadeo, Gerhard Weikum.* 
    
3. **CA-EHN: Commonsense Word Analogy from E-HowNet.** arxiv, 2019. [paper](https://arxiv.org/abs/1908.07218) [dataset](https://github.com/jacobvsdanniel)
    
    *Peng-Hsuan Li, Tsan-Yu Yang, Wei-Yun Ma.* 
    
Actually, I don not get the dataset. -- 2020.2.23

4. **A Logical Model for Supporting Social Commonsense Knowledge Acquisition.** arxiv, 2019. [paper](https://arxiv.org/abs/1912.11599) 
    
    *Maarten Sap, Ronan Le Bras, Emily Allaway, Chandra Bhagavatula, Nicholas Lourie, Hannah Rashkin, Brendan Roof, Noah A. Smith, Yejin Choi.* 
    
5. **Automatic Extraction of Commonsense LocatedNear Knowledge.** ACL, 2018. [paper](https://www.aclweb.org/anthology/P18-2016/) [dataset&code](https://github.com/adapt-sjtu/commonsense-locatednear)
    
    *Frank F. Xu, Bill Y. Lin, Kenny Q. Zhu.* 
    
6. **Extracting Commonsense Properties from Embeddings with Limited Human Guidance.** ACL, 2018. [paper](https://www.aclweb.org/anthology/P18-2102/) [dataset&code](https://github.com/yangyiben/PCE) [presentation](https://vimeo.com/285805855/) [slide](https://www.aclweb.org/anthology/attachments/P18-2102.Presentation.pdf/)
    
    *Yiben Yang, Larry Birnbaum, Ji-Ping Wang, Doug Downey.* 
    
7. **Acquiring Common Sense Spatial Knowledge Through Implicit Spatial Templates.** AAAI, 2018. [paper](https://www.aaai.org/ocs/index.php/AAAI/AAAI18/paper/view/16232) [dataset&code](https://github.com/gcollell/spatial-commonsense)
    
    *Guillem Collell, Luc Van Gool, Marie-Francine Moens.* 
 8. **ConceptNet 5.5: An Open Multilingual Graph of General Knowledge.** AAAI, 2017. [paper](http://aaai.org/ocs/index.php/AAAI/AAAI17/paper/view/14972) [dataset](http://conceptnet.io/) [code](https://github.com/commonsense/conceptnet5) 
    
    *Robyn Speer, Joshua Chin, Catherine Havasi.* 
 9. **The "Something Something" Video Database for Learning and Evaluating Visual Common Sense.** ICCV, 2017. [paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8237884) 
 
    *Raghav Goyal, Samira Ebrahimi Kahou, Vincent Michalski, Joanna Materzynska, Susanne Westphal, Heuna Kim, Valentin Haenel, Ingo Fründ, Peter Yianilos, Moritz Mueller-Freitag, Florian Hoppe, Christian Thurau, Ingo Bax, Roland Memisevic.* 
 10. **Stating the Obvious: Extracting Visual Common Sense Knowledge.** NAACL, 2016. [paper](https://www.aaai.org/ocs/index.php/FLAIRS/FLAIRS16/paper/view/12785)
 
     *Mark Yatskar, Vicente Ordonez, Ali Farhadi.* 
   
 11. **GECKA3D: A 3D Game Engine for Commonsense Knowledge Acquisition.** FLAIRS Conference, 2016. [paper](https://www.aaai.org/ocs/index.php/FLAIRS/FLAIRS16/paper/view/12785)
 
     *Erik Cambria, Tam V. Nguyen, Brian Cheng, Kenneth Kwok, Jose Sepulveda.* 
    
### [Commonsense Knowledge Updating](#content)
 1. **Joint Reasoning for Multi-Faceted Commonsense Knowledge.** arxiv, 2020. [paper](https://arxiv.org/abs/2001.04170)
 
     *Erik Cambria, Tam V. Nguyen, Brian Cheng, Kenneth Kwok, Jose Sepulveda.* 

## [Commonsense Making and Explanation](#content)   
### [Direct Sense Making and Explanation](#content)
### [Indirect Sense Making](#content)
#### [Representation](#content)
##### [Pre-trained Language Models](#content)
##### [Event Representation](#content)
#### [Specific Tasks](#content)
##### [Commonsense Reasoning](#content)
###### [Textual Commonsense Reasoning](#content)
 1. <span id = "WSC">**The Winograd Schema Challenge.**</span> AAAI workshop, 2011. [paper](https://www.aaai.org/ocs/index.php/SSS/SSS11/paper/view/2502/2964)
 
     *Hector J. Levesque.* 
     > It includes two datasets: Pronoun Disambiguation Problems (PDP) and Winograd Schema Challenge. Example:  
     The city councilmen refused the demonstrators a permit because they feared violence.  
     Who feared violence?  
     A. The city councilmen B. The demonstrators

 2. <span id = "UDSSM">**Unsupervised Deep Structured Semantic Models for Commonsense Reasoning.**</span> ACL, 2019. [paper](https://www.aclweb.org/anthology/N19-1094.pdf)
 
     *Wang, Shuohang and Zhang, Sheng and Shen, Yelong and Liu, Xiaodong and Liu, Jingjing and Gao, Jianfeng and Jiang, Jing.* 
 3. <span id = "COPA">**Choice of Plausible Alternatives: An Evaluation of Commonsense Causal Reasoning.**</span> AAAI workshop, 2011. [paper](https://www.aaai.org/ocs/index.php/SSS/SSS11/paper/view/2418/2960)
 
     *Roemmele, Melissa and Bejan, Cosmin Adrian and Gordon, Andrew S.* 
     > The input is a premise, and the output are alternatives of one has casual relation with the premise. The answer is the effect or the cause of the premise.     
     Example:   
     (forward causal reasoning)         
     Premise: The man lost his balance on the ladder.    
     What happened as a result?   
     Alternative 1: He fell off the ladder.     
     Alternative 2: He climbed up the ladder.      
     (backwards causal reasoning)      
     Premise: The man fell unconscious.    
     What was the cause of this?    
     Alternative 1: The assailant struck the man in the head.   
     Alternative 2: The assailant took the man’s wallet. 
 4. <span id = "JOCI">**Ordinal Common-sense Inference.**</span> TACL, 2017. [paper](https://transacl.org/ojs/index.php/tacl/article/view/1082/255) 
 
     *Zhang, Sheng and Rudinger, Rachel and Duh, Kevin and Van Durme, Benjamin.* 
     
       > This dataset evaluates commonsense inference by predicting the ordinal likelihood of a hypothesis given a context.
       
 5. <span id = "Event2Mind">**Event2Mind: Commonsense Inference on Events, Intents, and Reactions.**</span> ACL, 2018. [paper](https://www.aclweb.org/anthology/P18-1043.pdf) [dataset](https://tinyurl.com/event2mind)
 
     *Rashkin, Hannah and Sap, Maarten and Allaway, Emily and Smith, Noah A and Choi, Yejin.* 
     
       > This dataset evaluates commonsense inference on mental states of event participants.   
       Example:
       Inputs: PersonX reads PersonY's diary   
       Outputs:
       PersonX's **intent**: to be nosey, know secrets    
       PersonX's **reaction**: guilty, curious
       PersonY's **reaction**:angry, violated, betrayed
 6. <span id = "KagNet">**KagNet: Knowledge-Aware Graph Networks for Commonsense Reasoning.**</span> EMNLP, 2019. [paper](https://arxiv.org/abs/1909.02151) 
 
     *Bill Yuchen Lin, Xinyue Chen, Jamin Chen, Xiang Ren.* 
     
###### [Visual Commonsense Reasoning](#content)
##### [Commonsense Question Answering](#content)
##### [Commonsense Reading Comprehension](#content)
##### [Understanding of Commonsense Stories](#content)
 1. <span id = "Story-Cloze-Test">**A Corpus and Cloze Evaluation for Deeper Understanding of Commonsense Stories.**</span> NAACL, 2016. [paper](https://www.aclweb.org/anthology/N16-1098.pdf) [dataset](http://cs.rochester.edu/nlp/rocstories)
 
     *Mostafazadeh, Nasrin and Chambers, Nathanael and He, Xiaodong and Parikh, Devi and Batra, Dhruv and Vanderwende, Lucy and Kohli, Pushmeet and Allen, James.* 
     
       > The input is a story, and the output are alternatives of one is the end of the stories.
       
 2. <span id = "IE+MSA(CA)">**Story Ending Generation with Incremental Encoding and Commonsense Knowledge.**</span> AAAI, 2019. [paper](https://www.aaai.org/ojs/index.php/AAAI/article/view/4612) [code](https://github.com/JianGuanTHU/StoryEndGen.)
 
     *Guan, Jian and Wang, Yansen and Huang, Minlie.* 
##### [Sentiment Analysis](#content)
##### [Dialogue](#content)
##### [Abstractive Summarization](#content)
##### [Text Generation](#content)
##### [Others](#content)
###### [Textual Tasks](#content)
###### [Visual Tasks](#content)
