---
title: ML.NET 指标
description: 了解用于评估 ML.NET 模型性能的指标
ms.date: 04/29/2019
author: natke
ms.openlocfilehash: 45176902a195906e7b5cffd24fc9da839406ad9d
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410537"
---
# <a name="model-evaluation-metrics-in-mlnet"></a>ML.NET 中的模型评估指标

## <a name="metrics-for-binary-classification"></a>二元分类指标

| 指标   |      说明      |  期望 |
|-----------|-----------------------|-----------|
| **准确性** |  [准确性](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification)指正确预测与测试数据集的比例。 它是正确预测次数与输入示例总数的比率。 仅当属于每个类的示例数量相似时，它才能正常工作。| **越接近 1.00 越好**。 但刚好 1.00 表示存在问题（通常包括：标签/目标泄漏、过度拟合或使用训练数据进行测试）。 当测试数据处于非平衡状态（大部分实例属于其中一个类）、数据集非常小，或分数趋近 0.00 或 1.00 时，准确性并不能真实反应分类器的效果，此时需要检查其他指标。 |
| **AUC** |    [aucROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) 或*曲线下面积*：此指标通过扫描真正率和假正率来测量曲线下面积。  |   **越接近 1.00 越好**。 应该大于 0.50 才可接受模型；AUC 为 0.50 或更小的模型毫无价值。 |
| **AUCPR** | [aucPR](https://www.coursera.org/lecture/ml-classification/precision-recall-curve-rENu8) 或*查准率-查全率曲线的曲线下面积*：在类非常不均衡的情况下（高度偏斜的数据集），是成功预测的有用度量值。 |  **越接近 1.00 越好**。 接近 1.00 的高分表明分类器返回准确的结果（高查准率），以及返回大部分正结果（高查全率）。 |
| **F1 分数** | [F1 分数](https://en.wikipedia.org/wiki/F1_score)也称为*均衡 F 分数或 F 度量值*。 这是查准率和查全率的调和平均数。 如果想要在查准率和查全率之间寻求平衡，F1 分数很有用。| **越接近 1.00 越好**。  F1 分数的最佳值为 1.00，最差值为 0.00。 它可指示分类器的查准率。 |

有关二元分类指标的更多详细信息，请阅读以下文章：

- [Accuracy, Precision, Recall or F1?](https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9)（准确性、查准率、查全率还是 F1？）
- [二元分类指标类](xref:Microsoft.ML.Data.BinaryClassificationMetrics)
- [The Relationship Between Precision-Recall and ROC Curves](http://pages.cs.wisc.edu/~jdavis/davisgoadrichcamera2.pdf)（查准率-查全率曲线与 ROC 曲线之间的关系）

## <a name="metrics-for-multi-class-classification"></a>多类分类指标

| 指标   |      说明      |  期望 |
|-----------|-----------------------|-----------|
| **微观准确性** |  [微平均准确性](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MicroAccuracy)聚合所有类的贡献度来计算平均指标。 它是正确预测的实例的部分。 微平均不考虑类成员资格。 基本而言，每个“示例-类”对对准确性指标的贡献度相同。 | **越接近 1.00 越好**。 在多类分类任务中，如果怀疑可能存在类不均衡的现象（即 某个类的实例可能比其他类的实例多很多），则应选择微观准确性，而不是宏观准确性。|
| **宏观准确性** | [宏平均准确性](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MacroAccuracy)指类级别的平均准确性。 每个类的准确性都会进行计算，宏观准确性就是这些准确性的平均值。 基本而言，每个类对准确性指标的贡献度相同。 占比较小的类与占比较大的类拥有同等的权重。 无论数据集包含多少个来自该类的实例，宏平均指标都会对每个类赋予相同的权重。 |  **越接近 1.00 越好**。  它为每个类单独计算该指标，然后取平均值（因此实现平等对待所有类） |
| **对数损失**| [对数损失](http://wiki.fast.ai/index.php/Log_Loss)测量分类模型的性能，其中预测输入是介于 0.00 和 1.00 之间的概率值。 随着预测概率偏离实际标签，对数损失会增加。 | **越接近 0.00 越好**。 完美模型的对数损失为 0.00。 我们的机器学习模型旨在最小化此值。|
| **对数损失减小** | [对数损失减小](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.LogLossReduction)可以解释为分类器相较随机预测的优势。| **取值范围为 [-inf, 1.00]，其中 1.00 表示完美的预测，0.00 表示准确性一般的预测**。 例如，如果该值等于 0.20，则可以将其解释为“正确预测的概率比随机猜测的概率高 20%”|

微观准确性通常能够更好地与 ML 预测的业务需求保持一致。 如果想要选择单个指标用于选择多类分类任务的质量，则通常应选择微观准确性。

例如，对于支持票证分类任务：（将传入的票证映射到支持团队）

- 微观准确性 - 传入票证分类给正确团队的频率如何？
- 宏观准确性 - 对于普通团队而言，传入票证符合其业务范围的频率如何？

在此示例中，宏观准确性对于小型团队而言任务过重；一个每年仅收到 10 个票证的小团队被视为每年可收到 10,000 个票证的大团队。 在本例中，微观准确性与“公司可通过自动化票证路由流程节省多少时间/金钱”这一业务需求相关性更高。

有关多类分类指标的更多详细信息，请阅读以下文章：

- [Micro- and Macro-average of Precision, Recall and F-Score](http://rushdishams.blogspot.com/2011/08/micro-and-macro-average-of-precision.html)（查准率、查全率和 F 分数的微平均及宏平均）
- [Multiclass Classification with Imbalanced Dataset](https://towardsdatascience.com/machine-learning-multiclass-classification-with-imbalanced-data-set-29f6a177c1a)（不均衡数据集的多类分类）

## <a name="metrics-for-regression"></a>回归指标

| 指标   |      说明      |  期望 |
|-----------|-----------------------|-----------|
| **R 平方** |  [R 平方 (R2)](https://en.wikipedia.org/wiki/Coefficient_of_determination) 又称为*决定系数*，其将模型的预测能力表示为取值范围介于 -inf 和 1.00 之间的值。 1.00 意味着完美拟合，且拟合度可以无穷差，因此分数可能为负数。 分数为 0.00 表示模型正在猜测标签的预期值。 R2 测量实际测试数据值与预测值的接近程度。 | **越接近 1.00 表示质量越好**。 但是，有时较低的 R 平方值（例如 0.50）对于方案而言可能完全正常或足够好，并且较高的 R 平方值并不总是好结果且有时可疑。 |
| **绝对值损失** |  [绝对值损失](https://en.wikipedia.org/wiki/Mean_absolute_error)又称为*平均绝对误差 (MAE)* ，其测量预测结果与实际结果的接近程度。 它是所有模型误差的平均值，其中模型误差是预测标签值和正确标签值之间的绝对差距。 为测试数据集的每个记录计算此预测误差。 最后，计算所有已记录的绝对误差的平均值。| **越接近 0.00 表示质量越好。** 请注意，平均绝对误差使用与待测量数据相同的比例（未规范化为特定范围）。 绝对值损失、平方损失和 RMS 损失只能用于同一数据集的模型或具有类似标签值分布的数据集之间的比较。 |
| **平方损失** |  [平方损失](https://en.wikipedia.org/wiki/Mean_squared_error)又称为*均方误差 (MSE)* 或*均方偏差 (MSD)* ，可指示回归线与一组测试数据值的接近程度。 它通过获取从点到回归线的距离（这些距离即为误差 E）并对这些距离求平方来做到这一点。 求平方可赋予较大的差异更大的权重。 | 它始终是非负值，并且**越接近 0.00 的值越好**。 可能会无法获得非常小的均方误差值，具体取决于数据。|
| **RMS 损失** |  [RMS 损失](https://en.wikipedia.org/wiki/Root-mean-square_deviation)又称为*均方根误差 (RMSE)* 和 *均方根偏差 (RMSD)* ，其测量模型预测的值与在建模环境中实际观测到的值之间的差异。 RMS 损失是平方损失的平方根，其具有与标签相同的单位，类似于绝对值损失，但赋予了较大的差异更大的权重。 均方根误差通常用于气候学、预测和回归分析，以验证试验结果。 | 它始终是非负值，并且**越接近 0.00 的值越好**。 RMSD 是准确性度量值，用于比较特定数据集的不同模型的预测误差，而不用于比较数据集之间的预测误差，因为它与比例相关。|

有关回归指标的更多详细信息，请阅读以下文章：

- [Regression Analysis:How Do I Interpret R-squared and Assess the Goodness-of-Fit?](https://blog.minitab.com/blog/adventures-in-statistics-2/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit)（回归分析：我如何解释 R 平方并评估拟合优度？）
- [How To Interpret R-squared in Regression Analysis](https://statisticsbyjim.com/regression/interpret-r-squared-regression)（如何在回归分析中解释 R 平方）
- [R-Squared Definition](https://www.investopedia.com/terms/r/r-squared.asp)（R 平方定义）
- [Mean Squared Error Definition](https://www.statisticshowto.datasciencecentral.com/mean-squared-error/)（均方误差定义）
- [What are Mean Squared Error and Root Mean Squared Error?](https://www.vernier.com/til/1014/)（什么是均方误差和均方根误差？）
