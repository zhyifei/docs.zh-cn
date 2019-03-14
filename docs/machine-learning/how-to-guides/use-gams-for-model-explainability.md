---
title: 在 ML.NET 中使用广义加性模型和形状函数来解释模型
description: 在 ML.NET 中使用广义加性模型和形状函数来解释模型
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: f7b8b9a3daabb16f59c901911a1f6950ce864fff
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675584"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a><span data-ttu-id="4792f-103">在 ML.NET 中使用广义加性模型和形状函数来解释模型</span><span class="sxs-lookup"><span data-stu-id="4792f-103">Use Generalized Additive Models and shape functions for model explainability in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="4792f-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="4792f-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="4792f-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="4792f-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="4792f-106">此操作说明和相关示例目前使用的是 ML.NET 版本 0.10。</span><span class="sxs-lookup"><span data-stu-id="4792f-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="4792f-107">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="4792f-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="4792f-108">在创建机器学习模型时，仅仅进行预测通常是不够的。</span><span class="sxs-lookup"><span data-stu-id="4792f-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="4792f-109">机器学习开发人员、决策者以及受模型影响的人员通常需要了解机器学习模型如何做出决策，以及哪些特性有助于提高其性能。</span><span class="sxs-lookup"><span data-stu-id="4792f-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="4792f-110">广义加性模型 (GAM) 在 Microsoft 内部用于解释模型，帮助机器学习开发人员创建易于由他人解释的高容量模型。</span><span class="sxs-lookup"><span data-stu-id="4792f-110">**Generalized Additive Models (GAMs)** are used internally at Microsoft for model explainability to help machine learning developers create high-capacity models that can be easily interpreted by others.</span></span>

<span data-ttu-id="4792f-111">GAM 是一类可解释模型，为线性模型，其中的项是非线性函数，称为单个变量的“形状函数”。</span><span class="sxs-lookup"><span data-stu-id="4792f-111">GAMs are a class of **interpretable models** that are linear models where the terms are nonlinear functions, called "shape functions" of a single variable.</span></span> <span data-ttu-id="4792f-112">作为线性模型，它们易于解释，但由于模型学习的是特性函数，而不是单一权重，因此它们可以建立比简单线性模型更复杂的关系模型。</span><span class="sxs-lookup"><span data-stu-id="4792f-112">As linear models, they are easily interpreted but because the models learn functions of features instead of a single weight, they can model more complex relationships than a simple linear model.</span></span> <span data-ttu-id="4792f-113">生成的 GAM 预测器有一个表示定型集平均预测的截距项，以及表示与平均预测偏差的形状函数。</span><span class="sxs-lookup"><span data-stu-id="4792f-113">The resulting GAM predictor has an intercept term that represents the average prediction over the training set, and shape functions that represent the deviation from the average prediction.</span></span> <span data-ttu-id="4792f-114">可目测检查形状函数，以查看模型对某个特性的不同值的响应，并将其可视化，如以下在代码示例结束时创建的图表所示。</span><span class="sxs-lookup"><span data-stu-id="4792f-114">The shape functions can be inspected by eye to see the response of the model to different values of a feature, and visualized like the following graph that is created at the end of the code example.</span></span> <span data-ttu-id="4792f-115">ML.NET 中的 GAM 定型程序的实施是使用浅层梯度推进树（例如树桩）来学习非参数形状函数，它基于 Lou、Caruana 和 Gehrke 在[分类和回归的可识别模型](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf)中所述的方法。</span><span class="sxs-lookup"><span data-stu-id="4792f-115">The GAM trainer in ML.NET is implemented using shallow gradient boosted trees (for example tree stumps) to learn nonparametric shape functions, and is based on the method described in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) by Lou, Caruana, and Gehrke.</span></span>

```csharp
// Train the Generalized Additive Model
var fitPipeline = pipeline.Fit(data);
var gamModel = fitPipeline.LastTransformer.Model;

// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
Console.WriteLine($"Average predicted cost: {intercept:0.00}");

// Get the column names from the training set
var columnNames = data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Get the index of a variable from the training data
var myFeatureIndex = columnNames.ToList().FindIndex(str => str.Equals("MyFeature"));

// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetBinEffects(myFeatureIndex);

// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
{
    Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
}
```

![广义加性模型形状函数图](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

<span data-ttu-id="4792f-117">有关如何定型 GAM 模型并检查和解释结果的示例，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs)。</span><span class="sxs-lookup"><span data-stu-id="4792f-117">For a sample of how to train a GAM model and inspect and interpret the results, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span></span>
