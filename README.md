**IMDB 電影評論情緒分析**
===
大家早安午安晚安，我是 Yi-Hong ，這篇 NOTEBOOK 將會包含我對這篇Notebook包含我對IMDB的評論做出的情緒分析

### 資料簡介

這份IMDB的影評資料來自standford大學在2011年發表的文章「[Learning Word Vectors for Sentiment Analysis](https://ai.stanford.edu/~amaas/papers/wvSent_acl2011.pdf)」，作為自然語言處理(NLP)的常見資料集，可從直接從library datasets取得資料。


資料包含2個部分：

1. text：影評
2. label：影評情緒，0代表負面，1代表正面。


### 模型簡介

在此我們使用BERT 模型作為處理分類的模型，但在說明BERT 之前，先說明Transformer 模型。

Transformer 是一種由Google 在2017 年提出的神經網路架構，它徹底改變了過去處理序列資料（如文字）的方式。在Transformer 出現之前，主流模型（如RNN 和LSTM）必須依序處理文字。這就像一個一個詞地閱讀句子，導致訓練速度慢，且難以處理長篇文章。 Transformer 的核心創新是注意力機制（Attention Mechanism）。它讓模型在處理某個詞時，能同時審視輸入序列中的所有詞，並判斷哪些詞與當前詞的關係最為重要。這使得模型能夠平行處理整個序列，大幅提升了訓練速度，並能有效捕捉詞彙之間的長距離語義關係。簡單來說，Transformer 提供了一套高效且強大的「語言理解藍圖」。


BERT 的全名是Bidirectional Encoder Representations from Transformers，是由Google 在2018 年提出的
預訓練模型，它的出現證明了Transformer 架構的強大潛力。BERT 成功地將Transformer 的藍圖應用在實際任務中。它的最大特點是雙向性。在訓練時，BERT 會同時參考一個詞的前後文語境來理解其含義。透過這種雙向訓練方式，BERT 能夠更全面地捕捉詞語的上下文語義，使其在多種自然語言處理任務（如情感分析、問答系統）中表現出色。


### 結果

預測結果如下

1. BERT 模型：準確率93%

|        | precision | recall | f1-score | support |
|-------:|----------:|-------:|---------:|--------:|
|Negative| 0.95      |   0.91 |  0.93    |  12500  |
|Positive| 0.91      |   0.96 |  0.93    |  12500  |
|Accuracy|           |        |  0.93    |  25000  |

如果想要瞭解 python 程式細節可以點開 NOTEBOOK ，如果只想快速瞭解結果可以點開報告觀看，謝謝大家。晚安
