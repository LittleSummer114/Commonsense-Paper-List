# Natural Language Inference-Paper-List
A summary of must-read papers for Natural Language Inference 

- Contributed by **[Jingyun Xu]**.

## Datasets

| Dataset                                          | Task                    | Language        | Size                           |
| ------------------------------------------------ | ----------------------- | --------------- | ------------------------------ |
| [The Winograd Schema Challenge (WSC, AAAI workshop, 2011)](#WSC)     | Pronoun Disambiguation      | English | 285 questions        |

## Baselines

| Model                                          | DataSet                    | Performance-1        | Performance-2                           |
| ------------------------------------------------ | ----------------------- | --------------- | ------------------------------ |
| [UDSSM (NAACL, 2019)](#UDSSM)     | WSC       | 59.2% (ensemble: 62.4% ) |                        |

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
 1. <span id = "Story-Cloze-Test">**A Corpus and Cloze Evaluation for Deeper Understanding of Commonsense Stories.**</span> NAACL, 2016. [paper](https://www.aclweb.org/anthology/N16-1098.pdf) [dataset](http://cs.rochester.edu/nlp/rocstories)
 
     *Mostafazadeh, Nasrin and Chambers, Nathanael and He, Xiaodong and Parikh, Devi and Batra, Dhruv and Vanderwende, Lucy and Kohli, Pushmeet and Allen, James.* 
     
       > The input is a story, and the output are alternatives of one is the end of the stories.
