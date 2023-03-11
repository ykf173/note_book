### 2020年初代GPT3

* 能力：计算能力，可以生成简单的文章
* 训练数据： 
  * 训练语料的60%来自于 2016 - 2019 的 C4 + 22% 来自于 WebText2 + 16% 来自于Books + 3%来自于Wikipedia
* 超能力来源于钞能力
  * **语言生成**的能力来自于语言建模的**训练目标** (language modeling)
  * **世界知识**来自 3000 亿单词的**训练语料库**
  * **模型的 1750 亿参数**是为了**存储知识**
* GPT-3（在 OpenAI API 中被称为`davinci`）
* 大模型：OPT  <  text-davinci-002 
* GPT3 后续
  * 代码训练
  * 指令微调 (instruction tuning) 
  * 基于人类反馈的强化学习 (reinforcement learning with human feedback, RLHF) 

### 2022版chatGPT

* 发展路线[OpenAI的模型索引文档](https://platform.openai.com/docs/models/overview)

  ![](assets/640.jpeg)

|中文|英文|备注|
| :------: | :--: | :------: |
|Emergent Ability|突现能力|小模型没有，只有模型大到一定程度才会出现的能力|
|prompt|提示词|把prompt输入给大模型，大模型给出completion|
|In-Context-Learning|上下文学习|在prompt里写几个例子，模型就可以照着这些例子生成结果|
|Chain-fo-Thought|思维链|在写prompt的时候，不仅给出结果，还要一步一步地写结果是怎么推导出来的|
|Scaling Laws|缩放法则|模型的效果的线性增长<br/>求模型的大小呈指数增长|
|Parameter-efficient Adaptation|高效参数适应|在固定住大模型参数的情况下，增加少量的新参数进行精调|
|Distribution Shift|分布转换|在一种数据分布上进行训练，在另一种数据分布上测试|
|Instruction Tuning|指令精调|用指令精调大模型|
|Code Tuning|在代码上精调|用代码精调大模型|