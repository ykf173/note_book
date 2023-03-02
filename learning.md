## 1. $$self-attention = softmax(\frac{QK^T}{\sqrt{d_k}})$$

### $\sqrt{d_k}$作用

> * 计算$QK^T$结果接近one-hot分布，将会带来严重的梯度消失问题
> * 如果这里不除，初始化时，初始化方差需要多除一个$\sqrt{d_k}$，从而使得方差为1

> * 熵不变性，为了保证注意力分摊均匀

## 2. Prompt应用

> * 噪声检测
> * 预标注



