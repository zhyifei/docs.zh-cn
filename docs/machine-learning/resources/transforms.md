---
title: 数据转换
description: 了解在 ML.NET 中受支持的不同数据转换。
ms.date: 08/08/2018
author: jralexander
ms.author: johalex
ms.openlocfilehash: 3c483f4a263052eb15435775a47f514893eee049
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43397138"
---
# <a name="data-transforms"></a>数据转换

下表包含有关 ML.NET 中受支持的所有数据转换的信息（选择数据转换类型以导航到相应的表）：

* [分类](#categorical)
* [合并器和分离器](#combiners-and-segregators)
* [功能选择](#feature-selection)
* [Featurizers](#featurizers)
* [标签分析](#label-parsing)
* [缺失值](#missing-values)
* [标准化](#normalization)
* [行筛选器](#row-filters)
* [架构](#schema)
* [文本处理和特征化](#text-processing-and-featurization)
* [杂项](#miscellaneous)

> [!NOTE]
> ML.NET 当前处于预览状态。 当前并不支持所有数据转换。 要提交某项转换请求，请在 [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues) GitHub 存储库中发起一个问题。

## <a name="categorical"></a>分类

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CategoricalHashOneHotVectorizer> | 使用基于哈希的编码对分类变量进行编码。 |
| <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer> | 使用基于术语字典的独热编码对分类变量进行编码。 |

## <a name="combiners-and-segregators"></a>合并器和分离器

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CombinerByContiguousGroupId> | 根据相邻的组 ID，将标量列的值汇集到矢量中。 |
| <xref:Microsoft.ML.Transforms.FeatureCombiner> | 将所有功能合并到一个功能列中。 |
| <xref:Microsoft.ML.Transforms.ManyHeterogeneousModelCombiner> | 将一系列 TransformModel 和一个 PredictorModel 合并到一个 PredictorModel 中。 |
| <xref:Microsoft.ML.Transforms.ModelCombiner> | 将一系列 TransformModel 合并到一个模型中。 |
| <xref:Microsoft.ML.Transforms.Segregator> | 将矢量列取消组合为一系列行；组转换的逆向。 |
| <xref:Microsoft.ML.Transforms.TwoHeterogeneousModelCombiner> | 将一个 TransformModel 和一个 PredictorModel 合并到一个 PredictorModel 中。 |

## <a name="feature-selection"></a>功能选择

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.FeatureSelectorByCount> | 选择非默认值计数大于或等于阈值的槽。 |
| <xref:Microsoft.ML.Transforms.FeatureSelectorByMutualInformation> | 选择所有指定列中的前 k 个槽，这些列按其与标签列的相互信息排序。 |

## <a name="featurizers"></a>Featurizers

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.HashConverter> | 将列值转换为哈希。 此转换接受数字和文本输入，包括单值和矢量值列。 |
| <xref:Microsoft.ML.Transforms.TreeLeafFeaturizer> | 训练树形集成，或从文件加载它，然后将数字功能矢量映射到三个输出：1。 包含树形集成的各个树输出的矢量。 2. 指示功能矢量落在树形集成上的叶子的矢量。 3. 指示功能矢量落在树形集成上的路径的矢量。 如果同时指定了模型文件和训练器，则矢量将使用模型文件。 如果两者都未指定，则矢量将训练默认的 FastTree 模型。 这可以处理键标签，方法是针对其可选的置换索引训练回归模型。 |

## <a name="label-parsing"></a>标签分析

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Dictionarizer> | 将输入值（单词、数字等）转换为字典中的索引。 |
| <xref:Microsoft.ML.Transforms.LabelColumnKeyBooleanConverter> | 将标签转换为键或布尔值（如果需要），使其适用于分类。 |
| <xref:Microsoft.ML.Transforms.LabelIndicator> | OVA 使用的标签重映射器。 |
| <xref:Microsoft.ML.Transforms.LabelToFloatConverter> | 将标签转换为浮点，使其适用于回归。 |
| <xref:Microsoft.ML.Transforms.PredictedLabelColumnOriginalValueConverter> | 将预测标签列转换为其原始值，除非它是布尔值类型。 |

## <a name="missing-values"></a>缺失值

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueHandler> | 通过将缺失值替换为默认值或平均值/最小值/最大值（仅适用于非文本列）来处理缺失值。 如果输入列类型为数值，则可以选择连接指示符列。 |
| <xref:Microsoft.ML.Transforms.MissingValueIndicator> | 创建一个布尔值输出列，其槽数与输入列相同，如果缺少输入列中的值，则输出值为 true。 |
| <xref:Microsoft.ML.Transforms.MissingValuesDropper> | 从矢量列中删除 NA。 |
| <xref:Microsoft.ML.Transforms.MissingValuesRowDropper> | 筛选出包含缺失值的行。 |
| <xref:Microsoft.ML.Transforms.MissingValueSubstitutor> | 创建与输入列的类型和大小相同的输出列，其中缺失值将替换为默认值或平均值/最小值/最大值（仅适用于非文本列）。 |

## <a name="normalization"></a>标准化

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BinNormalizer> | 将值分配到等密度箱中，并将值映射到其 bin_number / number_of_bins。 |
| <xref:Microsoft.ML.Transforms.ConditionalNormalizer> | 仅在需要时，对列进行标准化。 |
| <xref:Microsoft.ML.Transforms.GlobalContrastNormalizer> | 对输入值执行全局对比度标准化：Y = (s * X - M) / D，其中 s 是范围，M 是平均值，D 是 L2 范数或标准差。 | 
| <xref:Microsoft.ML.Transforms.LogMeanVarianceNormalizer> | 根据计算平均数和数据对数方差对数据进行标准化。 |
| <xref:Microsoft.ML.Transforms.LpNormalizer> | 通过将矢量（行）重新调整为单位范数（L2、L1 或 LInf）来单独标准化矢量。 对矢量 X 执行以下操作：Y = (X - M) / D，其中 M 是平均值，D 是 L2 范数、L1 范数或 LInf 范数。 |
| <xref:Microsoft.ML.Transforms.MeanVarianceNormalizer> | 根据计算平均数和数据方差对数据进行标准化。 |
| <xref:Microsoft.ML.Transforms.MinMaxNormalizer> | 根据观察到的数据的最小值和最大值对数据进行标准化。 |
| <xref:Microsoft.ML.Transforms.SupervisedBinNormalizer> | 与 <xref:Microsoft.ML.Transforms.BinNormalizer> 类似，但根据与标签列的关联计算箱数，而不是等密度。 新值是 bin_number / number_of_bins。 |

## <a name="row-filters"></a>行筛选器

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowRangeFilter> | 在 Single、Double 或 Key 类型的列上筛选数据视图（相邻）。 保留指定的最小/最大范围内的值。 总是筛选出 NaN。如果输入是 Key 类型，则最小值/最大值将被视为值数量的百分比。 |
| <xref:Microsoft.ML.Transforms.RowSkipAndTakeFilter> | 允许将输入限制为可选偏移的行的子集。 可用于实现数据分页。 |
| <xref:Microsoft.ML.Transforms.RowSkipFilter> | 允许通过跳过多行来将输入限制为行的子集。 |
| <xref:Microsoft.ML.Transforms.RowTakeFilter> | 允许通过使用 N 个第一行来将输入限制为行的子集。 |

## <a name="schema"></a>架构

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnConcatenator> | 连接同一项目类型的两列。 |
| <xref:Microsoft.ML.Transforms.ColumnCopier> | 复制数据集中的列。|
| <xref:Microsoft.ML.Transforms.ColumnDropper> | 从数据集中删除列。 |
| <xref:Microsoft.ML.Transforms.ColumnSelector> | 选择一组列，删除所有其他列。 |
| <xref:Microsoft.ML.Transforms.ColumnTypeConverter> | 使用标准转换将列转换为其他类型。 |
| <xref:Microsoft.ML.Transforms.KeyToTextConverter> | KeyToValueTransform 利用 KeyValues 元数据将键索引映射到 KeyValues 元数据中的相应值。 |
| <xref:Microsoft.ML.Transforms.NGramTranslator> | 在给定的键矢量中生成一组 ngrams 计数（长度为 1-n 的连续值的序列）。 它通过生成 ngram 字典并使用字典中的 ID 作为包中的索引来实现。 | 
| <xref:Microsoft.ML.Transforms.OptionalColumnCreator> | 如果反序列化后源列不存在，请创建具有正确类型和默认值的列。 |

## <a name="text-processing-and-featurization"></a>文本处理和特征化

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CharacterTokenizer> | 面向字符的 tokenizer，其中文本被视为一系列字符。 |
| <xref:Microsoft.ML.Transforms.TextFeaturizer> | 将文本文档集合转换为数值功能矢量的转换。 功能矢量是给定已标记文本中的（单词和/或字符）ngrams 的标准化计数。 |
| <xref:Microsoft.ML.Transforms.TextToKeyConverter> | 将输入值（单词、数字等）转换为字典中的索引。 |
| <xref:Microsoft.ML.Transforms.WordEmbeddings> | 一种转换，它使用预先训练模型将文本令牌的矢量转换为数值矢量。 有关该技术的详细信息，请参阅 [Word 嵌入](https://en.wikipedia.org/wiki/Word_embedding) Wikipedia 页。 |
| <xref:Microsoft.ML.Transforms.WordTokenizer> | 此转换的输入是文本，输出是包含原始文本中单词（令牌）的文本矢量。 该分隔符是空格，但可指定任何其他字符（或多个字符）。 |

## <a name="miscellaneous"></a>杂项

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ApproximateBootstrapSampler> | 近似启动采样。 |
| <xref:Microsoft.ML.Transforms.BinaryPredictionScoreColumnsRenamer> | 对于二进制预测，重命名 PredictedLabel 和 Score 列以包含正类的名称。|
| <xref:Microsoft.ML.Transforms.DataCache> | 使用指定缓存选项缓存。 |
| <xref:Microsoft.ML.Transforms.DatasetScorer> | 使用预测模型对数据集进行评分。 |
| <xref:Microsoft.ML.Transforms.DatasetTransformScorer> | 使用转换模型对数据集进行评分。 |
| <xref:Microsoft.ML.Transforms.NoOperation> | 不执行任何操作。 |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | 添加具有已生成数字序列的列。 |
| <xref:Microsoft.ML.Transforms.ScoreColumnSelector> | 仅选择最后评分列和参数中指定的其他列。 |
| <xref:Microsoft.ML.Transforms.Scorer> | 将预测模型转换为转换模型。 |
| <xref:Microsoft.ML.Transforms.SentimentAnalyzer> | 使用预先训练的情绪模型对输入字符串进行评分。 |
| <xref:Microsoft.ML.Transforms.TrainTestDatasetSplitter> | 将数据集拆分为训练集和测试集。 |
