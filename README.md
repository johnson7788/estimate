# Efficient Integration of Multi-Order Dynamics and Internal Dynamics in Stock Movement Prediction

[![arXiv](https://img.shields.io/badge/arXiv-2211.07400-b31b1b.svg)](https://arxiv.org/abs/2211.07400)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

深度神经网络（DNN）架构的进步使股票市场数据的新预测技术成为可能。与其他多变量时间序列数据不同，股票市场显示出两个独特的特征：(i) 多阶动态，因为股票价格受到强烈的非对等相关关系的影响（例如，在同一行业内）；(ii) 内部动态，因为每只股票显示出一些特殊的行为。最近基于DNN的方法使用超图捕捉多阶动态，但在卷积中依赖傅里叶基础，这既没有效率也没有效果。此外，它们在很大程度上忽略了内部动态，对每只股票采用相同的模型，这意味着严重的信息损失。在本文中，我们提出了一个股票走势预测的框架，以克服上述问题。具体来说，该框架包括时间生成过滤器，在LSTM网络上实现基于记忆的机制，试图学习每个股票的个别模式。此外，我们采用超图关注来捕捉非成对的关联性。在这里，使用小波基而不是傅里叶基，使我们能够简化信息传递并专注于局部卷积。用美国市场六年的数据进行的实验表明，我们的框架在利润和稳定性方面优于最先进的方法。

Please read and cite our paper: [![arXiv](https://img.shields.io/badge/arXiv-2211.07400-b31b1b.svg)](https://arxiv.org/abs/2211.07400)

#### Citation 
```
@inproceedings{huynh2023wsdm,
  author    = {Thanh Trung Huynh and Minh Hieu Nguyen and Thanh Tam Nguyen and Phi Le Nguyen and Matthias Weidlich and Quoc Viet Hung Nguyen and Karl Aberer},
  title     = {Efficient Integration of Multi-Order Dynamics and Internal Dynamics in Stock Movement Prediction},
  booktitle = {{WSDM} '23: The Sixteeth {ACM} International Conference on Web Search
               and Data Mining, Virtual Event / Singapore, February 27 - March 3,
               2023},
  publisher = {{ACM}},
  year      = {2023},
}
```

## Install environment
Init environment using conda
```
conda create -n estimate python=3.8.13
conda activate estimate
```
Install pytorch
```
conda install pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch
```
Install torch geometric: Please follow [these instructions](https://pytorch-geometric.readthedocs.io/en/latest/notes/installation.html).
For our environment, we use the command:
```
conda install pyg -c pyg
```
Install other packages:
```
pip install -r requirements.txt
```

## Train and Test
Please using the file **help.sh** for training and testing the ESTIMATE.
```
bash help.sh
```
按照说明进行操作就可以了。如果模型被训练了，预训练的文件夹就会存在。 因此，我们可以停用训练模式，只运行测试模式。
