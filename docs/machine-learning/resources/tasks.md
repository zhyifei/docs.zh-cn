---
title: 机器学习任务
description: 浏览 ML.NET 中支持的不同机器学习任务。
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 875006a9cddb87b5f9436b78773420858fd842dd
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207713"
---
# <a name="machine-learning-tasks"></a>机器学习任务

在生成机器学习模型时，首先需要定义你希望通过数据实现的目标。 之后，可以根据你的实际情况选取正确的机器学习任务。 下面介绍了可以从中选择的不同机器学习任务，以及一些常见用例。 

> [!NOTE]
> ML.NET 当前处于预览状态。 目前并不支持所有机器学习任务。 若要提交请求以获取某项任务，请在 [dotnet/machinelearning 存储库](https://github.com/dotnet/machinelearning/issues)中打开一个问题。

> [!NOTE]
> 目前，ML.NET 不支持使用映像的机器学习任务。 将在未来版本中添加该支持。 

## <a name="binary-classification"></a>二元分类

[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例所属的两个类（类别）。 分类算法输入是一组标记示例，其中每个标签为整数 0 或 1。 二元分类算法的输出是一个分类器，可用于预测未标记的新实例的类。 二元分类方案示例包括：

* [了解 Twitter 评论的情绪](../tutorials/sentiment-analysis.md)，“正面”或“负面”。
* 诊断患者是否患有某种疾病。
* 决定是否要将电子邮件标记为“垃圾邮件”。

有关详细信息，请参阅 Wikipedia 上的[二元分类](https://en.wikipedia.org/wiki/Binary_classification)一文。

## <a name="multiclass-classification"></a>多类分类

[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例的类（类别）。 分类算法输入是一组标记示例。 每个标签是 0 到 k-1 之间的整数，其中 k 表示类的数目。 分类算法的输出是一个分类器，可用于预测未标记的新实例的类。 多类分类方案示例包括：

* 确定狗的品种是“西伯利亚哈士奇”、“金毛寻回犬”、“贵宾犬”等。
* 了解电影评论是“正面”、“中立”还是“负面”。
* 将酒店评语分类为“位置”、“价格”、“整洁度”等。

有关详细信息，请参阅 Wikipedia 上的[多类分类](https://en.wikipedia.org/wiki/Multiclass_classification)一文。

## <a name="regression"></a>回归

[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于从一组相关特征中预测标签值。 标签可以是任何实际值，而不是像在分类任务中那样来自一组有限的值。 回归算法模拟其相关特征上的标签依赖关系，以确定标签将如何随着特征值的变化而变化。 回归算法输入是一组带已知值标签的示例。 回归算法输出是一个函数，可用于预测任何一组新输入特征的标签值。 回归方案示例包括：

* 基于房子特性（如卧室数量、位置或大小）来预测房价。
* 基于历史数据和当前市场趋势预测将来的股票价格。
* 基于广告预算预测产品销售。

> [!NOTE]
> 目前，ML.NET 仍在构建对涉及时序的回归任务的支持。

## <a name="clustering"></a>聚类分析

[非监管式机器学习](glossary.md#unsupervised-machine-learning)任务，用于将数据实例分组到包含类似特性的群集。 聚类分析还可用来识别可能无法通过浏览或简单的观察以逻辑方式推导出的数据集中的关系。 聚类分析算法的输入和输出取决于选择的方法。 可以采取分发、质心、连接或基于密度的方法。 ML.NET 当前支持使用 K 平均值聚类分析的基于质心的方法。 聚类分析方案示例包括：

* 基于酒店选择的习惯和特征来了解酒店来宾群。
* 确定客户群和人口统计信息来帮助生成目标广告活动。
* 基于生产指标对清单进行分类。

## <a name="anomaly-detection-coming-soon"></a>异常检测（即将推出）

## <a name="ranking-coming-soon"></a>排名（即将推出）

## <a name="recommendation-coming-soon"></a>建议（即将推出）

