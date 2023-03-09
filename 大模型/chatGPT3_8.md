> * **devinci**（GPT3初代）--->[**code-davinci-001** ，**code-cushman-001[12b]**]（Codex论文）--->  [**instruct-davinci-beta**，**text-devinci-001** ]（指令微调instructGPT论文）---> [**code-devinci-002**]（beta测试，Codex）--->[**text-davinci-002**]（SFT）---> [**text-davinci-003**，**ChatGPT**]（RLHF）
> * Code-davinci-002：上下文学习能力，coding能力
> * Text-davinci-003:加入语言建模（LM），有监督精调（SFT），零样本学习能力增强，上下文学习能力减弱
> * chatGPT：对话能力增强，上下文学习能力减弱

指令微调：解锁/激发原有能力，在大量数据的预训练的情况下，模型已经具备了各种能力，是通过指令微调激发出来的。

Alignment tax：对齐税



**在`code-davinci-002`上进行指令微调后，模型可以生成更加符合人类期待的反馈（或者说模型与人类对齐），例如：零样本问答、生成安全和公正的对话回复、拒绝超出模型它知识范围的问题。**这应该是我们所需要的



### `code-davinci-002`与`text-davinci-002`

* 相应人类指令
* 泛化到人类未见过的任务
* 代码生成和代码理解
* 利用思维链（chain-of-thought）进行复杂推理：解锁