## NeuraTrans: An Interactive Neural Machine Transition App
+ [1. Introduction](#1-introduction)
+ [2. App Demo](#2-App-Demo)
+ [3. Model Training](#3-Model-Training)

### 1. Introduction
+ Developed an interactive bilingual translation app utilizing **Recurrent Neural Networks (RNN) and Transformer models** for neural machine translation.
+ Trained a sequence-to-sequence model for translating Chinese Mandarin to English using Anki data.

### 2. App Demo
Using the interactive translation app deployed with Gradio, you can input a sentence in Chinese and receive the output in English. The demo model is trained using the Transformer architecture.
![demo](demo/NMT%20Demo.gif)

### 3. Model Training
In the notebook [Neural_Machine_Translation.ipynb](https://github.com/xiaorandu/neural_machine_translation/blob/main/Neural_Machine_Translation.ipynb), machine translation is performed by using two deep learning approaches: a Recurrent Neural Network (RNN) and Transformer. Specifically, the Anki data for Chinese Mandarin to English translation is trained using sequence-to-sequence models. 

Encoder and decoder models for Recurrent Neural Network (RNN) and Transformer are implemented. The notebook also demonstrates the data pre-processing, model training, model inference, and model evaluation on sentence translations from Chinese Mandarin to English. The data contains 29909 bilingual pairs from Anki data.

Here are some examples of the pre-processed data:
```
                         eng	                                  cmn
0	<start> i don't think that it's good . <end>	         <start> 我 不 觉 得 它 很 好 。 <end>
1	<start> do you know the concert schedule of lo...	     <start> 你 知 道 伦 敦 交 响 乐 团 的 演 奏 会 行 程 吗 ？ <end>
2	<start> tom told me that mary is leaving tomor...	     <start> 汤 姆 和 我 说 明 天 玛 丽 会 离 开 。 <end>
3	<start> tom isn't at the hotel . <end>	               <start> 汤 姆 不 在 酒 店 。 <end>
4	<start> i do not think that he will come . <end>	     <start> 我 不 認 為 他 會 來 。 <end>
```
Here are some examples of predicted English sentences compared with actual English sentences from a given Chinese Mandarin sentence for the two approaches. Loss and BLEU scores are also shown below.
+ Recurrent Neural Network (RNN)
  ```
  Source sentence: <start> 那 栋 建 筑 是 什 么 呢 ？ <end>
  Target sentence: <start> what's that building ? <end>
  Predicted sentence: <start> what's that bird ? <end>
  ----------------
  Source sentence: <start> 我 沒 聽 到 任 何 人 在 說 話 。 <end>
  Target sentence: <start> i didn't hear anyone talking . <end>
  Predicted sentence: <start> i didn't hear anyone talking . <end>
  ----------------
  Source sentence: <start> 我 發 現 了 一 些 有 趣 的 東 西 。 <end>
  Target sentence: <start> i've discovered something interesting . <end>
  Predicted sentence: <start> i've found something interesting . <end>
  ----------------
  Source sentence: <start> 這 不 是 湯 姆 要 的 嗎 ？ <end>
  Target sentence: <start> isn't this what tom asked for ? <end>
  Predicted sentence: <start> is this ? <end>
  ----------------
  Source sentence: <start> 那 里 的 气 候 怎 么 样 ? <end>
  Target sentence: <start> what's the climate there like ? <end>
  Predicted sentence: <start> how is the weather there ? <end>
  ----------------

  Loss 1.6082
  BLEU 1-gram: 0.196719
  BLEU 2-gram: 0.062080
  BLEU 3-gram: 0.047848
  BLEU 4-gram: 0.045530
  ```
+ Transformer
  ```
  Source sentence: <start> 我 昨 晚 应 该 早 点 睡 觉 的 。 <end>
  Target sentence: <start> i should've gone to bed earlier last night . <end>
  Predicted sentence: <start> i should've been feeling last night . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> .
  ----------------
  Source sentence: <start> 汤 姆 和 玛 丽 拥 有 一 个 小 型 的 有 机 农 场 。 <end>
  Target sentence: <start> tom and mary own a small organic farm . <end>
  Predicted sentence: <start> tom and mary have a small organic farm . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> .
  ----------------
  Source sentence: <start> 我 知 道 湯 姆 餓 了 。 <end>
  Target sentence: <start> i know that tom is hungry . <end>
  Predicted sentence: <start> i know tom is hungry . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end>
  ----------------
  Source sentence: <start> 汤 姆 确 定 那 里 会 有 很 多 人 。 <end>
  Target sentence: <start> tom didn't doubt that there would be a lot of people there . <end>
  Predicted sentence: <start> tom is certain that he will be there . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> .
  ----------------
  Source sentence: <start> 我 不 会 放 弃 你 的 。 <end>
  Target sentence: <start> i won't abandon you . <end>
  Predicted sentence: <start> i won't abandon you . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> . <end> you . <end> you .
  ----------------

  Loss 2.3302
  BLEU 1-gram: 0.202575
  BLEU 2-gram: 0.059269
  BLEU 3-gram: 0.042997
  BLEU 4-gram: 0.039652
  ```
