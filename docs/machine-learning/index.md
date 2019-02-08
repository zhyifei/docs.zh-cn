---
title: ML.NET 内容指南
description: 了解如何使用 ML.NET 生成自定义 AI 解决方案并将其集成到 .NET 应用程序。
ms.date: 01/18/2019
ms.custom: seodec18
ms.openlocfilehash: 37496adb20cfe38e731c9c8364b6f9cff319f6c4
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826253"
---
# <a name="mlnet-content-guide"></a><span data-ttu-id="d28b4-103">ML.NET 内容指南</span><span class="sxs-lookup"><span data-stu-id="d28b4-103">ML.NET Content Guide</span></span>

<span data-ttu-id="d28b4-104">此指南介绍基本概念，并提供有关使用 ML.NET 的教程和 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d28b4-104">This guide explains basic concepts and provides tutorials and an API reference for working with ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="d28b4-105">本文档引用 ML.NET（目前为预览版）。</span><span class="sxs-lookup"><span data-stu-id="d28b4-105">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="d28b4-106">材料可能会有所变化。</span><span class="sxs-lookup"><span data-stu-id="d28b4-106">Material may be subject to change.</span></span> <span data-ttu-id="d28b4-107">有关详细信息，请参阅 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="d28b4-107">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="get-started"></a><span data-ttu-id="d28b4-108">入门</span><span class="sxs-lookup"><span data-stu-id="d28b4-108">Get started</span></span>

<span data-ttu-id="d28b4-109">若要在 ML.NET 中安装并开始构建，请按照[入门教程](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial)操作。</span><span class="sxs-lookup"><span data-stu-id="d28b4-109">To install and start building in ML.NET, follow the [Get started tutorial](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span></span>

<span data-ttu-id="d28b4-110">若要了解有关 ML.NET 的信息，请参阅[什么是 ML.NET？](what-is-mldotnet.md)</span><span class="sxs-lookup"><span data-stu-id="d28b4-110">To learn about ML.NET, see [What is ML.NET?](what-is-mldotnet.md)</span></span>

<span data-ttu-id="d28b4-111">要了解基本知识，请参阅 [ML.NET 中模型定型的基本概念](basic-concepts-model-training-in-mldotnet.md)。</span><span class="sxs-lookup"><span data-stu-id="d28b4-111">To understand basics, see [Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span></span>

## <a name="tutorials"></a><span data-ttu-id="d28b4-112">教程</span><span class="sxs-lookup"><span data-stu-id="d28b4-112">Tutorials</span></span>

<span data-ttu-id="d28b4-113">[使用二元分类模型分析情绪](tutorials/sentiment-analysis.md)演示如何构建确定情绪是积极还是消极的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d28b4-113">[Analyze sentiment using a binary classification model](tutorials/sentiment-analysis.md) shows you how to build an app that determines whether sentiment is positive or negative.</span></span>

<span data-ttu-id="d28b4-114">[使用多类分类模型对 GitHub 问题分类](tutorials/github-issue-classification.md)展示了如何生成可确定 GitHub 问题的“区域”标签的应用。</span><span class="sxs-lookup"><span data-stu-id="d28b4-114">[Classify GitHub issues using a multiclass classification model](tutorials/github-issue-classification.md) shows you how to build an app that determines the Area label for a GitHub issue.</span></span>

<span data-ttu-id="d28b4-115">[使用回归模型预测价格](tutorials/taxi-fare.md)演示如何构建一个使用历史数据中的许多因素来确定答案的预测性应用程序。</span><span class="sxs-lookup"><span data-stu-id="d28b4-115">[Predict prices using a regression model](tutorials/taxi-fare.md) shows you how to build a predictive app that uses many factors from historical data to determine the answer.</span></span>

<span data-ttu-id="d28b4-116">[根据特征对鸢尾花进行分类](tutorials/iris-clustering.md)演示如何使用聚类分析模型来分析鸢尾花数据集。</span><span class="sxs-lookup"><span data-stu-id="d28b4-116">[Classify iris flowers by features](tutorials/iris-clustering.md) shows you how to use a clustering model to analyze the iris data set.</span></span> 

## <a name="how-to-guide"></a><span data-ttu-id="d28b4-117">操作指南</span><span class="sxs-lookup"><span data-stu-id="d28b4-117">How to guide</span></span>

<span data-ttu-id="d28b4-118">[使用 Infer.NET 和概率性编程建立一个游戏配对列表应用](how-to-guides/matchup-app-infer-net.md)演示如何构建一个简化版的配对应用，就像在 Xbox 游戏中看到的那样。</span><span class="sxs-lookup"><span data-stu-id="d28b4-118">[Build a game match-up list app with Infer.NET and probabilistic programming](how-to-guides/matchup-app-infer-net.md) shows you how to build a simplified version of a match-up app like you'd see in an Xbox game.</span></span>

## <a name="resources"></a><span data-ttu-id="d28b4-119">资源</span><span class="sxs-lookup"><span data-stu-id="d28b4-119">Resources</span></span>

<span data-ttu-id="d28b4-120">[机器学习术语表](resources/glossary.md)定义关键术语。</span><span class="sxs-lookup"><span data-stu-id="d28b4-120">[Machine learning glossary](resources/glossary.md) defines key terminology.</span></span>

<span data-ttu-id="d28b4-121">[机器学习任务](resources/tasks.md)描述任务，例如分类和异常情况检测。</span><span class="sxs-lookup"><span data-stu-id="d28b4-121">[Machine learning tasks](resources/tasks.md) describes tasks, such as classification and anomaly detection.</span></span> 

<span data-ttu-id="d28b4-122">[数据转换](resources/transforms.md)介绍 ML.NET 中的数据准备功能。</span><span class="sxs-lookup"><span data-stu-id="d28b4-122">[Data transforms](resources/transforms.md) describes data preparation capabilities in ML.NET.</span></span>


## <a name="api-reference"></a><span data-ttu-id="d28b4-123">API 参考</span><span class="sxs-lookup"><span data-stu-id="d28b4-123">API reference</span></span>

<span data-ttu-id="d28b4-124">[ML.NET API 参考](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)介绍了各种可用的 API。</span><span class="sxs-lookup"><span data-stu-id="d28b4-124">[ML.NET API Reference](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) describes the breadth of APIs available.</span></span>
