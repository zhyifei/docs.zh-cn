---
title: 计算用于评估机器学习模型质量的指标 - ML.NET
description: 了解如何使用 ML.NET 来计算用于评估和验证机器学习模型质量的指标
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: ad71f7da6981ac370e60725f88d3c70b1d5c5237
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679211"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a><span data-ttu-id="84ae7-103">计算用于评估机器学习模型质量的指标 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="84ae7-103">Calculate metrics to evaluate machine learning model quality - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="84ae7-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="84ae7-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="84ae7-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="84ae7-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="84ae7-106">此操作说明和相关示例目前使用的是 ML.NET 版本 0.10。</span><span class="sxs-lookup"><span data-stu-id="84ae7-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="84ae7-107">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="84ae7-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="84ae7-108">训练模型后如何评估质量？</span><span class="sxs-lookup"><span data-stu-id="84ae7-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="84ae7-109">每个机器学习任务都会公开用于质量评估的指标。</span><span class="sxs-lookup"><span data-stu-id="84ae7-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="84ae7-110">可使用任务的相应“上下文”来评估模型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="84ae7-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```