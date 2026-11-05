# ResNet-18 学习项目

使用 PyTorch 手动搭建适用于 CIFAR-10 的 ResNet-18，
学习残差连接、模型训练与评估，并使用 Git 和 GitHub 管理代码。

## 网络结构

- 自定义 BasicBlock，支持原样捷径和投影捷径
- 四个阶段，每个阶段包含两个残差块
- 开头使用 3×3 卷积，步长为 1，不使用最大池化
- 全局平均池化后，通过全连接层输出 10 个类别分数

## 运行环境

- Python 3.11
- PyTorch 2.7.1+cu118
- torchvision 0.22.1+cu118
- GPU：NVIDIA GeForce RTX 3050 Laptop GPU

## 数据准备

将 CIFAR-10 解压后的文件夹放在以下位置：

```text
ResNet/
├── resnet.ipynb
├── README.md
├── .gitignore
└── data/
    └── cifar-10-batches-py/
```

数据集和训练权重由 `.gitignore` 忽略，不包含在仓库中。

## 运行方式

打开 `resnet.ipynb`，选择已安装 PyTorch 的 Python 环境，
按顺序执行单元格。

## 初步结果

训练 1 个 epoch 后：

| 指标 | 结果 |
|---|---:|
| 训练平均损失 | 1.2774 |
| 训练准确率 | 54.21% |
| 测试损失 | 0.8864 |
| 测试准确率 | 68.10% |

训练指标是在整轮参数持续更新的过程中累计得到的；
测试指标使用该轮结束后的模型计算。

## 后续计划

- 学习迁移学习和模型微调
- 添加验证集与数据增强
- 绘制训练曲线