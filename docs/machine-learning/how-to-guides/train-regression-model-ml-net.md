---
title: 使用 ML.NET 定型回归模型以预测某个值
description: 了解如何使用 ML.NET 定型机器学习回归模型以预测某个值
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: faee51550250f08443d4d9349fa2f1c92bf411dc
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092899"
---
# <a name="train-a-regression-model-to-predict-a-value-using-mlnet"></a><span data-ttu-id="01a80-103">使用 ML.NET 定型回归模型以预测某个值</span><span class="sxs-lookup"><span data-stu-id="01a80-103">Train a regression model to predict a value using ML.NET</span></span>

<span data-ttu-id="01a80-104">通常，在 ML.NET 中进行模型定型需要执行三个步骤：</span><span class="sxs-lookup"><span data-stu-id="01a80-104">Generally, there are three steps for model training in ML.NET:</span></span>

1. <span data-ttu-id="01a80-105">获取 `IDataView` 形式的定型数据</span><span class="sxs-lookup"><span data-stu-id="01a80-105">Get the training data in a form of an `IDataView`</span></span>
2. <span data-ttu-id="01a80-106">将“学习管道”构建为一系列基本“运算符”（估算器）。</span><span class="sxs-lookup"><span data-stu-id="01a80-106">Build the 'learning pipeline' as a sequence of elementary 'operators' (estimators).</span></span>
3. <span data-ttu-id="01a80-107">在管道上调用 `Fit` 以获得定型的模型。</span><span class="sxs-lookup"><span data-stu-id="01a80-107">Call `Fit` on the pipeline to obtain the trained model.</span></span>

<span data-ttu-id="01a80-108">在此[示例文件](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv)中，预测标签（`target`）是最后一列（第 12 列），其余所有内容都是功能：</span><span class="sxs-lookup"><span data-stu-id="01a80-108">In this [Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv),the predicted label (`target`) is the last column (12th) and all the rest are features:</span></span>

```console
feature_0;feature_1;feature_2;feature_3;feature_4;feature_5;feature_6;feature_7;feature_8;feature_9;feature_10;target
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.

// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
        columns: new TextLoader.Column[]
        {
            // We read the first 11 values as a single float vector.
            new TextLoader.Column("FeatureVector",DataKind.R4,0,10),
            // Separately, read the target variable.
            new TextLoader.Column("Target",DataKind.R4,11)
        },
        // Default separator is tab, but the dataset has semicolon.
        separatorChar: ';',
        // First line of the file is a header, not a data row.
        hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var trainData = reader.Read(dataPath);

// Step two: define the learning pipeline.

// We 'start' the pipeline with the output of the reader.
var pipeline =
        // First 'normalize' the data (rescale to be
        // between -1 and 1 for all examples)
        mlContext.Transforms.Normalize("FeatureVector")
        // Cache data in memory so that SDCA trainer will be able to randomly access training examples without
        // reading data from disk multiple times. Data will be cached at its first use in any downstream step.
        // Notice that unused part in the data may not be cached.
        .AppendCacheCheckpoint(mlContext)
        // First 'normalize' the data (rescale to be
        // between -1 and 1 for all examples)
        .Append(mlContext.Regression.Trainers.StochasticDualCoordinateAscent("Target", "FeatureVector"));

// Step three. Fit the pipeline to the training data.
var model = pipeline.Fit(trainData);
```