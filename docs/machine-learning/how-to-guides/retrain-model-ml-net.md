---
title: 重新训练模型
description: 了解如何在 ML.NET 中重新训练模型
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 2f8f8c035166612aabede8a512485bdf296c5655
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557909"
---
# <a name="re-train-a-model"></a><span data-ttu-id="4ef51-103">重新训练模型</span><span class="sxs-lookup"><span data-stu-id="4ef51-103">Re-train a model</span></span>

<span data-ttu-id="4ef51-104">了解如何在 ML.NET 中重新训练机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="4ef51-104">Learn how to retrain a machine learning model in ML.NET.</span></span>

<span data-ttu-id="4ef51-105">这个世界和它周围的数据在不断变化。</span><span class="sxs-lookup"><span data-stu-id="4ef51-105">The world and the data around it change at a constant pace.</span></span> <span data-ttu-id="4ef51-106">因此，模型也需要更改和更新。</span><span class="sxs-lookup"><span data-stu-id="4ef51-106">As such, models need to change and update as well.</span></span> <span data-ttu-id="4ef51-107">借助 ML.NET 提供的功能，可以将已学习的模型参数作为起点并不断汲取以往经验来重新训练模型，而不必每次都从头开始。</span><span class="sxs-lookup"><span data-stu-id="4ef51-107">ML.NET provides functionality for re-training models using learned model parameters as a starting point to continually build on previous experience rather than starting from scratch every time.</span></span>  

<span data-ttu-id="4ef51-108">以下算法可在 ML.NET 中重新训练：</span><span class="sxs-lookup"><span data-stu-id="4ef51-108">The following algorithms are re-trainable in ML.NET:</span></span>

- [<span data-ttu-id="4ef51-109">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-109">AveragedPerceptronTrainer</span></span>](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [<span data-ttu-id="4ef51-110">FieldAwareFactorizationMachineTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-110">FieldAwareFactorizationMachineTrainer</span></span>](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [<span data-ttu-id="4ef51-111">LbfgsLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-111">LbfgsLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [<span data-ttu-id="4ef51-112">LbfgsMaximumEntropyMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-112">LbfgsMaximumEntropyMulticlassTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [<span data-ttu-id="4ef51-113">LbfgsPoissonRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-113">LbfgsPoissonRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [<span data-ttu-id="4ef51-114">LinearSvmTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-114">LinearSvmTrainer</span></span>](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [<span data-ttu-id="4ef51-115">OnlineGradientDescentTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-115">OnlineGradientDescentTrainer</span></span>](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [<span data-ttu-id="4ef51-116">SgdCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-116">SgdCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [<span data-ttu-id="4ef51-117">SgdNonCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-117">SgdNonCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [<span data-ttu-id="4ef51-118">SymbolicSgdLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="4ef51-118">SymbolicSgdLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a><span data-ttu-id="4ef51-119">加载预先训练的模型</span><span class="sxs-lookup"><span data-stu-id="4ef51-119">Load pre-trained model</span></span>

<span data-ttu-id="4ef51-120">首先，将预先训练的模型加载到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="4ef51-120">First, load the pre-trained model into your application.</span></span> <span data-ttu-id="4ef51-121">若要了解有关加载训练管道和模型的详细信息，请参阅相关的[操作说明文章](./consuming-model-ml-net.md)。</span><span class="sxs-lookup"><span data-stu-id="4ef51-121">To learn more about loading training pipelines and models, see the related [how-to article](./consuming-model-ml-net.md).</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema of data prep pipeline and trained model
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data prepration pipeline
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip", out dataPrepPipelineSchema);

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("ogd_model.zip", out modelSchema);
```

## <a name="extract-pre-trained-model-parameters"></a><span data-ttu-id="4ef51-122">提取预先训练的模型参数</span><span class="sxs-lookup"><span data-stu-id="4ef51-122">Extract pre-trained model parameters</span></span>

<span data-ttu-id="4ef51-123">加载模型后，通过访问预先训练模型的 [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) 属性来提取已学习的模型参数。</span><span class="sxs-lookup"><span data-stu-id="4ef51-123">Once the model is loaded, extract the learned model parameters by accessing the [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) property of the pre-trained model.</span></span> <span data-ttu-id="4ef51-124">使用线性回归模型 [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) 训练预先训练的模型，该线性回归模型可创建输出 [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) 的 [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601)。</span><span class="sxs-lookup"><span data-stu-id="4ef51-124">The pre-trained model was trained using the linear regression model [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) which creates a[`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) that outputs [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span></span> <span data-ttu-id="4ef51-125">这些线性回归模型参数包含模型已学习的偏差和权重或系数。</span><span class="sxs-lookup"><span data-stu-id="4ef51-125">These linear regression model parameters contain the learned bias and weights or coefficients of the model.</span></span> <span data-ttu-id="4ef51-126">这些值将用作新的重新训练模型的起点。</span><span class="sxs-lookup"><span data-stu-id="4ef51-126">These values will be used as a starting point for the new re-trained model.</span></span>

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters = 
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a><span data-ttu-id="4ef51-127">重新训练模型</span><span class="sxs-lookup"><span data-stu-id="4ef51-127">Re-train model</span></span>

<span data-ttu-id="4ef51-128">重新训练模型的过程与训练模型的过程没有什么不同。</span><span class="sxs-lookup"><span data-stu-id="4ef51-128">The process for retraining a model is no different than that of training a model.</span></span> <span data-ttu-id="4ef51-129">唯一的区别是，除了数据之外，[`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) 方法还将原始学习模型参数作为输入，并将它们用作重新训练过程的起点。</span><span class="sxs-lookup"><span data-stu-id="4ef51-129">The only difference is, the [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) method in addition to the data also takes as input the original learned model parameters and uses them as a starting point in the re-training process.</span></span>  

```csharp
// New Data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};

//Load New Data
IDataView newData = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Preprocess Data
IDataView transformedNewData = dataPrepPipeline.Transform(newData);

// Retrain model
RegressionPredictionTransformer<LinearRegressionModelParameters> retrainedModel = 
    mlContext.Regression.Trainers.OnlineGradientDescent()
        .Fit(transformedNewData, originalModelParameters);
```

## <a name="compare-model-parameters"></a><span data-ttu-id="4ef51-130">比较模型参数</span><span class="sxs-lookup"><span data-stu-id="4ef51-130">Compare model parameters</span></span>

<span data-ttu-id="4ef51-131">如何知道是否真的进行了重新训练？</span><span class="sxs-lookup"><span data-stu-id="4ef51-131">How do you know if re-training actually happened?</span></span> <span data-ttu-id="4ef51-132">一种方法是比较重新训练模型的参数是否与原始模型的参数不同。</span><span class="sxs-lookup"><span data-stu-id="4ef51-132">One way would be to compare whether the re-trained model's parameters are different than those of the original model.</span></span> <span data-ttu-id="4ef51-133">下面的代码示例将原始模型与重新训练模型的权重进行比较，并将它们输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="4ef51-133">The code sample below compares the original against the re-trained model weights and outputs them to the console.</span></span>

```csharp
// Extract Model Parameters of re-trained model
LinearRegressionModelParameters retrainedModelParameters = retrainedModel.Model as LinearRegressionModelParameters;

// Inspect Change in Weights
var weightDiffs = 
    originalModelParameters.Weights.Zip(
        retrainedModelParameters.Weights, (original, retrained) => original - retrained).ToArray();

Console.WriteLine("Original | Retrained | Difference");
for(int i=0;i < weightDiffs.Count();i++)
{
    Console.WriteLine($"{originalModelParameters.Weights[i]} | {retrainedModelParameters.Weights[i]} | {weightDiffs[i]}");
}
```

<span data-ttu-id="4ef51-134">下表显示了可能的输出。</span><span class="sxs-lookup"><span data-stu-id="4ef51-134">The table below shows what the output might look like.</span></span> 

|<span data-ttu-id="4ef51-135">原始</span><span class="sxs-lookup"><span data-stu-id="4ef51-135">Original</span></span> | <span data-ttu-id="4ef51-136">重新训练后</span><span class="sxs-lookup"><span data-stu-id="4ef51-136">Retrained</span></span> | <span data-ttu-id="4ef51-137">差值</span><span class="sxs-lookup"><span data-stu-id="4ef51-137">Difference</span></span> |
|---|---|---|
| <span data-ttu-id="4ef51-138">33039.86</span><span class="sxs-lookup"><span data-stu-id="4ef51-138">33039.86</span></span> | <span data-ttu-id="4ef51-139">56293.76</span><span class="sxs-lookup"><span data-stu-id="4ef51-139">56293.76</span></span> | <span data-ttu-id="4ef51-140">-23253.9</span><span class="sxs-lookup"><span data-stu-id="4ef51-140">-23253.9</span></span> |
| <span data-ttu-id="4ef51-141">29099.14</span><span class="sxs-lookup"><span data-stu-id="4ef51-141">29099.14</span></span> | <span data-ttu-id="4ef51-142">49586.03</span><span class="sxs-lookup"><span data-stu-id="4ef51-142">49586.03</span></span> | <span data-ttu-id="4ef51-143">-20486.89</span><span class="sxs-lookup"><span data-stu-id="4ef51-143">-20486.89</span></span> |
| <span data-ttu-id="4ef51-144">28938.38</span><span class="sxs-lookup"><span data-stu-id="4ef51-144">28938.38</span></span> | <span data-ttu-id="4ef51-145">48609.23</span><span class="sxs-lookup"><span data-stu-id="4ef51-145">48609.23</span></span> | <span data-ttu-id="4ef51-146">-19670.85</span><span class="sxs-lookup"><span data-stu-id="4ef51-146">-19670.85</span></span> |
| <span data-ttu-id="4ef51-147">30484.02</span><span class="sxs-lookup"><span data-stu-id="4ef51-147">30484.02</span></span> | <span data-ttu-id="4ef51-148">53745.43</span><span class="sxs-lookup"><span data-stu-id="4ef51-148">53745.43</span></span> | <span data-ttu-id="4ef51-149">-23261.41</span><span class="sxs-lookup"><span data-stu-id="4ef51-149">-23261.41</span></span> |
