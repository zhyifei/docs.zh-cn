---
title: 使用规范化程序来预处理要在数据处理过程中使用的定型数据 - ML.NET
description: 了解如何使用规范化程序对定型数据进行预处理，这些数据将在 ML.NET 中用于机器学习模型生成、训练和评分
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: c8b959904705e996c97bdcd8b3444e754d14d046
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297614"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>使用规范化程序来预处理要在数据处理过程中使用的定型数据 - ML.NET

ML.NET 公开大量[参数和非参数化算法](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/)。

与训练线性或其他参数模型时的情况不同，在这种情况下，选择哪种规范化程序并不那么重要。

始终在 ML.NET 学习管道中直接包含规范化程序，以便它：

- 仅使用定型数据进行训练，而不使用测试数据。
- 正确应用于所有新传入的数据，而无需在预测时进行额外的预处理。

下面是一个代码片段，展示了学习管道规范化操作。 假定鸢尾花数据集：

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features", DataKind.R4, 0, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    // Default separator is tab, but the dataset has comma.
    Separator = ","
});

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
        new NormalizingEstimator.MinMaxColumn("Features", "MinMaxNormalized", fixZero: true),
        new NormalizingEstimator.MeanVarColumn("Features", "MeanVarNormalized", fixZero: true),
        new NormalizingEstimator.BinningColumn("Features", "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
