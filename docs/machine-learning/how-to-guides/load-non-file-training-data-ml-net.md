---
title: 使用非文本文件数据训练机器学习模型 - ML.NET
description: 了解如何使用 ML.NET 加载非文件训练数据，用于预测管道中的机器学习模型培训。
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 27b327a63cb55b7fce0f4ff7facd3ee7c4a1c85c
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678606"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="47900-103">使用非文本文件数据训练机器学习模型 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="47900-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="47900-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="47900-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="47900-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="47900-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="47900-106">此操作说明和相关示例目前使用的是 ML.NET 版本 0.10。</span><span class="sxs-lookup"><span data-stu-id="47900-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="47900-107">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="47900-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="47900-108">ML.NET 的常见演示用例是使用 `TextLoader` 读取文件中的培训数据。</span><span class="sxs-lookup"><span data-stu-id="47900-108">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="47900-109">但是，在实际训练情景中，数据可能位于其他位置，例如：</span><span class="sxs-lookup"><span data-stu-id="47900-109">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="47900-110">SQL 表中</span><span class="sxs-lookup"><span data-stu-id="47900-110">in SQL tables</span></span>
* <span data-ttu-id="47900-111">从日志文件中提取</span><span class="sxs-lookup"><span data-stu-id="47900-111">extracted from log files</span></span>
* <span data-ttu-id="47900-112">动态生成</span><span class="sxs-lookup"><span data-stu-id="47900-112">generated on the fly</span></span>

<span data-ttu-id="47900-113">使用[架构理解](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md)将现有 C# `IEnumerable`作为 `DataView` 引入 ML.NET。</span><span class="sxs-lookup"><span data-stu-id="47900-113">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="47900-114">在此示例中，你将生成客户改动预测模型，并从生产系统中提取以下功能：</span><span class="sxs-lookup"><span data-stu-id="47900-114">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="47900-115">客户 ID（被模型忽略）</span><span class="sxs-lookup"><span data-stu-id="47900-115">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="47900-116">客户是否有改动（目标“标签”）</span><span class="sxs-lookup"><span data-stu-id="47900-116">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="47900-117">“人口统计类别”（一个字符串，如“年轻成人”等。）</span><span class="sxs-lookup"><span data-stu-id="47900-117">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="47900-118">最近 5 天访问次数。</span><span class="sxs-lookup"><span data-stu-id="47900-118">The number of visits from the last 5 days.</span></span>

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

<span data-ttu-id="47900-119">将数据加载到 `DataView`，使用以下代码训练模型：</span><span class="sxs-lookup"><span data-stu-id="47900-119">Load this data into the `DataView` and train the model, using the following code:</span></span>

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
var trainData = mlContext.Data.ReadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
