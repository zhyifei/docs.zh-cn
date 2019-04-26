---
title: 什么是 ML.NET？应该如何理解机器学习基础知识？
description: ML.NET 是一个免费的开源跨平台机器学习框架，可用于生成自定义 AI 解决方案并将其集成到 .NET 应用程序。
author: cjgronlund
ms.custom: seodec18
ms.topic: overview
ms.date: 03/01/2019
ms.openlocfilehash: 3f5d44e90ba705195deba54ef658668488cdb0f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200358"
---
# <a name="what-is-mlnet-and-how-do-i-understand-machine-learning-basics"></a><span data-ttu-id="3902c-103">什么是 ML.NET？应该如何理解机器学习基础知识？</span><span class="sxs-lookup"><span data-stu-id="3902c-103">What is ML.NET and how do I understand Machine Learning basics?</span></span>

<span data-ttu-id="3902c-104">ML.NET 是一个免费的开源跨平台机器学习框架，可用于生成自定义机器学习解决方案并将其集成到 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3902c-104">ML.NET is a free, open-source, and cross-platform machine learning framework that enables you to build custom machine learning solutions and integrate them into your .NET applications.</span></span> <span data-ttu-id="3902c-105">借助 ML.NET API，你可以使用自己已有的 .NET 技能将 AI 结合到应用中，而无需离开 .NET。</span><span class="sxs-lookup"><span data-stu-id="3902c-105">With the ML.NET APIs, you can incorporate AI into your apps using the .NET skills you already have and without leaving .NET.</span></span>

> [!NOTE]
> <span data-ttu-id="3902c-106">本文档引用 ML.NET（目前为预览版）。</span><span class="sxs-lookup"><span data-stu-id="3902c-106">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="3902c-107">材料可能会有所变化。</span><span class="sxs-lookup"><span data-stu-id="3902c-107">Material may be subject to change.</span></span> <span data-ttu-id="3902c-108">有关详细信息，请参阅 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="3902c-108">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="what-is-machine-learning"></a><span data-ttu-id="3902c-109">什么是机器学习？</span><span class="sxs-lookup"><span data-stu-id="3902c-109">What is machine learning?</span></span>

<span data-ttu-id="3902c-110">机器学习是一种允许计算机使用现有数据预测未来行为、结果和趋势的数据科学方法。</span><span class="sxs-lookup"><span data-stu-id="3902c-110">Machine learning is a data science technique that allows computers to use existing data to forecast future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="3902c-111">使用机器学习，计算机可以在未显式编程的情况下进行学习。</span><span class="sxs-lookup"><span data-stu-id="3902c-111">Using machine learning, computers learn without being explicitly programmed.</span></span>

<span data-ttu-id="3902c-112">机器学习的预测可以使得应用和设备更智能。</span><span class="sxs-lookup"><span data-stu-id="3902c-112">Forecasts or predictions from machine learning can make apps and devices smarter.</span></span> <span data-ttu-id="3902c-113">在线购物时，机器学习基于历史购买推荐你可能喜欢的其他产品。</span><span class="sxs-lookup"><span data-stu-id="3902c-113">When you shop online, machine learning helps recommend other products you might like based on what you've purchased.</span></span> <span data-ttu-id="3902c-114">刷信用卡时，机器学习将事务与事务数据库进行比较，帮助检测欺诈行为。</span><span class="sxs-lookup"><span data-stu-id="3902c-114">When your credit card is swiped, machine learning compares the transaction to a database of transactions and helps detect fraud.</span></span> <span data-ttu-id="3902c-115">当扫地机器人清理房间时，机器学习帮助其确定工作是否完成。</span><span class="sxs-lookup"><span data-stu-id="3902c-115">When your robot vacuum cleaner vacuums a room, machine learning helps it decide whether the job is done.</span></span>

## <a name="short-videos-on-data-science"></a><span data-ttu-id="3902c-116">数据科学的简短视频</span><span class="sxs-lookup"><span data-stu-id="3902c-116">Short videos on data science</span></span> 

<span data-ttu-id="3902c-117">从一位顶级数据科学家的五个有关“适合初学者的数据科学”的短片了解机器学习和数据科学基础知识的简介。</span><span class="sxs-lookup"><span data-stu-id="3902c-117">Get a quick introduction to the basics of machine learning and data science from *Data Science for Beginners* in five short videos from a top data scientist.</span></span> <span data-ttu-id="3902c-118">这些视频很基础但也很有用，适用于对数据科学感兴趣的人和与数据科学家合作的人。</span><span class="sxs-lookup"><span data-stu-id="3902c-118">These videos are basic but useful, whether you're interested in doing data science or you work with data scientists.</span></span>

* <span data-ttu-id="3902c-119">视频 1：[5 个数据科学问题的解答](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-the-5-questions-data-science-answers)（5 分 14 秒）。</span><span class="sxs-lookup"><span data-stu-id="3902c-119">Video 1: [The 5 questions data science answers](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-the-5-questions-data-science-answers) *(5 min 14 sec)*.</span></span>

* <span data-ttu-id="3902c-120">视频 2：[数据是否可用于数据科学？](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-is-your-data-ready-for-data-science)</span><span class="sxs-lookup"><span data-stu-id="3902c-120">Video 2: [Is your data ready for data science?](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-is-your-data-ready-for-data-science)</span></span> <span data-ttu-id="3902c-121">（4 分 56 秒）</span><span class="sxs-lookup"><span data-stu-id="3902c-121">*(4 min 56 sec)*</span></span>

* <span data-ttu-id="3902c-122">视频 3：[提出数据方面的可解答问题](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-ask-a-question-you-can-answer-with-data)（4 分 17 秒）</span><span class="sxs-lookup"><span data-stu-id="3902c-122">Video 3: [Ask a question you can answer with data](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-ask-a-question-you-can-answer-with-data) *(4 min 17 sec)*</span></span>

* <span data-ttu-id="3902c-123">视频 4：[使用简单的模型预测答案](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-predict-an-answer-with-a-simple-model)（7 分 42 秒）</span><span class="sxs-lookup"><span data-stu-id="3902c-123">Video 4: [Predict an answer with a simple model](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-predict-an-answer-with-a-simple-model) *(7 min 42 sec)*</span></span>

* <span data-ttu-id="3902c-124">视频 5：[复制他人的工作以研究数据科学](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-copy-other-peoples-work-to-do-data-science)（3 分 18 秒）</span><span class="sxs-lookup"><span data-stu-id="3902c-124">Video 5: [Copy other people's work to do data science](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-copy-other-peoples-work-to-do-data-science) *(3 min 18 sec)*</span></span>
