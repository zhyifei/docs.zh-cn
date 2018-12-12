---
title: 使用非文本文件数据训练机器学习模型 - ML.NET
description: 了解如何使用 ML.NET 加载非文件训练数据，用于预测管道中的机器学习模型培训。
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 971c5c62acc9dd7bf29aa11ce898c2b76822c3d7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125397"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="3d933-103">使用非文本文件数据训练机器学习模型 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="3d933-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

<span data-ttu-id="3d933-104">ML.NET 的常见演示用例是使用 `TextLoader` 读取文件中的培训数据。</span><span class="sxs-lookup"><span data-stu-id="3d933-104">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="3d933-105">但是，在实际训练情景中，数据可能位于其他位置，例如：</span><span class="sxs-lookup"><span data-stu-id="3d933-105">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="3d933-106">SQL 表中</span><span class="sxs-lookup"><span data-stu-id="3d933-106">in SQL tables</span></span>
* <span data-ttu-id="3d933-107">从日志文件中提取</span><span class="sxs-lookup"><span data-stu-id="3d933-107">extracted from log files</span></span>
* <span data-ttu-id="3d933-108">动态生成</span><span class="sxs-lookup"><span data-stu-id="3d933-108">generated on the fly</span></span>

<span data-ttu-id="3d933-109">使用[架构理解](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md)将现有 C# `IEnumerable`作为 `DataView` 引入 ML.NET。</span><span class="sxs-lookup"><span data-stu-id="3d933-109">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="3d933-110">在此示例中，你将生成客户改动预测模型，并从生产系统中提取以下功能：</span><span class="sxs-lookup"><span data-stu-id="3d933-110">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="3d933-111">客户 ID（被模型忽略）</span><span class="sxs-lookup"><span data-stu-id="3d933-111">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="3d933-112">客户是否有改动（目标“标签”）</span><span class="sxs-lookup"><span data-stu-id="3d933-112">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="3d933-113">“人口统计类别”（一个字符串，如“年轻成人”等。）</span><span class="sxs-lookup"><span data-stu-id="3d933-113">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="3d933-114">最近 5 天访问次数。</span><span class="sxs-lookup"><span data-stu-id="3d933-114">The number of visits from the last 5 days.</span></span>

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

<span data-ttu-id="3d933-115">将数据加载到 `DataView`，使用以下代码训练模型：</span><span class="sxs-lookup"><span data-stu-id="3d933-115">Load this data into the `DataView` and train the model, using the following code:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.CreateStreamingDataView(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
