---
title: 什么是模型生成器，它的工作原理是怎样的？
description: 如何使用 ML.NET 模型生成器自动训练机器学习模型
author: natke
ms.date: 06/26/2019
ms.custom: overview
ms.openlocfilehash: 6f5bbe3c389e3ca42550a48ef3e6edbc963ac2e9
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410585"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>什么是模型生成器，它的工作原理是怎样的？

ML.NET 模型生成器是一个易于理解的图形化 Visual Studio 扩展，用于生成、训练和部署自定义机器学习模型。 

模型生成器使用自动化的机器学习 (AutoML) 来探索不同的机器学习算法和设置，以帮助找到最合适的方案。

使用模型生成器不需要具备机器学习的专业知识。 只需要一些数据，和确定要解决的问题。 模型生成器会生成将模型添加到 .NET 应用程序的代码。

![模型生成器 Visual Studio 扩展用户界面动画](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> 模型生成器当前为预览版。

## <a name="scenarios"></a>方案

可以为模型生成器提供许多不同的方案，从而为应用程序生成一个机器学习模型。

方案就是要对数据进行的预测类型的描述。 例如:
- 根据历史销售数据预测未来的产品销量
- 根据客户评价将情绪分类为正面或负面
- 检测某项银行交易是否存在欺诈性
- 将客户反馈问题传递至公司中合适的团队

在模型生成器中，需要将方案映射到 [ML.NET 任务](resources/tasks.md)上。 可以使用模型生成器进行回归（预测数字）和分类（预测类别）   。

### <a name="which-machine-learning-scenario-is-right-for-me"></a>哪个机器学习方案最适合我？

模型生成器带有用于情绪分析、问题分类、价格预测和自定义方案的模板。 这些模板可以作为特定 ML.NET 方案的起点。

#### <a name="sentiment-analysis-binary-classification"></a>情绪分析（二元分类）

情绪分析可用于预测的客户反馈中的正面情绪或负面情绪。 它是一个二元分类任务的例子。

二元分类用于将数据分为两类（是/否；通过/失败；true/false；正面/负面）。 该分类可回答类似于以下的问题：

- 该电子邮件是否是垃圾邮件？ （垃圾邮件检测）
- 哪些申请者有资格得到成员身份？ （申请筛选）
- 哪些帐户可能不会按时支付发票？ （风险缓解）
- 此信用卡交易是否存在欺诈性？ （欺诈检测）

如果方案需要将数据分为两类，可以将该模板与自己的数据集配合使用。
 
#### <a name="issue-classification-multiclass-classification"></a>问题分类（多类分类）

问题分类可用于使用问题标题和描述对客户反馈（例如 GitHub 上的反馈）问题进行分类。 它是一个多类分类任务的例子。

多类分类可用于将数据分为三类或更多类。 该分类可回答类似于以下的问题：

- 我应向哪个部门传递支持票证？ （支持票证传递）
- 客户问题的优先级是什么？ （客户问题优先级）
- 产品属于什么类别？ （产品分类）
- 文档是什么类型？ （文档/电子邮件分类）

如果需要将数据分为三类或更多类，可以使用问题分类模板。

#### <a name="price-prediction-regression"></a>价格预测（回归）

价格预测可以通过房屋的位置、大小等特点来预测房价。 它是一个回归任务的例子。

回归用于预测数字。 该分类可回答类似于以下的问题：

- 一套房屋的售价会是多少？ （价格预测）
- 机械部件将在多长时间以后需要维修？ （预测性维护）
- 这台烘干机的含水量是多少？ （机器监控）
- 此区域的年度销售总额将是多少？ （销售预测）

如果要使用自己的数据集预测数字值，可以使用价格预测模板。

#### <a name="custom-scenario-choose-your-task"></a>自定义方案（选择自己的任务）

使用自定义方案，可以选择自己的任务。 选择对问题最有帮助的方案。

使用自定义方案，可以选择自己的机器学习任务。 在之前介绍的各类模板中，机器学习任务仅限于二元分类、多类分类或回归这三种方案。 在此模板中，可以选择要对自己的数据使用的 ML 任务。

## <a name="data"></a>数据

在将方案映射到任务上后，模型生成器会要求你提供数据集。 这些数据用于训练、评估和选择最适合方案的的模型。 还需要选择想预测的输出。

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

### <a name="data-formats"></a>数据格式

模型生成器对数据设有以下限制：

- 数据必须存储在文件（具有标题行的 .csv 或.tsv 文件）或 SQL server 数据库中。
- 训练数据集不能超过 1 GB
- SQL Server 在训练用途上有 100,000 行的限制
- 在训练之前，将 SQL server 中的数据从服务器复制到本地计算机

### <a name="example-datasets"></a>示例数据集

如果还没有自己的数据，请试用以下数据集之一：

|方案|ML 任务|数据|Label|功能|
|-|-|-|-|-|
|价格预测|回归|[出租车费数据](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|车费|行程时间、距离|
|异常情况检测|二元分类|[产品销售数据](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|产品销售额|月份|
|情绪分析|二元分类|[网站评论数据](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_SentimentAnalysis/SentimentAnalysis/Data/wikiDetoxAnnotated40kRows.tsv)|标签（负面情绪为 0，正面情绪为 1）|评论、年份|
|欺诈检测|二元分类|[信用卡数据](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|类（存在欺诈性为 1，否则为 0）|金额，V1-V28（匿名处理后的特征）|
|文本分类|多类分类|[GitHub 问题数据](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|区域|标题、描述|

## <a name="train"></a>定型

选择方案、数据和标签后，模型生成器会训练该模型。

### <a name="what-is-training"></a>什么是训练？

训练是一个自动的过程，模型生成器通过该过程教模型如何回答方案相关的问题。 训练后，模型可以对其没有见过的输入数据进行预测。 例如，在预测房价时，可以预测新上市的房屋销售价。

因为模型生成器使用自动机器学习 (AutoML)，所以在训练期间不需要任何人工输入或微调操作。

### <a name="how-long-should-i-train-for"></a>训练时长应为多长时间？

你可以提供一个训练时长。 一般情况下，训练时间越长，生成的模型就越准确。 如果训练用的数据集增大，训练时间也会变长。 关于数据集大小增加和训练时间之间的关系，请参考下表。

数据集大小  | 数据集类型       | 平均训练时间
------------- | ------------------ | --------------
0 - 10 Mb     | 数值和文本   | 10 秒
10 - 100 Mb   | 数值和文本   | 10 分钟 
100 - 500 Mb  | 数值和文本   | 30 分钟 
500 - 1 Gb    | 数值和文本   | 60 分钟 
1 Gb 以上         | 数值和文本   | 3 小时以上 

训练的确切时间还取决于：

- 列的类型（文本还是数值）
- 机器学习任务的类型（回归还是分类）
- 用于训练的行数
- 用于训练的特征列数

模型生成器已使用 1 TB 的数据集进行了大规模的测试，但为这么大的数据集生成高质量的模型可能需要多达 4 天的时间！

## <a name="evaluate"></a>评估

评估是让经过训练的模型对新的测试数据进行预测，然后度量预测效果的过程。

模型生成器将训练数据拆分为训练集和测试集。 训练数据 (80%) 用于训练模型，测试数据 (20%) 用于评估模型。  用于评估的指标取决于 ML 任务。 有关详细信息，请参阅[模型评估指标](resources/metrics.md)。  

### <a name="sentiment-analysis-binary-classification"></a>情绪分析（二元分类）

二元分类问题的默认指标是“准确性”  。 准确性定义的是模型对测试数据集做出的正确预测的比例。 越接近 100% 越好  。

报告的其他指标，如 AUC（曲线下面积），用于度量真正例率和假正例率之间的比例，在高于 0.50 时，才是可以接受的模型。 

此外还有一些其他指标，如 F1 分数，可以用来控制检准率（正确的预测占该类总预测数的比例）和检全率（正确预测占该类总实际成员的比例）之间的平衡。

### <a name="issue-classification-multiclass-classification"></a>问题分类（多类分类）

多类分类问题的默认指标是“微观准确性”  。 越接近 100% 越好  。

在将数据分为多个类的问题中，有两种类型的准确性：

- 微观准确性：所有实例中正确预测的百分比。 在问题分类方案中，微观准确性是分配到正确类别的传入问题的比例。 
- 宏观准确性：在类级别上得出的平均准确性。 在问题分类方案中，会为每个类别测量准确性，然后对各个类别的准确性求平均值。 对于此指标，所有类得到的权重都是相等的。 如果是完全均匀的数据集（即每个类别中的示例数量相等），微观准确性和宏观准确性就是相同的。


### <a name="price-prediction-regression"></a>价格预测（回归）

回归问题的默认指标是“RSquared”  。 1 是可能达到的最佳值。 RSquared 越接近 1，模型就越好。

报告的其他指标，如绝对损失、平方损失和 RMS 损失，可以用来理解模型，并将其与其他回归模型进行比较。 

## <a name="improve"></a>改进

如果模型性能评分不符合预期，可以：

* 延长训练时间。 有了更多时间，自动机器学习引擎可以尝试更多算法和设置。

* 添加更多数据。 有时候可能是数据量不足，无法训练出高质量的机器学习模型。 

* 均衡分配数据。 对于分类任务，请确保在各个类别间均匀分配训练集。 例如，若有四个类别和 100 个训练示例，前两类（标记 1 和标记 2）包含 90 个记录，而剩下两类（标记 3 和标记 4）只包含 10 个记录，这就存在数据不均衡的问题，可能会导致模型很难正确预测标记 3 或标记 4。

## <a name="code"></a>代码

完成评估阶段后，模型生成器会输出一份模型文件和代码，可以使用该代码将模型添加到应用程序。 ML.NET 模型保存为 zip 文件。 用于加载和使用模型的代码会以新项目的形式添加到解决方案中。 模型生成器还会添加一个示例控制台应用，可以运行该应用来查看工作状态下的模型。

此外，模型生成器还会输出生成模型的代码，以便你能了解生成模型所使用的步骤。 还可以通过模型训练代码使用新的数据重新训练模型。

## <a name="whats-next"></a>后续步骤

请尝试[价格预测或任何回归方案](tutorials/predict-prices-with-model-builder.md)
