---
title: 机器学习任务
description: 浏览 ML.NET 中支持的不同机器学习任务。
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 22249ac2d275a4168dbd8b03b90d9698fe90f2d1
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34860640"
---
# <a name="machine-learning-tasks"></a><span data-ttu-id="80260-103">机器学习任务</span><span class="sxs-lookup"><span data-stu-id="80260-103">Machine learning tasks</span></span>

<span data-ttu-id="80260-104">在生成机器学习模型时，首先需要定义你希望通过数据实现的目标。</span><span class="sxs-lookup"><span data-stu-id="80260-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="80260-105">之后，可以根据你的实际情况选取正确的机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="80260-105">After, you can pick the right machine learning task for your situation.</span></span> <span data-ttu-id="80260-106">下面介绍了可以从中选择的不同机器学习任务，以及一些常见用例。</span><span class="sxs-lookup"><span data-stu-id="80260-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span> 

> [!NOTE]
> <span data-ttu-id="80260-107">ML.NET 当前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="80260-107">ML.NET is currently in Preview.</span></span> <span data-ttu-id="80260-108">目前并不支持所有机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="80260-108">Not all machine learning tasks are currently supported.</span></span> <span data-ttu-id="80260-109">若要提交请求以获取某项任务，请在 [dotnet/machinelearning 存储库](https://github.com/dotnet/machinelearning/issues)中打开一个问题。</span><span class="sxs-lookup"><span data-stu-id="80260-109">To submit a request for a certain task, open an issue in the [dotnet/machinelearning repository](https://github.com/dotnet/machinelearning/issues).</span></span>

> [!NOTE]
> <span data-ttu-id="80260-110">目前，ML.NET 不支持使用映像的机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="80260-110">Currently, ML.NET does not support machine learning tasks with images.</span></span> <span data-ttu-id="80260-111">将在未来版本中添加该支持。</span><span class="sxs-lookup"><span data-stu-id="80260-111">Support will be added in future releases.</span></span> 

## <a name="binary-classification"></a><span data-ttu-id="80260-112">二元分类</span><span class="sxs-lookup"><span data-stu-id="80260-112">Binary classification</span></span>

<span data-ttu-id="80260-113">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例所属的两个类（类别）。</span><span class="sxs-lookup"><span data-stu-id="80260-113">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="80260-114">分类算法输入是一组标记示例，其中每个标签为整数 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="80260-114">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="80260-115">二元分类算法的输出是一个分类器，可用于预测未标记的新实例的类。</span><span class="sxs-lookup"><span data-stu-id="80260-115">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="80260-116">二元分类方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="80260-116">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="80260-117">[了解 Twitter 评论的情绪](../tutorials/sentiment-analysis.md)，“正面”或“负面”。</span><span class="sxs-lookup"><span data-stu-id="80260-117">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="80260-118">诊断患者是否患有某种疾病。</span><span class="sxs-lookup"><span data-stu-id="80260-118">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="80260-119">决定是否要将电子邮件标记为“垃圾邮件”。</span><span class="sxs-lookup"><span data-stu-id="80260-119">Making a decision to mark an email as "spam" or not.</span></span>

## <a name="multi-class-classification"></a><span data-ttu-id="80260-120">多类分类</span><span class="sxs-lookup"><span data-stu-id="80260-120">Multi-class classification</span></span>

<span data-ttu-id="80260-121">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例的类（类别）。</span><span class="sxs-lookup"><span data-stu-id="80260-121">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="80260-122">分类算法输入是一组标记示例。</span><span class="sxs-lookup"><span data-stu-id="80260-122">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="80260-123">每个标签是 0 到 k-1 之间的整数，其中 k 表示类的数目。</span><span class="sxs-lookup"><span data-stu-id="80260-123">Each label is an integer between 0 and k-1, where k is the number of classes.</span></span> <span data-ttu-id="80260-124">分类算法的输出是一个分类器，可用于预测未标记的新实例的类。</span><span class="sxs-lookup"><span data-stu-id="80260-124">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="80260-125">多类分类方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="80260-125">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="80260-126">确定狗的品种是“西伯利亚哈士奇”、“金毛寻回犬”、“贵宾犬”等。</span><span class="sxs-lookup"><span data-stu-id="80260-126">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="80260-127">了解电影评论是“正面”、“中立”还是“负面”。</span><span class="sxs-lookup"><span data-stu-id="80260-127">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="80260-128">将酒店评语分类为“位置”、“价格”、“整洁度”等。</span><span class="sxs-lookup"><span data-stu-id="80260-128">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

## <a name="regression"></a><span data-ttu-id="80260-129">回归</span><span class="sxs-lookup"><span data-stu-id="80260-129">Regression</span></span>

<span data-ttu-id="80260-130">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于从一组相关特征中预测标签值。</span><span class="sxs-lookup"><span data-stu-id="80260-130">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="80260-131">标签可以是任何实际值，而不是像在分类任务中那样来自一组有限的值。</span><span class="sxs-lookup"><span data-stu-id="80260-131">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="80260-132">回归算法模拟其相关特征上的标签依赖关系，以确定标签将如何随着特征值的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="80260-132">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="80260-133">回归算法输入是一组带已知值标签的示例。</span><span class="sxs-lookup"><span data-stu-id="80260-133">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="80260-134">回归算法输出是一个函数，可用于预测任何一组新输入特征的标签值。</span><span class="sxs-lookup"><span data-stu-id="80260-134">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="80260-135">回归方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="80260-135">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="80260-136">基于房子特性（如卧室数量、位置或大小）来预测房价。</span><span class="sxs-lookup"><span data-stu-id="80260-136">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="80260-137">基于历史数据和当前市场趋势预测将来的股票价格。</span><span class="sxs-lookup"><span data-stu-id="80260-137">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="80260-138">基于广告预算预测产品销售。</span><span class="sxs-lookup"><span data-stu-id="80260-138">Predicting sales of a product based on advertising budgets.</span></span>

> [!NOTE]
> <span data-ttu-id="80260-139">目前，ML.NET 仍在构建对涉及时序的回归任务的支持。</span><span class="sxs-lookup"><span data-stu-id="80260-139">Currently, ML.NET is still building support for regression tasks that involve time series.</span></span>

## <a name="clustering"></a><span data-ttu-id="80260-140">聚类分析</span><span class="sxs-lookup"><span data-stu-id="80260-140">Clustering</span></span>

<span data-ttu-id="80260-141">[非监管式机器学习](glossary.md#unsupervised-machine-learning)任务，用于将数据实例分组到包含类似特性的群集。</span><span class="sxs-lookup"><span data-stu-id="80260-141">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="80260-142">聚类分析还可用来识别可能无法通过浏览或简单的观察以逻辑方式推导出的数据集中的关系。</span><span class="sxs-lookup"><span data-stu-id="80260-142">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="80260-143">聚类分析算法的输入和输出取决于选择的方法。</span><span class="sxs-lookup"><span data-stu-id="80260-143">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="80260-144">可以采取分发、质心、连接或基于密度的方法。</span><span class="sxs-lookup"><span data-stu-id="80260-144">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="80260-145">ML.NET 当前支持使用 K 平均值聚类分析的基于质心的方法。</span><span class="sxs-lookup"><span data-stu-id="80260-145">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="80260-146">聚类分析方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="80260-146">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="80260-147">基于酒店选择的习惯和特征来了解酒店来宾群。</span><span class="sxs-lookup"><span data-stu-id="80260-147">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="80260-148">确定客户群和人口统计信息来帮助生成目标广告活动。</span><span class="sxs-lookup"><span data-stu-id="80260-148">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="80260-149">基于生产指标对清单进行分类。</span><span class="sxs-lookup"><span data-stu-id="80260-149">Categorizing inventory based on manufacturing metrics.</span></span>

## <a name="anomaly-detection-coming-soon"></a><span data-ttu-id="80260-150">异常检测（即将推出）</span><span class="sxs-lookup"><span data-stu-id="80260-150">Anomaly detection (*coming soon*)</span></span>

## <a name="ranking-coming-soon"></a><span data-ttu-id="80260-151">排名（即将推出）</span><span class="sxs-lookup"><span data-stu-id="80260-151">Ranking (*coming soon*)</span></span>

## <a name="recommendation-coming-soon"></a><span data-ttu-id="80260-152">建议（即将推出）</span><span class="sxs-lookup"><span data-stu-id="80260-152">Recommendation (*coming soon*)</span></span>

