---
title: 什么是模型生成器，它的工作原理是怎样的？
description: 如何使用 ML.NET 模型生成器自动训练机器学习模型
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: a871c3a3751a93bdf0104c873215b164616f0664
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69611462"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>什么是模型生成器，它的工作原理是怎样的？

ML.NET 模型生成器是一个直观的图形化 Visual Studio 扩展，用于生成、训练和部署自定义机器学习模型。

模型生成器使用自动化的机器学习 (AutoML) 来探索不同的机器学习算法和设置，以帮助找到最合适的方案。

使用模型生成器不需要具备机器学习的专业知识。 只需要一些数据，和确定要解决的问题。 模型生成器会生成将模型添加到 .NET 应用程序的代码。

![模型生成器 Visual Studio 扩展用户界面动画](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> 模型生成器当前为预览版。

## <a name="scenarios"></a>方案

可以为模型生成器提供许多不同的方案，从而为应用程序生成一个机器学习模型。

方案就是要使用数据进行预测类型的描述。 例如:
- 根据历史销售数据预测未来的产品销量
- 根据客户评价将情绪分类为正面或负面
- 检测某项银行交易是否存在欺诈性
- 将客户反馈问题传递至公司中合适的团队

## <a name="choose-a-model-type"></a>选择模型类型

在模型生成器中，需要选择机器学习模型类型。 模型类型取决于尝试进行的预测类型。

对于预测数字的方案，机器学习模型称为 `regression`。

对于预测类别的方案，模型类型为 `classification`。 有两种类型的分类：
- 其中只有两个类别：`binary classification`。
- 其中有三个或更多个类别：`multiclass classification`。

### <a name="which-model-type-is-right-for-me"></a>哪种模型类型适合我？

#### <a name="predict-a-category-when-there-are-only-two-categories"></a>预测类别（只有两个类别时）

二元分类用于将数据分为两个类别（是/否；通过/失败；true/false；正面/负面）。

![显示二元分类示例（包括欺诈检测、风险环节和应用程序屏蔽）的图示](media/binary-classification-examples.png)

情绪分析可用于预测的客户反馈中的正面情绪或负面情绪。 它是一个二元分类模型类型的例子。

如果方案需要将数据分为两类，可以将该模板与自己的数据集配合使用。

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a>预测类别（有三个或更多个类别时）

多类分类可用于将数据分为三类或更多类。 

![多类分类示例，包括文档和产品分类、支持票证路由以及客户问题优先级](media/multiclass-classification-examples.png)

问题分类可用于使用问题标题和描述对客户反馈（例如 GitHub 上的反馈）问题进行分类。 它是一个多类分类模型类型的例子。

如果需要将数据分为三类或更多类，可以使用问题分类模板。

#### <a name="predict-a-number"></a>预测数字

回归用于预测数字。

![显示回归示例（如价格预测、销售预测和预测性维护）的图示](media/regression-examples.png)

价格预测可以通过房屋的位置、大小等特点来预测房价。 它是一个回归模型类型的例子。

如果要使用自己的数据集预测数字值，可以使用价格预测模板。

#### <a name="custom-scenario-choose-your-model-type"></a>自定义方案（选择自己的模型类型）

使用自定义方案，可以手动选择自己的模型类型。

## <a name="data"></a>数据

选择模型类型后，模型生成器会要求你提供数据集。 这些数据用于训练、评估和选择最适合方案的的模型。

![显示模型生成器步骤的图示](media/model-builder-steps.png)

### <a name="choose-the-output-to-predict-label"></a>选择要预测的输出（标签）

数据集是一个表格，其中，行中含训练示例，列中含特性。 每一行都具有：
- 一个标签，即要预测的特性 
- 特征（为预测标签而用作输入的特性）  。

在房价预测方案中，特性可能是：
- 房屋的面积
- 卧室和卫生间的数量
- 邮政编码

标签是与其所属行（包含面积、卧室和卫生间值以及邮政编码信息）对应的历史房价。

![表显示房价数据的行和列，其中包含由大小、房间数、邮政编码和价格标签组成的特征](media/model-builder-data.png)

### <a name="example-datasets"></a>示例数据集

如果还没有自己的数据，请试用以下数据集之一：

|方案|模型类型|数据|Label|特征|
|-|-|-|-|-|
|价格预测|回归|[出租车费数据](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|车费|行程时间、距离|
|异常情况检测|二元分类|[产品销售数据](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|产品销售额|月份|
|情绪分析|二元分类|[网站评论数据](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|标签（负面情绪为 0，正面情绪为 1）|评论、年份|
|欺诈检测|二元分类|[信用卡数据](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|类（存在欺诈性为 1，否则为 0）|金额，V1-V28（匿名处理后的特征）|
|文本分类|多类分类|[GitHub 问题数据](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|区域|标题、描述|

## <a name="train"></a>定型

选择方案、数据和标签后，模型生成器会训练该模型。

### <a name="what-is-training"></a>什么是训练？

训练是一个自动的过程，模型生成器通过该过程教模型如何回答方案相关的问题。 训练后，模型可以对其没有见过的输入数据进行预测。 例如，在预测房价时，可以预测新上市的房屋销售价。

因为模型生成器使用自动机器学习 (AutoML)，所以在训练期间不需要任何人工输入或微调操作。

## <a name="evaluate"></a>评估

评估是让经过训练的模型对新的测试数据进行预测，然后度量预测效果的过程。

模型生成器将训练数据拆分为训练集和测试集。 训练数据 (80%) 用于训练模型，测试数据 (20%) 用于评估模型。 模型生成器使用指标来衡量模型的优秀程度。 所使用的具体指标取决于模型类型。 有关详细信息，请参阅[模型评估指标](resources/metrics.md)。

## <a name="improve"></a>改进

如果模型性能评分不符合预期，可以：

* 延长训练时间。 有了更多时间，自动机器学习引擎可以尝试更多算法和设置。

* 添加更多数据。 有时候可能是数据量不足，无法训练出高质量的机器学习模型。

* 均衡分配数据。 对于分类任务，请确保在各个类别间均匀分配训练集。 例如，若有四个类别和 100 个训练示例，前两类（标记 1 和标记 2）包含 90 个记录，而剩下两类（标记 3 和标记 4）只包含 10 个记录，这就存在数据不均衡的问题，可能会导致模型很难正确预测标记 3 或标记 4。

## <a name="code"></a>代码

完成评估阶段后，模型生成器会输出一份模型文件和代码，可以使用该代码将模型添加到应用程序。 ML.NET 模型保存为 zip 文件。 用于加载和使用模型的代码会以新项目的形式添加到解决方案中。 模型生成器还会添加一个示例控制台应用，可以运行该应用来查看工作状态下的模型。

此外，模型生成器还会输出生成模型的代码，以便你能了解生成模型所使用的步骤。 还可以通过模型训练代码使用新的数据重新训练模型。

## <a name="whats-next"></a>后续步骤

[安装](how-to-guides/install-model-builder.md)模型生成器 Visual Studio 扩展

请尝试[价格预测或任何回归方案](tutorials/predict-prices-with-model-builder.md)
