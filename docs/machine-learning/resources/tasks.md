---
title: 机器学习任务 - ML.NET
description: 浏览 ML.NET 中支持的不同机器学习任务和关联的学习器。
ms.custom: seodec18
ms.date: 11/29/2018
author: jralexander
ms.openlocfilehash: 4b333fb8c954c94ed84033d9858a496f591f2169
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126583"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="38840-103">ML.NET 中的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="38840-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="38840-104">在生成机器学习模型时，首先需要定义你希望通过数据实现的目标。</span><span class="sxs-lookup"><span data-stu-id="38840-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="38840-105">之后，可以根据你的实际情况选取正确的机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="38840-105">Afterwards, you can pick the right machine learning task for your situation.</span></span> <span data-ttu-id="38840-106">下面介绍了可以从中选择的不同机器学习任务，以及一些常见用例。</span><span class="sxs-lookup"><span data-stu-id="38840-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

> [!NOTE]
> <span data-ttu-id="38840-107">ML.NET 当前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="38840-107">ML.NET is currently in Preview.</span></span> <span data-ttu-id="38840-108">目前并不支持所有机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="38840-108">Not all machine learning tasks are currently supported.</span></span> <span data-ttu-id="38840-109">若要提交请求以获取某项任务，请在 [dotnet/machinelearning 存储库](https://github.com/dotnet/machinelearning/issues)中打开一个问题。</span><span class="sxs-lookup"><span data-stu-id="38840-109">To submit a request for a certain task, open an issue in the [dotnet/machinelearning repository](https://github.com/dotnet/machinelearning/issues).</span></span>

## <a name="binary-classification"></a><span data-ttu-id="38840-110">二元分类</span><span class="sxs-lookup"><span data-stu-id="38840-110">Binary classification</span></span>

<span data-ttu-id="38840-111">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例所属的两个类（类别）。</span><span class="sxs-lookup"><span data-stu-id="38840-111">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="38840-112">分类算法输入是一组标记示例，其中每个标签为整数 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="38840-112">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="38840-113">二元分类算法的输出是一个分类器，可用于预测未标记的新实例的类。</span><span class="sxs-lookup"><span data-stu-id="38840-113">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="38840-114">二元分类方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="38840-114">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="38840-115">[了解 Twitter 评论的情绪](../tutorials/sentiment-analysis.md)，“正面”或“负面”。</span><span class="sxs-lookup"><span data-stu-id="38840-115">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="38840-116">诊断患者是否患有某种疾病。</span><span class="sxs-lookup"><span data-stu-id="38840-116">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="38840-117">决定是否要将电子邮件标记为“垃圾邮件”。</span><span class="sxs-lookup"><span data-stu-id="38840-117">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="38840-118">确定照片是否包含狗或水果。</span><span class="sxs-lookup"><span data-stu-id="38840-118">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="38840-119">有关详细信息，请参阅 Wikipedia 上的[二元分类](https://en.wikipedia.org/wiki/Binary_classification)一文。</span><span class="sxs-lookup"><span data-stu-id="38840-119">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

<span data-ttu-id="38840-120">推荐的二元分类学习器：</span><span class="sxs-lookup"><span data-stu-id="38840-120">Recommended learners for binary classification:</span></span>

* <span data-ttu-id="38840-121">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-121">AveragedPerceptronTrainer</span></span>
* <span data-ttu-id="38840-122">StochasticGradientDescentClassificationTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-122">StochasticGradientDescentClassificationTrainer</span></span>
* <span data-ttu-id="38840-123">LightGbmBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-123">LightGbmBinaryTrainer</span></span>
* <span data-ttu-id="38840-124">FastTreeBinaryClassificationTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-124">FastTreeBinaryClassificationTrainer</span></span>
* <span data-ttu-id="38840-125">SymSgdClassificationTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-125">SymSgdClassificationTrainer</span></span>

### <a name="binary-classification-learners"></a><span data-ttu-id="38840-126">二元分类学习器</span><span class="sxs-lookup"><span data-stu-id="38840-126">Binary Classification Learners</span></span>

<span data-ttu-id="38840-127">以下学习器可用于二元分类任务：</span><span class="sxs-lookup"><span data-stu-id="38840-127">The following learners are available for binary classification tasks:</span></span>

* [<span data-ttu-id="38840-128">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-128">AveragedPerceptronTrainer</span></span>](xref:Microsoft.ML.Trainers.Online.AveragedPerceptronTrainer)
* [<span data-ttu-id="38840-129">BinaryClassificationGamTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-129">BinaryClassificationGamTrainer</span></span>](xref:Microsoft.ML.Trainers.FastTree.BinaryClassificationGamTrainer)
* [<span data-ttu-id="38840-130">FastForestClassification</span><span class="sxs-lookup"><span data-stu-id="38840-130">FastForestClassification</span></span>](xref:Microsoft.ML.Trainers.FastTree.FastForestClassification)
* [<span data-ttu-id="38840-131">FastTreeBinaryClassificationTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-131">FastTreeBinaryClassificationTrainer</span></span>](xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer)
* [<span data-ttu-id="38840-132">FieldAwareFactorizationMachineTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-132">FieldAwareFactorizationMachineTrainer</span></span>](xref:Microsoft.ML.Runtime.FactorizationMachine.FieldAwareFactorizationMachineTrainer)
* [<span data-ttu-id="38840-133">LightGbmBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-133">LightGbmBinaryTrainer</span></span>](xref:Microsoft.ML.Runtime.LightGBM.LightGbmBinaryTrainer)
* [<span data-ttu-id="38840-134">LinearSvm</span><span class="sxs-lookup"><span data-stu-id="38840-134">LinearSvm</span></span>](xref:Microsoft.ML.Trainers.Online.LinearSvm)
* [<span data-ttu-id="38840-135">PriorTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-135">PriorTrainer</span></span>](xref:Microsoft.ML.Trainers.PriorTrainer)
* [<span data-ttu-id="38840-136">RandomTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-136">RandomTrainer</span></span>](xref:Microsoft.ML.Trainers.RandomTrainer)
* [<span data-ttu-id="38840-137">StochasticGradientDescentClassificationTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-137">StochasticGradientDescentClassificationTrainer</span></span>](xref:Microsoft.ML.Trainers.StochasticGradientDescentClassificationTrainer)
* [<span data-ttu-id="38840-138">SymSgdClassificationTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-138">SymSgdClassificationTrainer</span></span>](xref:Microsoft.ML.Trainers.SymSgd.SymSgdClassificationTrainer)

## <a name="multiclass-classification"></a><span data-ttu-id="38840-139">多类分类</span><span class="sxs-lookup"><span data-stu-id="38840-139">Multiclass classification</span></span>

<span data-ttu-id="38840-140">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例的类（类别）。</span><span class="sxs-lookup"><span data-stu-id="38840-140">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="38840-141">分类算法输入是一组标记示例。</span><span class="sxs-lookup"><span data-stu-id="38840-141">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="38840-142">每个标签通常以文本形式开始。</span><span class="sxs-lookup"><span data-stu-id="38840-142">Each label normally starts as text.</span></span> <span data-ttu-id="38840-143">然后通过 TermTransform 运行，它可将其转换为 Key（数字）类型。</span><span class="sxs-lookup"><span data-stu-id="38840-143">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="38840-144">分类算法的输出是一个分类器，可用于预测未标记的新实例的类。</span><span class="sxs-lookup"><span data-stu-id="38840-144">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="38840-145">多类分类方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="38840-145">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="38840-146">确定狗的品种是“西伯利亚哈士奇”、“金毛寻回犬”、“贵宾犬”等。</span><span class="sxs-lookup"><span data-stu-id="38840-146">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="38840-147">了解电影评论是“正面”、“中立”还是“负面”。</span><span class="sxs-lookup"><span data-stu-id="38840-147">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="38840-148">将酒店评语分类为“位置”、“价格”、“整洁度”等。</span><span class="sxs-lookup"><span data-stu-id="38840-148">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="38840-149">有关详细信息，请参阅 Wikipedia 上的[多类分类](https://en.wikipedia.org/wiki/Multiclass_classification)一文。</span><span class="sxs-lookup"><span data-stu-id="38840-149">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

<span data-ttu-id="38840-150">推荐的多类学习器：</span><span class="sxs-lookup"><span data-stu-id="38840-150">Recommended learners for Multi-class:</span></span>

* <span data-ttu-id="38840-151">OVA-AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-151">OVA-AveragedPerceptronTrainer</span></span>
* <span data-ttu-id="38840-152">SdcaMultiClassTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-152">SdcaMultiClassTrainer</span></span>
* <span data-ttu-id="38840-153">LightGbmMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-153">LightGbmMulticlassTrainer</span></span>
* <span data-ttu-id="38840-154">OVA-FastTreeBinaryClassificationTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-154">OVA-FastTreeBinaryClassificationTrainer</span></span>

>[!NOTE]
><span data-ttu-id="38840-155">OVA 和 PKPD 升级任何[二元分类学习器](#binary-classification)，以便对多类数据集进行操作。</span><span class="sxs-lookup"><span data-stu-id="38840-155">OVA and PKPD upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="38840-156">有关详细信息，请参阅 [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest)。</span><span class="sxs-lookup"><span data-stu-id="38840-156">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-learners"></a><span data-ttu-id="38840-157">多类分类学习器</span><span class="sxs-lookup"><span data-stu-id="38840-157">Multiclass Classification Learners</span></span>

<span data-ttu-id="38840-158">以下学习器可用于多类分类任务：</span><span class="sxs-lookup"><span data-stu-id="38840-158">The following learners are available for multiclass classification tasks:</span></span>

* [<span data-ttu-id="38840-159">LightGbmMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-159">LightGbmMulticlassTrainer</span></span>](xref:Microsoft.ML.Runtime.LightGBM.LightGbmMulticlassTrainer)
* [<span data-ttu-id="38840-160">MetaMulticlassTrainer<TTransformer,TModel></span><span class="sxs-lookup"><span data-stu-id="38840-160">MetaMulticlassTrainer<TTransformer,TModel></span></span>](xref:Microsoft.ML.Runtime.Learners.MetaMulticlassTrainer%602)
* [<span data-ttu-id="38840-161">MultiClassClassificationTrainers</span><span class="sxs-lookup"><span data-stu-id="38840-161">MultiClassClassificationTrainers</span></span>](xref:Microsoft.ML.Trainers.MultiClassClassificationTrainers)
* [<span data-ttu-id="38840-162">MultiClassNaiveBayesTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-162">MultiClassNaiveBayesTrainer</span></span>](xref:Microsoft.ML.Trainers.MultiClassNaiveBayesTrainer)
* [<span data-ttu-id="38840-163">Ova</span><span class="sxs-lookup"><span data-stu-id="38840-163">Ova</span></span>](xref:Microsoft.ML.Trainers.Ova)
* [<span data-ttu-id="38840-164">Pkpd</span><span class="sxs-lookup"><span data-stu-id="38840-164">Pkpd</span></span>](xref:Microsoft.ML.Trainers.Pkpd)
* [<span data-ttu-id="38840-165">SdcaMultiClassTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-165">SdcaMultiClassTrainer</span></span>](xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer)

## <a name="regression"></a><span data-ttu-id="38840-166">回归</span><span class="sxs-lookup"><span data-stu-id="38840-166">Regression</span></span>

<span data-ttu-id="38840-167">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于从一组相关特征中预测标签值。</span><span class="sxs-lookup"><span data-stu-id="38840-167">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="38840-168">标签可以是任何实际值，而不是像在分类任务中那样来自一组有限的值。</span><span class="sxs-lookup"><span data-stu-id="38840-168">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="38840-169">回归算法模拟其相关特征上的标签依赖关系，以确定标签将如何随着特征值的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="38840-169">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="38840-170">回归算法输入是一组带已知值标签的示例。</span><span class="sxs-lookup"><span data-stu-id="38840-170">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="38840-171">回归算法输出是一个函数，可用于预测任何一组新输入特征的标签值。</span><span class="sxs-lookup"><span data-stu-id="38840-171">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="38840-172">回归方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="38840-172">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="38840-173">基于房子特性（如卧室数量、位置或大小）来预测房价。</span><span class="sxs-lookup"><span data-stu-id="38840-173">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="38840-174">基于历史数据和当前市场趋势预测将来的股票价格。</span><span class="sxs-lookup"><span data-stu-id="38840-174">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="38840-175">基于广告预算预测产品销售。</span><span class="sxs-lookup"><span data-stu-id="38840-175">Predicting sales of a product based on advertising budgets.</span></span>

<span data-ttu-id="38840-176">推荐的回归学习器：</span><span class="sxs-lookup"><span data-stu-id="38840-176">Recommended learners for regression:</span></span>

* <span data-ttu-id="38840-177">FastTreeTweedieTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-177">FastTreeTweedieTrainer</span></span> 
* <span data-ttu-id="38840-178">LightGbmRegressorTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-178">LightGbmRegressorTrainer</span></span> 
* <span data-ttu-id="38840-179">SdcaRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-179">SdcaRegressionTrainer</span></span> 
* <span data-ttu-id="38840-180">FastTreeRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-180">FastTreeRegressionTrainer</span></span>

### <a name="regression-learners"></a><span data-ttu-id="38840-181">回归学习器</span><span class="sxs-lookup"><span data-stu-id="38840-181">Regression Learners</span></span>

<span data-ttu-id="38840-182">以下学习器可用于回归任务：</span><span class="sxs-lookup"><span data-stu-id="38840-182">The following learners are available for regression tasks:</span></span>

* [<span data-ttu-id="38840-183">FastTreeRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-183">FastTreeRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer)
* [<span data-ttu-id="38840-184">FastTreeRegressionFastTreeTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-184">FastTreeRegressionFastTreeTrainer</span></span>](xref:Microsoft.ML.Runtime.FastTreeRegressionFastTreeTrainer)
* [<span data-ttu-id="38840-185">FastTreeTweedieRegressionFastTreeTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-185">FastTreeTweedieRegressionFastTreeTrainer</span></span>](xref:Microsoft.ML.Runtime.FastTreeTweedieRegressionFastTreeTrainer)
* [<span data-ttu-id="38840-186">FastTreeTweedieTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-186">FastTreeTweedieTrainer</span></span>](xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer)
* [<span data-ttu-id="38840-187">LightGbmRegressorTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-187">LightGbmRegressorTrainer</span></span>](xref:Microsoft.ML.Runtime.LightGBM.LightGbmRegressorTrainer)
* [<span data-ttu-id="38840-188">LogisticRegression</span><span class="sxs-lookup"><span data-stu-id="38840-188">LogisticRegression</span></span>](xref:Microsoft.ML.Runtime.Learners.LogisticRegression)
* [<span data-ttu-id="38840-189">OlsLinearRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-189">OlsLinearRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.HalLearners.OlsLinearRegressionTrainer)
* [<span data-ttu-id="38840-190">OnlineGradientDescentTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-190">OnlineGradientDescentTrainer</span></span>](xref:Microsoft.ML.Trainers.Online.OnlineGradientDescentTrainer)
* [<span data-ttu-id="38840-191">PoissonRegression</span><span class="sxs-lookup"><span data-stu-id="38840-191">PoissonRegression</span></span>](xref:Microsoft.ML.Trainers.PoissonRegression)
* [<span data-ttu-id="38840-192">RegressionGamTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-192">RegressionGamTrainer</span></span>](xref:Microsoft.ML.Trainers.FastTree.RegressionGamTrainer)
* [<span data-ttu-id="38840-193">SdcaRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-193">SdcaRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer)
* [<span data-ttu-id="38840-194">FastTree.SingleTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-194">FastTree.SingleTrainer</span></span>](xref:Microsoft.ML.Trainers.FastTree.SingleTrainer)
* [<span data-ttu-id="38840-195">LightGBM.SingleTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-195">LightGBM.SingleTrainer</span></span>](xref:Microsoft.ML.Runtime.LightGBM.SingleTrainer)

## <a name="clustering"></a><span data-ttu-id="38840-196">聚类分析</span><span class="sxs-lookup"><span data-stu-id="38840-196">Clustering</span></span>

<span data-ttu-id="38840-197">[非监管式机器学习](glossary.md#unsupervised-machine-learning)任务，用于将数据实例分组到包含类似特性的群集。</span><span class="sxs-lookup"><span data-stu-id="38840-197">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="38840-198">聚类分析还可用来识别可能无法通过浏览或简单的观察以逻辑方式推导出的数据集中的关系。</span><span class="sxs-lookup"><span data-stu-id="38840-198">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="38840-199">聚类分析算法的输入和输出取决于选择的方法。</span><span class="sxs-lookup"><span data-stu-id="38840-199">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="38840-200">可以采取分发、质心、连接或基于密度的方法。</span><span class="sxs-lookup"><span data-stu-id="38840-200">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="38840-201">ML.NET 当前支持使用 K 平均值聚类分析的基于质心的方法。</span><span class="sxs-lookup"><span data-stu-id="38840-201">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="38840-202">聚类分析方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="38840-202">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="38840-203">基于酒店选择的习惯和特征来了解酒店来宾群。</span><span class="sxs-lookup"><span data-stu-id="38840-203">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="38840-204">确定客户群和人口统计信息来帮助生成目标广告活动。</span><span class="sxs-lookup"><span data-stu-id="38840-204">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="38840-205">基于生产指标对清单进行分类。</span><span class="sxs-lookup"><span data-stu-id="38840-205">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-learners"></a><span data-ttu-id="38840-206">聚类分析学习器</span><span class="sxs-lookup"><span data-stu-id="38840-206">Clustering Learners</span></span>

<span data-ttu-id="38840-207">以下学习器可用于聚类分析任务：</span><span class="sxs-lookup"><span data-stu-id="38840-207">The following learners are available for clustering tasks:</span></span>

* [<span data-ttu-id="38840-208">KMeansPlusPlusTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-208">KMeansPlusPlusTrainer</span></span>](xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer)

## <a name="anomaly-detection"></a><span data-ttu-id="38840-209">异常情况检测</span><span class="sxs-lookup"><span data-stu-id="38840-209">Anomaly detection</span></span>

<span data-ttu-id="38840-210">此任务使用主体组件分析 (PCA) 创建异常情况检测模型。</span><span class="sxs-lookup"><span data-stu-id="38840-210">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="38840-211">基于 PCA 的异常情况检测有助于在以下场景中构建模型：可以很轻松地从一个类中获得定型数据（例如有效事务），但难以获得目标异常的足够示例。</span><span class="sxs-lookup"><span data-stu-id="38840-211">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="38840-212">PCA 是机器学习中已建立的一种技术，由于它揭示了数据的内部结构，并解释了数据中的差异，因此经常被用于探索性数据分析。</span><span class="sxs-lookup"><span data-stu-id="38840-212">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="38840-213">PCA 的工作方式是通过分析包含多个变量的数据。</span><span class="sxs-lookup"><span data-stu-id="38840-213">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="38840-214">它查找变量之间的关联性，并确定最能捕捉结果差异的值的组合。</span><span class="sxs-lookup"><span data-stu-id="38840-214">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="38840-215">这些组合的特性值用于创建一个更紧凑的特性空间，称为主体组件。</span><span class="sxs-lookup"><span data-stu-id="38840-215">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="38840-216">异常情况检测包含机器学习中的许多重要任务：</span><span class="sxs-lookup"><span data-stu-id="38840-216">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="38840-217">识别潜在的欺诈交易。</span><span class="sxs-lookup"><span data-stu-id="38840-217">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="38840-218">指示发生了网络入侵的学习模式。</span><span class="sxs-lookup"><span data-stu-id="38840-218">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="38840-219">发现异常的患者群集。</span><span class="sxs-lookup"><span data-stu-id="38840-219">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="38840-220">检查输入系统的值。</span><span class="sxs-lookup"><span data-stu-id="38840-220">Checking values entered into a system.</span></span>

<span data-ttu-id="38840-221">根据定义，异常情况属于罕见事件，因此很难收集具有代表性的数据样本用于建模。</span><span class="sxs-lookup"><span data-stu-id="38840-221">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="38840-222">此类别中包含的算法是专门设计用来解决使用不平衡数据集建立和定型模型的核心挑战。</span><span class="sxs-lookup"><span data-stu-id="38840-222">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-learners"></a><span data-ttu-id="38840-223">异常情况检测学习器</span><span class="sxs-lookup"><span data-stu-id="38840-223">Anomaly detection learners</span></span>

<span data-ttu-id="38840-224">以下学习器可用于异常情况检测任务：</span><span class="sxs-lookup"><span data-stu-id="38840-224">The following learners are available for anomaly detection tasks:</span></span>

* [<span data-ttu-id="38840-225">RandomizedPcaTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-225">RandomizedPcaTrainer</span></span>](xref:Microsoft.ML.Trainers.PCA.RandomizedPcaTrainer)

## <a name="ranking"></a><span data-ttu-id="38840-226">排名</span><span class="sxs-lookup"><span data-stu-id="38840-226">Ranking</span></span>

<span data-ttu-id="38840-227">排名任务从一组标记的示例构建排名程序。</span><span class="sxs-lookup"><span data-stu-id="38840-227">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="38840-228">该示例集由实例组组成，这些实例组可以使用给定的标准进行评分。</span><span class="sxs-lookup"><span data-stu-id="38840-228">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="38840-229">每个实例的排名标签是 { 0, 1, 2, 3, 4 }。</span><span class="sxs-lookup"><span data-stu-id="38840-229">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="38840-230">排名程序定型为用每个实例的未知分数对新实例组进行排名。</span><span class="sxs-lookup"><span data-stu-id="38840-230">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="38840-231">ML.NET 排名学习器基于[机器已学习的排名](https://en.wikipedia.org/wiki/Learning_to_rank)。</span><span class="sxs-lookup"><span data-stu-id="38840-231">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-learners"></a><span data-ttu-id="38840-232">排名学习器</span><span class="sxs-lookup"><span data-stu-id="38840-232">Ranking learners</span></span>

<span data-ttu-id="38840-233">以下学习器可用于排名任务：</span><span class="sxs-lookup"><span data-stu-id="38840-233">The following learners are available for ranking tasks:</span></span>

* [<span data-ttu-id="38840-234">FastTreeRankingFastTreeTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-234">FastTreeRankingFastTreeTrainer</span></span>](xref:Microsoft.ML.Runtime.FastTreeRankingFastTreeTrainer)
* [<span data-ttu-id="38840-235">FastTreeRankingTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-235">FastTreeRankingTrainer</span></span>](xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer)
* [<span data-ttu-id="38840-236">LightGbmRankingTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-236">LightGbmRankingTrainer</span></span>](xref:Microsoft.ML.Runtime.LightGBM.LightGbmRankingTrainer)

## <a name="recommendation"></a><span data-ttu-id="38840-237">建议</span><span class="sxs-lookup"><span data-stu-id="38840-237">Recommendation</span></span>

<span data-ttu-id="38840-238">推荐任务支持生成推荐产品或服务的列表。</span><span class="sxs-lookup"><span data-stu-id="38840-238">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="38840-239">ML.NET 使用[矩阵因子分解 (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29)，这是一种[协作筛选](https://en.wikipedia.org/wiki/Collaborative_filtering)算法，当目录中有历史产品评级数据时，推荐使用该算法。</span><span class="sxs-lookup"><span data-stu-id="38840-239">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="38840-240">例如，你为用户提供历史电影评级数据，并希望向他们推荐接下来可能观看的其他电影。</span><span class="sxs-lookup"><span data-stu-id="38840-240">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-learners"></a><span data-ttu-id="38840-241">推荐学习器</span><span class="sxs-lookup"><span data-stu-id="38840-241">Recommendation learners</span></span>

<span data-ttu-id="38840-242">以下学习器可用于推荐任务：</span><span class="sxs-lookup"><span data-stu-id="38840-242">The following learners are available for recommendation tasks:</span></span>

* [<span data-ttu-id="38840-243">MatrixFactorizationTrainer</span><span class="sxs-lookup"><span data-stu-id="38840-243">MatrixFactorizationTrainer</span></span>](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer)
* [<span data-ttu-id="38840-244">MatrixFactorizationPredictionTransformer</span><span class="sxs-lookup"><span data-stu-id="38840-244">MatrixFactorizationPredictionTransformer</span></span>](xref:Microsoft.ML.Trainers.Recommender.MatrixFactorizationPredictionTransformer)
