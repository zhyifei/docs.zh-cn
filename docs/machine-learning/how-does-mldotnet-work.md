---
title: 什么是 ML.NET 以及它如何工作？
description: ML.NET 使你能够在联机或脱机场景中将机器学习添加到 .NET 应用程序中。 借助此功能，可以使用应用程序的可用数据进行自动预测，而无需连接到网络以使用 ML.NET。 本文介绍 ML.NET 中机器学习的基础知识。
ms.date: 09/27/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
author: natke
ms.openlocfilehash: 1ae6b82ada841ad172cbe6a59b667aaaf619e714
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592052"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="9e3f9-105">什么是 ML.NET 以及它如何工作？</span><span class="sxs-lookup"><span data-stu-id="9e3f9-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="9e3f9-106">ML.NET 使你能够在联机或脱机场景中将机器学习添加到 .NET 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="9e3f9-107">借助此功能，可以使用应用程序的可用数据进行自动预测，而无需连接到网络。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-107">With this capability, you can make automatic predictions using the data available to your application without having to be connected to a network.</span></span> <span data-ttu-id="9e3f9-108">本文介绍 ML.NET 中机器学习的基础知识。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-108">This article explains the basics of machine learning in ML.NET.</span></span>

<span data-ttu-id="9e3f9-109">ML.NET 在使用 .NET Core 的 Windows、Linux 和 macOS 或使用 .NET Framework 的 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-109">ML.NET runs on Windows, Linux, and macOS using .NET Core, or Windows using .NET Framework.</span></span> <span data-ttu-id="9e3f9-110">所有平台均支持 64 位。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-110">64 bit is supported on all platforms.</span></span> <span data-ttu-id="9e3f9-111">Windows 支持 32 位，TensorFlow、LightGBM 和 ONNX 相关功能除外。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-111">32 bit is supported on Windows, except for TensorFlow, LightGBM, and ONNX related functionality.</span></span>

<span data-ttu-id="9e3f9-112">可以使用 ML.NET 进行的预测类型的示例包括：</span><span class="sxs-lookup"><span data-stu-id="9e3f9-112">Examples of the type of predictions that you can make with ML.NET include:</span></span>

|||
|-|-|
|<span data-ttu-id="9e3f9-113">分类/类别划分</span><span class="sxs-lookup"><span data-stu-id="9e3f9-113">Classification/Categorization</span></span>|<span data-ttu-id="9e3f9-114">自动将客户反馈划分为正面和负面类别</span><span class="sxs-lookup"><span data-stu-id="9e3f9-114">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="9e3f9-115">回归/预测连续值</span><span class="sxs-lookup"><span data-stu-id="9e3f9-115">Regression/Predict continuous values</span></span>|<span data-ttu-id="9e3f9-116">根据大小和位置预测房屋价格</span><span class="sxs-lookup"><span data-stu-id="9e3f9-116">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="9e3f9-117">异常情况检测</span><span class="sxs-lookup"><span data-stu-id="9e3f9-117">Anomaly Detection</span></span>|<span data-ttu-id="9e3f9-118">检测欺诈性银行交易</span><span class="sxs-lookup"><span data-stu-id="9e3f9-118">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="9e3f9-119">建议</span><span class="sxs-lookup"><span data-stu-id="9e3f9-119">Recommendations</span></span>|<span data-ttu-id="9e3f9-120">根据在线购物者之前的购买情况向其建议可能想要购买的产品</span><span class="sxs-lookup"><span data-stu-id="9e3f9-120">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="9e3f9-121">Hello ML.NET World</span><span class="sxs-lookup"><span data-stu-id="9e3f9-121">Hello ML.NET World</span></span>

<span data-ttu-id="9e3f9-122">以下代码片段中的代码演示了最简单的 ML.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-122">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="9e3f9-123">此示例构造线性回归模型，使用房屋大小和价格数据预测房屋价格。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-123">This example constructs a linear regression model to predict house prices using house size and price data.</span></span> <span data-ttu-id="9e3f9-124">在实际应用程序中，数据和模型将复杂得多。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-124">In your real-life applications, your data and model will be much more complex.</span></span>

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;
    
    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }
    
        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }
    
        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();
    
            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
    
            // 3. Train model
            var model = pipeline.Fit(trainingData);
    
            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    } 
```

## <a name="code-workflow"></a><span data-ttu-id="9e3f9-125">代码工作流</span><span class="sxs-lookup"><span data-stu-id="9e3f9-125">Code workflow</span></span>

<span data-ttu-id="9e3f9-126">以下关系图表示应用程序代码结构，以及模型开发的迭代过程：</span><span class="sxs-lookup"><span data-stu-id="9e3f9-126">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>

- <span data-ttu-id="9e3f9-127">将训练数据收集并加载到 **IDataView** 对象中</span><span class="sxs-lookup"><span data-stu-id="9e3f9-127">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="9e3f9-128">指定操作的管道，以提取特征并应用机器学习算法</span><span class="sxs-lookup"><span data-stu-id="9e3f9-128">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="9e3f9-129">通过在管道上调用 **Fit()** 来训练模型</span><span class="sxs-lookup"><span data-stu-id="9e3f9-129">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="9e3f9-130">评估模型并通过迭代进行改进</span><span class="sxs-lookup"><span data-stu-id="9e3f9-130">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="9e3f9-131">将模型保存为二进制格式，以便在应用程序中使用</span><span class="sxs-lookup"><span data-stu-id="9e3f9-131">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="9e3f9-132">将模型加载回 **ITransformer** 对象</span><span class="sxs-lookup"><span data-stu-id="9e3f9-132">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="9e3f9-133">通过调用 **CreatePredictionEngine.Predict()** 进行预测</span><span class="sxs-lookup"><span data-stu-id="9e3f9-133">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![ML.NET 应用程序开发流包括用于数据生成、管道开发、模型训练、模型评估和模型使用的组件](./media/mldotnet-annotated-workflow.png) 

<span data-ttu-id="9e3f9-135">让我们更深入地探讨这些概念。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-135">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="9e3f9-136">机器学习模型</span><span class="sxs-lookup"><span data-stu-id="9e3f9-136">Machine learning model</span></span>

<span data-ttu-id="9e3f9-137">ML.NET 模型是一个对象，它包含为了获得预测输出而要对输入数据执行的转换。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-137">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="9e3f9-138">Basic</span><span class="sxs-lookup"><span data-stu-id="9e3f9-138">Basic</span></span>

<span data-ttu-id="9e3f9-139">最基本的模型是二维线性回归，其中一个连续数量与另一个连续数量成比例关系，如上述房价示例所示。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-139">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span> 

![具有偏差和权重参数的线性回归模型](./media/linear-regression-model.svg)

<span data-ttu-id="9e3f9-141">模型很简单：$Price = b + Size \* w$。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-141">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="9e3f9-142">参数 $b$ 和 $w$ 通过根据一组 (size, price) 对拟合一根直线来进行估算。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-142">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="9e3f9-143">用于查找模型参数的数据称为**训练数据**。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-143">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="9e3f9-144">机器学习模型的输入称为**特征**。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-144">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="9e3f9-145">在此示例中，$Size$ 是唯一的特征。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-145">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="9e3f9-146">用于训练机器学习模型的真值称为**标签**。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-146">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="9e3f9-147">此处训练数据集中的 $Price$ 值是标签。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-147">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="9e3f9-148">更复杂</span><span class="sxs-lookup"><span data-stu-id="9e3f9-148">More complex</span></span>

<span data-ttu-id="9e3f9-149">更复杂的模型使用事务文本描述将金融事务分类为类别。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-149">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="9e3f9-150">通过删除冗余的字词和字符，以及对字词和字符组合进行计数，每个事务描述都被分解为一组特征。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-150">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="9e3f9-151">该特征集用于基于训练数据中的类别集训练线性模型。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-151">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="9e3f9-152">新描述与训练集中的描述越相似，它就越有可能被分配到同一类别。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-152">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span> 

![文本分类模型](./media/text-classification-model.svg)

<span data-ttu-id="9e3f9-154">房屋价格模型和文本分类模型均为**线性**模型。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-154">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="9e3f9-155">根据数据的性质和要解决的问题，还可以使用**决策树**模型、**广义加性**模型和其他模型。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-155">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="9e3f9-156">可以在[任务](./resources/tasks.md)中找到有关模型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-156">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="9e3f9-157">数据准备</span><span class="sxs-lookup"><span data-stu-id="9e3f9-157">Data preparation</span></span>

<span data-ttu-id="9e3f9-158">在大多数情况下，可用的数据不适合直接用于训练机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-158">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="9e3f9-159">需要准备或预处理原始数据，然后才能将其用于查找模型的参数。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-159">The raw data needs to be prepared, or pre-processed before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="9e3f9-160">数据可能需要从字符串值转换为数字表示形式。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-160">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="9e3f9-161">输入数据中可能会包含冗余信息。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-161">You might have redundant information in your input data.</span></span> <span data-ttu-id="9e3f9-162">可能需要缩小或放大输入数据的维度。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-162">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="9e3f9-163">数据可能需要进行规范化或缩放。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-163">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="9e3f9-164">[ML.NET 教程](./tutorials/index.md)讲解用于特定机器学习任务的文本、图像、数字和时序数据的不同数据处理管道。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-164">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="9e3f9-165">[如何准备数据](./how-to-guides/prepare-data-ml-net.md)展示了如何更广泛地应用数据准备。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-165">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to applied data preparation more generally.</span></span>

<span data-ttu-id="9e3f9-166">可以在“资源”部分找到所有[可用转换](./resources/transforms.md)的附录。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-166">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="9e3f9-167">模型评估</span><span class="sxs-lookup"><span data-stu-id="9e3f9-167">Model evaluation</span></span>

<span data-ttu-id="9e3f9-168">训练模型后，如何了解其进行未来预测的表现如何？</span><span class="sxs-lookup"><span data-stu-id="9e3f9-168">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="9e3f9-169">借助 ML.NET，可以根据一些新的测试数据评估模型。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-169">With ML.NET, you can evaluate your model against some new test data.</span></span> 

<span data-ttu-id="9e3f9-170">每种类型的机器学习任务都具有用于根据测试数据集评估模型的准确性和精确性的指标。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-170">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="9e3f9-171">对于我们的房屋价格示例，我们使用了**回归**任务。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-171">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="9e3f9-172">若要评估模型，请将以下代码添加到原始示例中。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-172">To evaluate the model, add the following code to the original sample.</span></span>

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);
                
        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

<span data-ttu-id="9e3f9-173">通过评估指标可得知错误率相当低，且预测输出和测试输出之间的相关性很高。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-173">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="9e3f9-174">这很简单！</span><span class="sxs-lookup"><span data-stu-id="9e3f9-174">That was easy!</span></span> <span data-ttu-id="9e3f9-175">在实际示例中，需要进行更多调整才能获得良好的模型指标。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-175">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="9e3f9-176">ML.NET 体系结构</span><span class="sxs-lookup"><span data-stu-id="9e3f9-176">ML.NET architecture</span></span>

<span data-ttu-id="9e3f9-177">在本部分中，我们将介绍 ML.NET 的体系结构模式。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-177">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="9e3f9-178">如果你是一位经验丰富的 .NET 开发人员，则你对其中一些模式可能已经很熟悉，但对有些模式则不那么熟悉。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-178">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="9e3f9-179">集中精神，让我们开始深入探索！</span><span class="sxs-lookup"><span data-stu-id="9e3f9-179">Hold tight, while we dive in!</span></span>

<span data-ttu-id="9e3f9-180">ML.NET 应用程序从 <xref:Microsoft.ML.MLContext> 对象开始。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-180">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="9e3f9-181">此单一实例对象包含**目录**。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-181">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="9e3f9-182">目录是用于数据加载和保存、转换、训练程序和模型操作组件的工厂。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-182">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="9e3f9-183">每个目录对象都具有创建不同类型的组件的方法：</span><span class="sxs-lookup"><span data-stu-id="9e3f9-183">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="9e3f9-184">数据加载和保存</span><span class="sxs-lookup"><span data-stu-id="9e3f9-184">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="9e3f9-185">数据准备</span><span class="sxs-lookup"><span data-stu-id="9e3f9-185">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="9e3f9-186">训练算法</span><span class="sxs-lookup"><span data-stu-id="9e3f9-186">Training algorithms</span></span>|<span data-ttu-id="9e3f9-187">二元分类</span><span class="sxs-lookup"><span data-stu-id="9e3f9-187">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="9e3f9-188">多类分类</span><span class="sxs-lookup"><span data-stu-id="9e3f9-188">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="9e3f9-189">异常情况检测</span><span class="sxs-lookup"><span data-stu-id="9e3f9-189">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="9e3f9-190">聚类分析</span><span class="sxs-lookup"><span data-stu-id="9e3f9-190">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="9e3f9-191">预测</span><span class="sxs-lookup"><span data-stu-id="9e3f9-191">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="9e3f9-192">排名</span><span class="sxs-lookup"><span data-stu-id="9e3f9-192">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="9e3f9-193">回归测试</span><span class="sxs-lookup"><span data-stu-id="9e3f9-193">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="9e3f9-194">建议</span><span class="sxs-lookup"><span data-stu-id="9e3f9-194">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="9e3f9-195">添加 `Microsoft.ML.Recommender` NuGet 包</span><span class="sxs-lookup"><span data-stu-id="9e3f9-195">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="9e3f9-196">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="9e3f9-196">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="9e3f9-197">添加 `Microsoft.ML.TimeSeries` NuGet 包</span><span class="sxs-lookup"><span data-stu-id="9e3f9-197">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="9e3f9-198">模型使用</span><span class="sxs-lookup"><span data-stu-id="9e3f9-198">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="9e3f9-199">可以导航到上述各个类别的创建方法。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-199">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="9e3f9-200">使用 Visual Studio 时，目录通过 IntelliSense 显示。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-200">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![用于回归训练程序的 Intellisense](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="9e3f9-202">生成管道</span><span class="sxs-lookup"><span data-stu-id="9e3f9-202">Build the pipeline</span></span>

<span data-ttu-id="9e3f9-203">每个目录中都有一组扩展方法。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-203">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="9e3f9-204">让我们看看如何使用扩展方法创建训练管道。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-204">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="9e3f9-205">在代码片段中，`Concatenate` 和 `Sdca` 均为目录中的方法。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-205">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="9e3f9-206">它们各创建一个追加到管道的 [IEstimator](xref:Microsoft.ML.IEstimator%601) 对象。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-206">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="9e3f9-207">此时，仅创建对象。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-207">At this point, the objects are created only.</span></span> <span data-ttu-id="9e3f9-208">不进行任何执行操作。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-208">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="9e3f9-209">定型模型</span><span class="sxs-lookup"><span data-stu-id="9e3f9-209">Train the model</span></span>

<span data-ttu-id="9e3f9-210">在管道中创建对象后，即可使用数据来训练模型。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-210">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="9e3f9-211">调用 `Fit()` 使用输入训练数据来估算模型的参数。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-211">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="9e3f9-212">这称为训练模型。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-212">This is known as training the model.</span></span> <span data-ttu-id="9e3f9-213">请记住，上述线性回归模型有两个模型参数：**偏差**和**权重**。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-213">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="9e3f9-214">在 `Fit()` 调用后，参数的值是已知的。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-214">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="9e3f9-215">大部分模型拥有的参数比这多得多。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-215">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="9e3f9-216">可以在[如何训练模型](./how-to-guides/train-machine-learning-model-ml-net.md)中了解有关模型训练的详细信息</span><span class="sxs-lookup"><span data-stu-id="9e3f9-216">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md)</span></span>

<span data-ttu-id="9e3f9-217">生成的模型对象实现 <xref:Microsoft.ML.ITransformer> 接口。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-217">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="9e3f9-218">也就是说，模型将输入数据转换为预测。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-218">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="9e3f9-219">使用模型</span><span class="sxs-lookup"><span data-stu-id="9e3f9-219">Use the model</span></span>

<span data-ttu-id="9e3f9-220">可以将输入数据批量转换为预测，也可以一次转换一个输入。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-220">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="9e3f9-221">在房屋价格示例中，我们同时执行了两种操作：为了评估模型而执行批量转换，以及为了进行新预测而执行单次转换。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-221">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="9e3f9-222">让我们进行单个预测。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-222">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```
 
<span data-ttu-id="9e3f9-223">`CreatePredictionEngine()` 方法接受一个输入类和一个输出类。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-223">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="9e3f9-224">字段名称和/或代码属性确定模型训练和预测期间使用的数据列的名称。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-224">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="9e3f9-225">可以在“操作说明”部分中了解[如何进行单个预测](./how-to-guides/single-predict-model-ml-net.md)。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-225">You can read about  [How to make a single prediction](./how-to-guides/single-predict-model-ml-net.md) in the How-to section.</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="9e3f9-226">数据模型和架构</span><span class="sxs-lookup"><span data-stu-id="9e3f9-226">Data models and schema</span></span>

<span data-ttu-id="9e3f9-227">ML.NET 机器学习管道的核心是 [DataView](xref:Microsoft.ML.IDataView) 对象。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-227">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="9e3f9-228">管道中的每个转换都有一个输入架构（转换期望在其输入中看到的数据名称、类型和大小）；以及一个输出架构（转换在转换后生成的数据名称、类型和大小）。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-228">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> <span data-ttu-id="9e3f9-229">下面的文档提供 [IDataView 接口及其类型系统](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html)的深度解析。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-229">The following document provides an in-depth explanation of the [IDataView interface and its type system](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span></span>

<span data-ttu-id="9e3f9-230">如果管道中一个转换的输出架构与下一个转换的输入架构不匹配，ML.NET 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-230">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="9e3f9-231">数据视图对象具有列和行。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-231">A data view object has columns and rows.</span></span> <span data-ttu-id="9e3f9-232">每个列都有名称、类型和长度。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-232">Each column has a name and a type and a length.</span></span> <span data-ttu-id="9e3f9-233">例如：房屋价格示例中的输入列为**大小**和**价格**。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-233">For example: the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="9e3f9-234">它们都是类型，且它们是标量数量而不是向量数量。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-234">They are both type  and they are scalar quantities rather than vector ones.</span></span>

   ![具有房屋价格预测数据的 ML.NET 数据视图示例](./media/ml-net-dataview.png)

<span data-ttu-id="9e3f9-236">所有 ML.NET 算法都在寻找属于向量的输入列。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-236">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="9e3f9-237">默认情况下，此向量列称为**特征**。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-237">By default this vector column is called **Features**.</span></span> <span data-ttu-id="9e3f9-238">这就是我们在房屋价格示例中将**大小**列连接到名为**特征**的新列中的原因。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-238">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="9e3f9-239">所有算法在执行预测后还会创建新列。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-239">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="9e3f9-240">这些新列的固定名称取决于机器学习算法的类型。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-240">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="9e3f9-241">对于回归任务，其中一个新列称为**分数**。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-241">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="9e3f9-242">这就是我们将价格数据归为此名称的原因。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-242">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```    

<span data-ttu-id="9e3f9-243">可以在[机器学习任务](resources/tasks.md)指南中找到有关不同机器学习任务的输出列的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-243">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="9e3f9-244">DataView 对象的一个​​重要属性是它们被**惰性**求值。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-244">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="9e3f9-245">数据视图仅在模型训练和评估以及数据预测期间加载及运行。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-245">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="9e3f9-246">在编写和测试 ML.NET 应用程序时，可以使用 Visual Studio 调试程序通过调用 [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) 方法来浏览任何数据视图对象。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-246">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="9e3f9-247">可以在调试程序中查看 `debug` 变量并检查其内容。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-247">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="9e3f9-248">不要在生产代码中使用 Preview 方法，因为它会大幅降低性能。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-248">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="9e3f9-249">模型部署</span><span class="sxs-lookup"><span data-stu-id="9e3f9-249">Model Deployment</span></span>

<span data-ttu-id="9e3f9-250">在实际应用程序中，模型训练和评估代码将与预测分离。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-250">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="9e3f9-251">事实上，这两项活动通常由单独的团队执行。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-251">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="9e3f9-252">模型开发团队可以保存模型以便用于预测应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-252">Your model development team can save the model for use in the prediction application.</span></span>

```csharp   
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="where-to-now"></a><span data-ttu-id="9e3f9-253">接下来做什么？</span><span class="sxs-lookup"><span data-stu-id="9e3f9-253">Where to now?</span></span>

<span data-ttu-id="9e3f9-254">可以在[教程](./tutorials/index.md)中了解如何使用不同的机器学习任务和更实际的数据集来生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-254">You can learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

<span data-ttu-id="9e3f9-255">或者，可以在[操作指南](./how-to-guides/index.md)中更深入地了解特定主题。</span><span class="sxs-lookup"><span data-stu-id="9e3f9-255">Or you can learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

<span data-ttu-id="9e3f9-256">如果非常感兴趣，可以直接阅读 [API 参考文档](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)！</span><span class="sxs-lookup"><span data-stu-id="9e3f9-256">And if you're super keen, you can dive straight into the [API Reference documentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)!</span></span>
