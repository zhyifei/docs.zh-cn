---
title: 使用规范化程序来预处理要在数据处理过程中使用的定型数据 - ML.NET
description: 了解如何使用规范化程序对定型数据进行预处理，这些数据将在 ML.NET 中用于机器学习模型生成、训练和评分
ms.date: 02/01/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4311307f5410a96bb4a30fcedd88bc43afd25c12
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738573"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a><span data-ttu-id="38ded-103">使用规范化程序来预处理要在数据处理过程中使用的定型数据 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="38ded-103">Preprocess training data with normalizers to use in data processing - ML.NET</span></span>

<span data-ttu-id="38ded-104">ML.NET 公开大量[参数和非参数化算法](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/)。</span><span class="sxs-lookup"><span data-stu-id="38ded-104">ML.NET exposes a number of [parametric and non-parametric algorithms](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span></span>

<span data-ttu-id="38ded-105">与训练线性或其他参数模型时的情况不同，在这种情况下，选择哪种规范化程序并不那么重要。</span><span class="sxs-lookup"><span data-stu-id="38ded-105">It's **not** as important which normalizer you choose as it is to **use** a normalizer when training linear or other parametric models.</span></span>

<span data-ttu-id="38ded-106">始终在 ML.NET 学习管道中直接包含规范化程序，以便它：</span><span class="sxs-lookup"><span data-stu-id="38ded-106">Always include the normalizer directly in the ML.NET learning pipeline, so it:</span></span>

- <span data-ttu-id="38ded-107">仅使用定型数据进行训练，而不使用测试数据。</span><span class="sxs-lookup"><span data-stu-id="38ded-107">is only trained on the training data, and not on your test data,</span></span>
- <span data-ttu-id="38ded-108">正确应用于所有新传入的数据，而无需在预测时进行额外的预处理。</span><span class="sxs-lookup"><span data-stu-id="38ded-108">is correctly applied to all the new incoming data, without the need for extra pre-processing at prediction time.</span></span>

<span data-ttu-id="38ded-109">下面是一个代码片段，展示了学习管道规范化操作。</span><span class="sxs-lookup"><span data-stu-id="38ded-109">Here's a snippet of code that demonstrates normalization in learning pipelines.</span></span> <span data-ttu-id="38ded-110">假定鸢尾花数据集：</span><span class="sxs-lookup"><span data-stu-id="38ded-110">It assumes the Iris dataset:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

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
