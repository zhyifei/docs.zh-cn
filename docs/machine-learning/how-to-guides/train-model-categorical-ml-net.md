---
title: 应用特征工程学来进行分类数据模型定型 - ML.NET
description: 了解如何使用 ML.NET 将特征工程学应用于分类数据的机器学习模型定型
ms.date: 02/06/2018
ms.custom: mvc,how-to
ms.openlocfilehash: c24840ee89917d270bcbacbcf36905b4ee82a4aa
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092080"
---
# <a name="apply-feature-engineering-for-model-training-on-categorical-data---mlnet"></a><span data-ttu-id="7fdf4-103">应用特征工程学来进行分类数据模型定型 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="7fdf4-103">Apply feature engineering for model training on categorical data - ML.NET</span></span>

<span data-ttu-id="7fdf4-104">需要将任何非浮点型数据转换为 `float` 数据类型，因为所有 ML.NET `learners` 都预期特征是 `float vector`。</span><span class="sxs-lookup"><span data-stu-id="7fdf4-104">You need to convert any non float data to `float` data types since all ML.NET `learners` expect features as a `float vector`.</span></span>

<span data-ttu-id="7fdf4-105">如果数据集包含 `categorical` 数据（例如，“enum”），ML.NET 则提供几种方法来将其转换为功能：</span><span class="sxs-lookup"><span data-stu-id="7fdf4-105">If the dataset contains `categorical` data (for example, 'enum'), ML.NET offers several ways of converting it to features:</span></span>

- <span data-ttu-id="7fdf4-106">独热编码</span><span class="sxs-lookup"><span data-stu-id="7fdf4-106">One-hot encoding</span></span>
- <span data-ttu-id="7fdf4-107">基于哈希的独热编码</span><span class="sxs-lookup"><span data-stu-id="7fdf4-107">Hash-based one-hot encoding</span></span>
- <span data-ttu-id="7fdf4-108">二进制编码（将类别索引转换为位序列，并将位用作功能）</span><span class="sxs-lookup"><span data-stu-id="7fdf4-108">Binary encoding (convert category index into a bit sequence and use bits as features)</span></span>

<span data-ttu-id="7fdf4-109">如果某些类别的基数非常高（许多不同的值，通常出现一小部分），则 `one-hot encoding` 可能会很浪费。</span><span class="sxs-lookup"><span data-stu-id="7fdf4-109">A `one-hot encoding` can be wasteful if some categories are very high-cardinality (lots of different values, with a small set commonly occurring.</span></span> <span data-ttu-id="7fdf4-110">在这种情况下，使用基于计数的特征选择来减少要编码的插槽数。</span><span class="sxs-lookup"><span data-stu-id="7fdf4-110">In that case, reduce the number of slots to encode with count-based feature selection.</span></span>

<span data-ttu-id="7fdf4-111">直接在 ML.NET 学习管道中包含分类特征，以确保分类转换：</span><span class="sxs-lookup"><span data-stu-id="7fdf4-111">Include categorical featurization directly in the ML.NET learning pipeline to ensure that the categorical transformation:</span></span>

- <span data-ttu-id="7fdf4-112">仅使用定型数据进行“定型”，而不使用测试数据。</span><span class="sxs-lookup"><span data-stu-id="7fdf4-112">is only 'trained' on the training data, and not on your test data,</span></span>
- <span data-ttu-id="7fdf4-113">正确应用于新传入的数据，而无需在预测时进行额外的预处理。</span><span class="sxs-lookup"><span data-stu-id="7fdf4-113">is correctly applied to new incoming data, without extra pre-processing at prediction time.</span></span>

<span data-ttu-id="7fdf4-114">以下示例说明[成人人口普查数据集](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt)的分类处理：</span><span class="sxs-lookup"><span data-stu-id="7fdf4-114">The following example illustrates categorical handling for the [adult census dataset](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>

```console
Label   Workclass   education   marital-status  occupation  relationship    ethnicity   sex native-country-region   age fnlwgt  education-num   capital-gain    capital-loss    hours-per-week
0   Private 11th    Never-married   Machine-op-inspct   Own-child   Black   Male    United-States   25  226802  7   0   0   40
0   Private HS-grad Married-civ-spouse  Farming-fishing Husband White   Male    United-States   38  89814   9   0   0   50
1   Local-gov   Assoc-acdm  Married-civ-spouse  Protective-serv Husband White   Male    United-States   28  336951  12  0   0   40
1   Private Some-college    Married-civ-spouse  Machine-op-inspct   Husband Black   Male    United-States   44  160323  10  7688    0   40
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(new[] 
    {
        new TextLoader.Column("Label", DataKind.BL, 0),
        // We will load all the categorical features into one vector column of size 8.
        new TextLoader.Column("CategoricalFeatures", DataKind.TX, 1, 8),
        // Similarly, load all numerical features into one vector of size 6.
        new TextLoader.Column("NumericalFeatures", DataKind.R4, 9, 14),
        // Let's also separately load the 'Workclass' column.
        new TextLoader.Column("Workclass", DataKind.TX, 1),
    },
    hasHeader: true
);

// Read the data.
var data = reader.Read(dataPath);

// Inspect the first 10 records of the categorical columns to check that they are correctly read.
var catColumns = data.GetColumn<string[]>(mlContext, "CategoricalFeatures").Take(10).ToArray();

// Build several alternative featurization pipelines.
var pipeline =
    // Convert each categorical feature into one-hot encoding independently.
    mlContext.Transforms.Categorical.OneHotEncoding("CategoricalFeatures", "CategoricalOneHot")
        // Convert all categorical features into indices, and build a 'word bag' of these.
        .Append(mlContext.Transforms.Categorical.OneHotEncoding("CategoricalFeatures", "CategoricalBag",OneHotEncodingTransformer.OutputKind.Bag))
        // One-hot encode the workclass column, then drop all the categories that have fewer than 10 instances in the train set.
        .Append(mlContext.Transforms.Categorical.OneHotEncoding("Workclass", "WorkclassOneHot"))
        .Append(mlContext.Transforms.FeatureSelection.SelectFeaturesBasedOnCount("WorkclassOneHot", "WorkclassOneHotTrimmed", count: 10));

// Let's train our pipeline, and then apply it to the same data.
var transformedData = pipeline.Fit(data).Transform(data);

// Inspect some columns of the resulting dataset.
var categoricalBags = transformedData.GetColumn<float[]>(mlContext, "CategoricalBag").Take(10).ToArray();
var workclasses = transformedData.GetColumn<float[]>(mlContext, "WorkclassOneHotTrimmed").Take(10).ToArray();

// Of course, if we want to train the model, we will need to compose a single float vector of all the features.
// Here's how we could do this:

var fullLearningPipeline = pipeline
    // Concatenate two of the 3 categorical pipelines, and the numeric features.
    .Append(mlContext.Transforms.Concatenate("Features", "NumericalFeatures", "CategoricalBag", "WorkclassOneHotTrimmed"))
    // Cache data in memory so that the following trainer will be able to access training examples without
    // reading them from disk multiple times.
    .AppendCacheCheckpoint(mlContext)
    // Now we're ready to train. We chose our FastTree trainer for this classification task.
    .Append(mlContext.BinaryClassification.Trainers.FastTree(numTrees: 50));

// Train the model.
var model = fullLearningPipeline.Fit(data);
```
