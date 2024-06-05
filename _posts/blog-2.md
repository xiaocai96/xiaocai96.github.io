---
title: 'Conda envirenment'
date: 2012-08-14
permalink: /posts/blog-1
tags:
  - Conda
  - Tutorials
---

A tutorial for conda

虚拟环境
------
1. 查看当前存在哪些虚拟环境
```conda env list```
或
```conda info --envs```
2. 创建虚拟环境
```conda create -n [EnvName] python=3.11.4```
3. 激活虚拟环境
```conda activate [gnnEnv]```

安装包
------
1. 基础工具
```conda install tdqm pandas numpy matplotlib```
2. Pytorch with cuda 11.8
```conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia```
3. Pytorch with cpuonly
```conda install pytorch torchvision torchaudio cpuonly -c pytorch```
4. PyG
```conda install pyg -c pyg```
```pip install torch_geometric```

删除虚拟环境
------
1. 退出环境
```conda deactivate```
2. 删除环境
```conda remove -n [EnvName] -all```

其他
------
1. 查看自动电脑是否安装cuda
```nvidia-smi```
2. pip错误
ERROR: Could not find a version that satisfies the requirement xxxx(from versions: none)
ERROR: No matching distribution found for xxxx
直接选用pip源并且信任它的来源就可以解决这种问题。
```pip install 库包名 -i [http://pypi.douban.com/simple/](http://pypi.douban.com/simple/) --trusted-host [pypi.douban.com](http://pypi.douban.com/)```
3. 镜像源安装其它库
```pip install sklearn -i https://pypi.tuna.tsinghua.edu.cn/simple```
```pip install pandas -i https://mirrors.aliyun.com/pypi/simple/ --trusted-host=mirrors.aliyun.com/pypi/simple```