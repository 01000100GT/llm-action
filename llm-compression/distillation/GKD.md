


图 1：在 XSum summarization 上比较 GKD 与常见的蒸馏方法。 我们使用经过监督微调（FT）训练的 T5 模型作为蒸馏的学生模型。 

有监督的 KD 和有监督的 FT 使用带有ground-truth摘要的 XSum 训练数据集，但 KD 可以查询教师以获得概率，而 FT 则不能。 

此外，on-policy 方法来自学生的样本摘要，而'Mixed'是指从真实情况和学生生成的摘要中进行统一采样。

ImitKD 对应于使用 Forward KL 的'Mixed'采样。 正如第 2 节中所讨论的，具有反向 KL 和广义 JS 散度 (JSD) 的 GKD 优于其他方法。








---



用于自回归序列模型的广义知识蒸馏



动机：

当前的自回归模型知识蒸馏方法存在两个关键问题：
1. 训练期间的输出序列与学生在部署期间生成的序列之间的分布不匹配；
2. 模型规格不足，即学生模型可能无法表达教师的分布。

为了解决这些问题，本文提出广义知识蒸馏(GKD)。

方法：

通过在训练期间从学生中采样输出序列来缓解分布不匹配。此外，GKD通过优化替代差异，如反向KL，这些差异专注于生成来自学生的样本，这些样本
在教师的分布下可能。

本文证明GKD在摘要、机器翻译和算术推理任务上超越了常用的LLM蒸馏方法。 

优势：所提出方法在自然语言生成任务上的表现一直优于更常用的知识蒸馏基线。进一步展示了该方法可以与强化学习结合，以优化序列级奖励，除了蒸馏大型教师模型的知识。



提出一种名为广义知识蒸馏(GKD)的方法，可以解决自回归模型在知识蒸馏过程中面临的分布不匹配和模型规格不足的问题，在自然语言生成任务上的表现一直优于更常用的知识蒸馏基线。




