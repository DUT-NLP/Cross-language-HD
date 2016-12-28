# 跨语言模糊限制语检测
## CHIR
在词语义表示（Word Semantic Representations，WSR）基础上，引入上下文模糊限制信息表示（Context Hedge Information Representations，CHIR），联合学习在特定语境下的模糊限制信息。<br>
首先，基于英文模糊限制语训练语料抽取英文模糊限制语词典，将英文模糊限制语词典翻译为中文，获得中文模糊限制语词典。<br>
然后，利用英文和中文模糊限制语词典，分别抽取中英文训练语料和测试语料中的模糊限制语候选词。<br>
最后，将跨语言模糊限制语识别任务的上下文模糊信息表示定义为：如果句子中出现两个或两个以上候选词，上下文模糊信息表示为该句中候选词的语义
表示相加。如果句子中只有一个候选词，上下文模糊信息表示为与词表示维度相同的零向量 0。

## Details
For more information about Long-short memory network, you can visit <http://deeplearning.net/tutorial/lstm.html#lstm><br>
In our work, we adopt an LSTM variant, which adds the "peephole connections" to the architecture [Gers and Schmidhuber,2000]<br> 
![peeohole] (https://github.com/DUT-NLP/Cross-language-HD/blob/master/peephole.png)
## Dataset 
实验采用 CoNLL 2010 的模糊限制语识别任务中的生物医学领域语料作为英文训练语料。该语料包括生物医学领域的摘要和
全文语料。中文测试语料采用Zhou等构建的中文模糊限制语语料库(CHedge)
## Requriments
python 2.7.11 and theano 0.8.2  

## Reference
Felix A. Gers and Jürgen Schmidhuber. 2000. Recurrent nets that time and count. In Proceedings of Neural Networks.IEEE-INNS-ENNS International Joint Conference on, 3:189–194
