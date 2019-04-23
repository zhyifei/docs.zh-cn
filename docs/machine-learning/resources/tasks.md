---
title: 机器学习任务 - ML.NET
description: 浏览 ML.NET 中支持的不同机器学习任务和关联的任务。
ms.custom: seodec18
ms.date: 04/12/2019
author: natke
ms.openlocfilehash: bfed9cf12f8d539c4327549e5305415ce096e022
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613156"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="c3444-103">ML.NET 中的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="c3444-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="c3444-104">在生成机器学习模型时，首先需要定义你希望通过数据实现的目标。</span><span class="sxs-lookup"><span data-stu-id="c3444-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="c3444-105">这样可以根据你的实际情况选择正确的机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="c3444-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="c3444-106">下面介绍了可以从中选择的不同机器学习任务，以及一些常见用例。</span><span class="sxs-lookup"><span data-stu-id="c3444-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="c3444-107">决定适合场景的任务后，则需要选择最佳算法来训练模型。</span><span class="sxs-lookup"><span data-stu-id="c3444-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="c3444-108">本节列出了每个任务的可用算法。</span><span class="sxs-lookup"><span data-stu-id="c3444-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="c3444-109">二元分类</span><span class="sxs-lookup"><span data-stu-id="c3444-109">Binary classification</span></span>

<span data-ttu-id="c3444-110">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例所属的两个类（类别）。</span><span class="sxs-lookup"><span data-stu-id="c3444-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="c3444-111">分类算法输入是一组标记示例，其中每个标签为整数 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="c3444-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="c3444-112">二元分类算法的输出是一个分类器，可用于预测未标记的新实例的类。</span><span class="sxs-lookup"><span data-stu-id="c3444-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="c3444-113">二元分类方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="c3444-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="c3444-114">[了解 Twitter 评论的情绪](../tutorials/sentiment-analysis.md)，“正面”或“负面”。</span><span class="sxs-lookup"><span data-stu-id="c3444-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="c3444-115">诊断患者是否患有某种疾病。</span><span class="sxs-lookup"><span data-stu-id="c3444-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="c3444-116">决定是否要将电子邮件标记为“垃圾邮件”。</span><span class="sxs-lookup"><span data-stu-id="c3444-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="c3444-117">确定照片是否包含狗或水果。</span><span class="sxs-lookup"><span data-stu-id="c3444-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="c3444-118">有关详细信息，请参阅 Wikipedia 上的[二元分类](https://en.wikipedia.org/wiki/Binary_classification)一文。</span><span class="sxs-lookup"><span data-stu-id="c3444-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-training-algorithms"></a><span data-ttu-id="c3444-119">二元分类训练算法</span><span class="sxs-lookup"><span data-stu-id="c3444-119">Binary Classification Training Algorithms</span></span>

<span data-ttu-id="c3444-120">可以使用以下算法训练二元分类模型：</span><span class="sxs-lookup"><span data-stu-id="c3444-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>

## <a name="multiclass-classification"></a><span data-ttu-id="c3444-121">多类分类</span><span class="sxs-lookup"><span data-stu-id="c3444-121">Multiclass classification</span></span>

<span data-ttu-id="c3444-122">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例的类（类别）。</span><span class="sxs-lookup"><span data-stu-id="c3444-122">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="c3444-123">分类算法输入是一组标记示例。</span><span class="sxs-lookup"><span data-stu-id="c3444-123">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="c3444-124">每个标签通常以文本形式开始。</span><span class="sxs-lookup"><span data-stu-id="c3444-124">Each label normally starts as text.</span></span> <span data-ttu-id="c3444-125">然后通过 TermTransform 运行，它可将其转换为 Key（数字）类型。</span><span class="sxs-lookup"><span data-stu-id="c3444-125">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="c3444-126">分类算法的输出是一个分类器，可用于预测未标记的新实例的类。</span><span class="sxs-lookup"><span data-stu-id="c3444-126">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="c3444-127">多类分类方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="c3444-127">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="c3444-128">确定狗的品种是“西伯利亚哈士奇”、“金毛寻回犬”、“贵宾犬”等。</span><span class="sxs-lookup"><span data-stu-id="c3444-128">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="c3444-129">了解电影评论是“正面”、“中立”还是“负面”。</span><span class="sxs-lookup"><span data-stu-id="c3444-129">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="c3444-130">将酒店评语分类为“位置”、“价格”、“整洁度”等。</span><span class="sxs-lookup"><span data-stu-id="c3444-130">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="c3444-131">有关详细信息，请参阅 Wikipedia 上的[多类分类](https://en.wikipedia.org/wiki/Multiclass_classification)一文。</span><span class="sxs-lookup"><span data-stu-id="c3444-131">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="c3444-132">一个与所有升级任何[二元分类学习器](#binary-classification)，以便对多类数据集进行操作。</span><span class="sxs-lookup"><span data-stu-id="c3444-132">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="c3444-133">有关详细信息，请参阅 [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest)。</span><span class="sxs-lookup"><span data-stu-id="c3444-133">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-training-algorithms"></a><span data-ttu-id="c3444-134">多类分类训练算法</span><span class="sxs-lookup"><span data-stu-id="c3444-134">Multiclass Classification training algorithms</span></span>

<span data-ttu-id="c3444-135">可以使用以下训练算法训练多类分类模型：</span><span class="sxs-lookup"><span data-stu-id="c3444-135">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

## <a name="regression"></a><span data-ttu-id="c3444-136">回归测试</span><span class="sxs-lookup"><span data-stu-id="c3444-136">Regression</span></span>

<span data-ttu-id="c3444-137">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于从一组相关特征中预测标签值。</span><span class="sxs-lookup"><span data-stu-id="c3444-137">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="c3444-138">标签可以是任何实际值，而不是像在分类任务中那样来自一组有限的值。</span><span class="sxs-lookup"><span data-stu-id="c3444-138">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="c3444-139">回归算法模拟其相关特征上的标签依赖关系，以确定标签将如何随着特征值的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="c3444-139">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="c3444-140">回归算法输入是一组带已知值标签的示例。</span><span class="sxs-lookup"><span data-stu-id="c3444-140">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="c3444-141">回归算法输出是一个函数，可用于预测任何一组新输入特征的标签值。</span><span class="sxs-lookup"><span data-stu-id="c3444-141">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="c3444-142">回归方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="c3444-142">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="c3444-143">基于房子特性（如卧室数量、位置或大小）来预测房价。</span><span class="sxs-lookup"><span data-stu-id="c3444-143">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="c3444-144">基于历史数据和当前市场趋势预测将来的股票价格。</span><span class="sxs-lookup"><span data-stu-id="c3444-144">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="c3444-145">基于广告预算预测产品销售。</span><span class="sxs-lookup"><span data-stu-id="c3444-145">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-training-algorithms"></a><span data-ttu-id="c3444-146">回归训练算法</span><span class="sxs-lookup"><span data-stu-id="c3444-146">Regression training algorithms</span></span>

<span data-ttu-id="c3444-147">可以使用以下算法训练回归模型：</span><span class="sxs-lookup"><span data-stu-id="c3444-147">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>

## <a name="clustering"></a><span data-ttu-id="c3444-148">聚类分析</span><span class="sxs-lookup"><span data-stu-id="c3444-148">Clustering</span></span>

<span data-ttu-id="c3444-149">[非监管式机器学习](glossary.md#unsupervised-machine-learning)任务，用于将数据实例分组到包含类似特性的群集。</span><span class="sxs-lookup"><span data-stu-id="c3444-149">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="c3444-150">聚类分析还可用来识别可能无法通过浏览或简单的观察以逻辑方式推导出的数据集中的关系。</span><span class="sxs-lookup"><span data-stu-id="c3444-150">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="c3444-151">聚类分析算法的输入和输出取决于选择的方法。</span><span class="sxs-lookup"><span data-stu-id="c3444-151">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="c3444-152">可以采取分发、质心、连接或基于密度的方法。</span><span class="sxs-lookup"><span data-stu-id="c3444-152">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="c3444-153">ML.NET 当前支持使用 K 平均值聚类分析的基于质心的方法。</span><span class="sxs-lookup"><span data-stu-id="c3444-153">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="c3444-154">聚类分析方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="c3444-154">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="c3444-155">基于酒店选择的习惯和特征来了解酒店来宾群。</span><span class="sxs-lookup"><span data-stu-id="c3444-155">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="c3444-156">确定客户群和人口统计信息来帮助生成目标广告活动。</span><span class="sxs-lookup"><span data-stu-id="c3444-156">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="c3444-157">基于生产指标对清单进行分类。</span><span class="sxs-lookup"><span data-stu-id="c3444-157">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-training-algorithms"></a><span data-ttu-id="c3444-158">聚类分析训练算法</span><span class="sxs-lookup"><span data-stu-id="c3444-158">Clustering training algorithms</span></span>

<span data-ttu-id="c3444-159">可以使用以下算法训练聚类分析模型：</span><span class="sxs-lookup"><span data-stu-id="c3444-159">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

## <a name="anomaly-detection"></a><span data-ttu-id="c3444-160">异常情况检测</span><span class="sxs-lookup"><span data-stu-id="c3444-160">Anomaly detection</span></span>

<span data-ttu-id="c3444-161">此任务使用主体组件分析 (PCA) 创建异常情况检测模型。</span><span class="sxs-lookup"><span data-stu-id="c3444-161">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="c3444-162">基于 PCA 的异常情况检测有助于在以下场景中构建模型：可以很轻松地从一个类中获得定型数据（例如有效事务），但难以获得目标异常的足够示例。</span><span class="sxs-lookup"><span data-stu-id="c3444-162">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="c3444-163">PCA 是机器学习中已建立的一种技术，由于它揭示了数据的内部结构，并解释了数据中的差异，因此经常被用于探索性数据分析。</span><span class="sxs-lookup"><span data-stu-id="c3444-163">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="c3444-164">PCA 的工作方式是通过分析包含多个变量的数据。</span><span class="sxs-lookup"><span data-stu-id="c3444-164">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="c3444-165">它查找变量之间的关联性，并确定最能捕捉结果差异的值的组合。</span><span class="sxs-lookup"><span data-stu-id="c3444-165">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="c3444-166">这些组合的特性值用于创建一个更紧凑的特性空间，称为主体组件。</span><span class="sxs-lookup"><span data-stu-id="c3444-166">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="c3444-167">异常情况检测包含机器学习中的许多重要任务：</span><span class="sxs-lookup"><span data-stu-id="c3444-167">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="c3444-168">识别潜在的欺诈交易。</span><span class="sxs-lookup"><span data-stu-id="c3444-168">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="c3444-169">指示发生了网络入侵的学习模式。</span><span class="sxs-lookup"><span data-stu-id="c3444-169">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="c3444-170">发现异常的患者群集。</span><span class="sxs-lookup"><span data-stu-id="c3444-170">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="c3444-171">检查输入系统的值。</span><span class="sxs-lookup"><span data-stu-id="c3444-171">Checking values entered into a system.</span></span>

<span data-ttu-id="c3444-172">根据定义，异常情况属于罕见事件，因此很难收集具有代表性的数据样本用于建模。</span><span class="sxs-lookup"><span data-stu-id="c3444-172">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="c3444-173">此类别中包含的算法是专门设计用来解决使用不平衡数据集建立和定型模型的核心挑战。</span><span class="sxs-lookup"><span data-stu-id="c3444-173">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-training-algorithms"></a><span data-ttu-id="c3444-174">异常情况检测训练算法</span><span class="sxs-lookup"><span data-stu-id="c3444-174">Anomaly detection training algorithms</span></span>

<span data-ttu-id="c3444-175">可以使用以下算法训练异常情况检测模型：</span><span class="sxs-lookup"><span data-stu-id="c3444-175">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

## <a name="ranking"></a><span data-ttu-id="c3444-176">排名</span><span class="sxs-lookup"><span data-stu-id="c3444-176">Ranking</span></span>

<span data-ttu-id="c3444-177">排名任务从一组标记的示例构建排名程序。</span><span class="sxs-lookup"><span data-stu-id="c3444-177">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="c3444-178">该示例集由实例组组成，这些实例组可以使用给定的标准进行评分。</span><span class="sxs-lookup"><span data-stu-id="c3444-178">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="c3444-179">每个实例的排名标签是 { 0, 1, 2, 3, 4 }。</span><span class="sxs-lookup"><span data-stu-id="c3444-179">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="c3444-180">排名程序定型为用每个实例的未知分数对新实例组进行排名。</span><span class="sxs-lookup"><span data-stu-id="c3444-180">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="c3444-181">ML.NET 排名学习器基于[机器已学习的排名](https://en.wikipedia.org/wiki/Learning_to_rank)。</span><span class="sxs-lookup"><span data-stu-id="c3444-181">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="c3444-182">排名训练算法</span><span class="sxs-lookup"><span data-stu-id="c3444-182">Ranking training algorithms</span></span>

<span data-ttu-id="c3444-183">可以使用以下算法训练排名模型：</span><span class="sxs-lookup"><span data-stu-id="c3444-183">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>

## <a name="recommendation"></a><span data-ttu-id="c3444-184">建议</span><span class="sxs-lookup"><span data-stu-id="c3444-184">Recommendation</span></span>

<span data-ttu-id="c3444-185">推荐任务支持生成推荐产品或服务的列表。</span><span class="sxs-lookup"><span data-stu-id="c3444-185">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="c3444-186">ML.NET 使用[矩阵因子分解 (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29)，这是一种[协作筛选](https://en.wikipedia.org/wiki/Collaborative_filtering)算法，当目录中有历史产品评级数据时，推荐使用该算法。</span><span class="sxs-lookup"><span data-stu-id="c3444-186">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="c3444-187">例如，你为用户提供历史电影评级数据，并希望向他们推荐接下来可能观看的其他电影。</span><span class="sxs-lookup"><span data-stu-id="c3444-187">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="c3444-188">建议训练算法</span><span class="sxs-lookup"><span data-stu-id="c3444-188">Recommendation training algorithms</span></span>

<span data-ttu-id="c3444-189">可以使用以下算法训练建议模型：</span><span class="sxs-lookup"><span data-stu-id="c3444-189">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
