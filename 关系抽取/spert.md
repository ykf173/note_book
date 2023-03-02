# Span-based Joint Entity and Relation Extraction with Transformer Pre-training

* 1. 模型

     ![image-20230224134133086](/Users/langming/我的/private/笔记/picture/spert模型图.png)

     * Span classification（区间分类）

       > 1. 将区间提前映射到提前定义好的标签空间，包含None，即负样本。
       >
       > 2. 分类器输入为：$X^s=e(s)\circ \boldsymbol{c}$
       >
       >    而 $e(s) = f(e_i, e_{i+1}, \ldots, e{i+k})\circ w_{k+1} \tag{1}$
       >
       >    其中： $\circ$表示向量连接运算，$w_{k+1}$表示$k+1$的宽度向量
       >
       >    c表示分类的特殊标记CLS
       >
       >    分类器输出为：
       >
       >    $$\hat{y}^{s}=softmax(W^s \cdot x^s + b^s)\tag{2}$$
       >
       >    * $w_{k+1}$通过一个宽度span向量反向传播得到
       >
       
     * Span filtering（区间过滤）
  
       > 　通过模型输出概率大小进行过滤
  
     * Relation classification（关系分类）
  
       > 1. 通过拼接bert编码输出以及 $w_{k+1}$ 得到关系分类器输入$e_(s_1)$，  $e_(s_2)$
       >
       > 2. 关系通过bert输出经过max-pooling层得到，其中关系位于$s_1$ 与 $s_2$之间，表示为$\boldsymbol{c}_{(s_1,s_2)}$，实体重叠时，$\boldsymbol{c}_{(s_1,s_2)}={None}$
       >
       > 3. 计算方式如下：
       >
       >    $$\boldsymbol{x}^r_1=\boldsymbol(s_1) \circ \boldsymbol(c(s_1,s_2)) \circ e(s_2)  \tag{3}$$
       >
       >    $$\boldsymbol{x}^r_2=\boldsymbol(s_2) \circ \boldsymbol(c(s_1,s_2)) \circ e(s_1) \tag{4}$$
       >
       >    $$\hat{y_{1/2}^r}=\sigma(W^r \cdot \boldsymbol{x}^r_{1/2} + b^r)$$
       >    
       >    其中$\sigma$表示sigmoid，设定阈值$\alpha$
       >
  
  2. 训练
  
     1. 总的损失:        $\mathcal{L} = \mathcal{L}^s+\mathcal{L}^t$
  
        其中$\mathcal{L}^s$表示span分类器的交叉熵计算，$\mathcal{L}^t$表示关系分类器的交叉熵计算
  
     2. 负样本构建：
        * 实体负样本，对于标注的实体以外的span乘以一个随机数$N_r$，得到实体分类器的负样本
        * 关系负样本，对于标注的实体以外的span乘以一个随机数$N_r$，得到实体分类器的负样本                                                                                                                                              
  
  3. 数据
  
  4. 实验
  
     ![image-20230225200018387](/Users/langming/我的/private/笔记/关系抽取/assets/image-20230225200018387.png)