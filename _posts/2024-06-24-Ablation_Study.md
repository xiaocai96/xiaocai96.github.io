---
title: 'Ablation Study'
date: 2024-06-24
permalink: /posts/2024/blog-5
tags:
  - Research
---

在知乎上看到一个关于消融实验的通俗易懂的解释


Ablation Study目的其实就是为了控制变量。

比如说你为了提升baseline的性能，给它加了两个模块A,B，加完之后效果果然提高了很多。于是你急急忙忙开始写论文，写到你的贡献，你给了两条：1.模块A，2.模块B。

但是这样写有个问题：尽管AB同时加上去对模型有提升效果，但是你并没有证明A、B两个模块分别都是有意义的。

所以为了验证A、B两个模块是不是真的都有用，你需要做ablation study。方法也很简单：

- 在baseline的基础上加上模块A，看效果。
- 在baseline的基础上加上模块B，看效果。
- 在baseline的基础上同时加上模块AB，看效果。

然后结果可能是，实验1和实验2的结果都不如实验3，那么说明AB都是有用的；然而也有可能你会发现实验1的结果和实验3一样，甚至更好。这就说明你的想法是有问题的，模块B其实并没有起到作用，提升只来自于模块A。

综上所述，ablation study就是你在同时提出多个思路提升某个模型的时候，为了验证这几个思路分别都是有效的，做的控制变量实验的工作。


An ablation study typically refers to removing some “feature” of the model or algorithm, and seeing how that affects performance.

Examples:

- An LSTM has 4 gates: feature, input, output, forget. We might ask: are all 4 necessary? What if I remove one? Indeed, lots of experimentation has gone into LSTM variants, the GRU being a notable example (which is simpler).
- If certain tricks are used to get an algorithm to work, it’s useful to know whether the algorithm is robust to removing these tricks. For example, DeepMind’s original DQN paper reports using (1) only periodically updating the reference network and (2) using a replay buffer rather than updating online. It’s very useful for the research community to know that both these tricks are necessary, in order to build on top of these results.
- If an algorithm is a modification of a previous work, and has multiple differences, researchers want to know what the key difference is.
- Simpler is better (inductive prior towards simpler model classes). If you can get the same performance with two models, prefer the simpler one.