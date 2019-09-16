---
title: 数据转换
description: 了解在 ML.NET 中受支持的特征工程组件。
author: natke
ms.author: nakersha
ms.date: 04/02/2019
ms.openlocfilehash: 25da3cceb3c9090661b34254ed240207aaf3b9d7
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929256"
---
# <a name="data-transformations"></a>数据转换

数据转换用于：

- 准备用于模型训练的数据
- 采用 TensorFlow 或 ONNX 格式应用导入的模型
- 通过模型传递数据后对其进行后处理

本指南中的数据转换返回实现 [IEstimator](xref:Microsoft.ML.IEstimator%601) 接口的类。 数据转换可以链接在一起。 每个数据转换都需要获取并生成特定类型和格式的数据，链接的参考文档中规定了具体类型和格式。

一些数据转换需要通过定型数据来计算参数。 例如，<xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> 转换器计算 `Fit()` 操作期间定型数据的平均值和方差，并在 `Transform()` 操作中使用这些参数。 

另一些数据转换不需要定型数据。 例如，<xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> 转换可以执行 `Transform()` 操作，而无需在 `Fit()` 操作期间看到任何定型数据。

## <a name="column-mapping-and-grouping"></a>列映射和分组

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | 将一个或多个输入列连接到新输出列中 |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | 复制和重命名一个或多个输入列 |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | 删除一个或多个输入列 |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | 选择一个或多个不包含输入数据的列 |

## <a name="normalization-and-scaling"></a>规范化和缩放

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | 减去（定型数据的）平均值，再除以（定型数据的）方差 |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | 根据定型数据的对数进行规范化 |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | 按 [lp 范数](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions)缩放输入向量，其中 p 为 1、2 或无穷大。 默认为 l2（欧几里得距离）范数 |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | 缩放行中的每个值，具体方法是减去行数据的平均值，除以（行数据的）标准差或 l2 范数，再乘以可配置的比例因子（默认值为 2） |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | 将输入值分配到箱索引，并除以箱数量，以生成介于 0 和 1 之间的浮点值。 计算箱边界是为了在各个箱中均匀分布定型数据 |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | 根据与标签列的相关性，将输入值分配到箱 |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | 按定型数据最小值和最大值的差值缩放输入 |

## <a name="conversions-between-data-types"></a>数据类型转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | 将输入列的类型转换为新类型 |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue*> | 根据提供的映射字典将值映射到键（类别） |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*> | 通过从输入数据创建映射，将值映射到键（类别） |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue*> | 将键转换回原始值 |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector*> | 将键转换回原始值的向量 |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector*> | 将键转换回原始值的二元向量 |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash*> | 哈希处理输入列中的值 |

## <a name="text-transformations"></a>文本转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText*> | 将文本列转换为规范化 ngram 和 char-gram 计数的浮点数组 | 
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords*> | 将一个或多个文本列拆分为各个字词 |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys*> | 将一个或多个文本列拆分为关于一组主题的各个字符浮点数 |
| <xref:Microsoft.ML.TextCatalog.NormalizeText*> | 更改大小写、删除标注字符、标点符号和数字 |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams*> | 将文本列转换为一组 ngram 计数（连续单词的序列）|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags*> | 将文本列转换为一组 ngram 向量计数 |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams*> | 将文本列转换为已哈希处理的 ngram 计数向量 |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags*> | 将文本列转换为一组已哈希处理的 ngram 计数 |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords*>  | 从输入列中删除指定语言的默认停用词 |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords*> | 从输入列中删除指定的停用词 |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation*> | 将文档（表示为浮点数向量）转换为关于一组主题的浮点数向量 |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding*> | 使用预定型模型将文本令牌向量转换为句向量 |

## <a name="image-transformations"></a>图像转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> | 将图像转换为灰度图像 |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage*> | 将像素向量转换为 <xref:Microsoft.ML.Transforms.Image.ImageDataViewType> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*> | 将输入图像中的像素转换为数字向量 |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*> | 将图像从文件夹加载到内存中 |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*> | 调整图像大小 |
| <xref:Microsoft.ML.OnnxCatalog.DnnFeaturizeImage*> | 应用预训练的深度神经网络 (DNN) 模型将输入图像转换为特征向量 |

## <a name="categorical-data-transformations"></a>分类数据转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*> | 将一个或多个文本列转换为[单热](https://en.wikipedia.org/wiki/One-hot)编码向量 |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding*> | 将一个或多个文本列转换为基于哈希的单热编码向量 |

## <a name="time-series-data-transformations"></a>时序数据转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectAnomalyBySrCnn*> | 使用 Spectral Residual (SR) 算法检测输入时序数据中的异常 |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectChangePointBySsa*> | 使用奇异谱分析 (SSA) 检测时序数据中的更改点 |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidChangePoint*> | 使用自适应内核密度估计和鞅评分检测独立同分布 (IID) 的时序数据中的更改点 |
| <xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa*> | 使用奇异谱分析 (SSA) 预测时序数据 |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectSpikeBySsa*> | 使用奇异谱分析 (SSA) 检测时序数据中的峰值 |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidSpike*> | 使用自适应内核密度估计和鞅评分检测独立同分布 (IID) 的时序数据中的峰值 |

## <a name="missing-values"></a>缺失值

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues*> | 新建布尔输出列：如果输入列中缺少值，输出列的值为 true |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*> | 新建输出列：如果输入列中缺少值，输出列的值设置为默认值，否则设置为输入值 |

## <a name="feature-selection"></a>功能选择

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount*> | 选择非默认值大于阈值的功能 |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation*> | 选择标签列中的数据最依赖的功能 |

## <a name="feature-transformations"></a>功能转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.KernelExpansionCatalog.ApproximatedKernelMap*> | 将每个输入向量映射到较低维度的特征空间，在该特征空间中，内积近似于内核函数，这样就可以将特征用作线性算法的输入 |
| <xref:Microsoft.ML.PcaCatalog.ProjectToPrincipalComponents*> | 通过应用主成分分析算法来降低输入特征向量的维度 |

## <a name="explainability-transformations"></a>解释能力转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.ExplainabilityCatalog.CalculateFeatureContribution*> | 计算特征向量的每个元素的贡献分数 |

## <a name="calibration-transformations"></a>校准转换

| Transform | 定义 |
| --- | --- |
|<xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.String%2CSystem.String%2CSystem.String%29> | 使用带有使用训练数据的参数估计的逻辑回归将二元分类器原始分数转换为类概率 |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.Double%2CSystem.Double%2CSystem.String%29> | 使用带有固定参数的逻辑回归将二元分类器原始分数转换为类概率 |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Naive*> | 通过将分数分配到箱并根据箱之间的分布计算概率将二元分类器原始分数转换为类概率 |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Isotonic*> | 通过将分数分配到箱将二元分类器原始分数转换为类概率（使用训练数据估计边界位置和箱的大小）  |

## <a name="deep-learning-transformations"></a>深度学习转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*> | 使用导入的 ONNX 模型转换输入数据 |
| <xref:Microsoft.ML.TensorflowCatalog.LoadTensorFlowModel*> | 使用导入的 TensorFlow 模型转换输入数据 |

## <a name="custom-transformations"></a>自定义转换

| Transform | 定义 |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping*> | 使用用户定义映射将现有列转换为新列 |
