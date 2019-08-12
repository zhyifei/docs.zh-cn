---
title: 机器学习任务
description: 浏览 ML.NET 中支持的不同机器学习任务和关联的任务。
ms.custom: seodec18
ms.date: 04/23/2019
author: natke
ms.openlocfilehash: bcd967c11156ca9b837631560e78722b13fc7ae0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630049"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="c7ca7-103">ML.NET 中的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="c7ca7-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="c7ca7-104">在生成机器学习模型时，首先需要定义你希望通过数据实现的目标。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="c7ca7-105">这样可以根据你的实际情况选择正确的机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="c7ca7-106">下面介绍了可以从中选择的不同机器学习任务，以及一些常见用例。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="c7ca7-107">决定适合场景的任务后，则需要选择最佳算法来训练模型。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="c7ca7-108">本节列出了每个任务的可用算法。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="c7ca7-109">二元分类</span><span class="sxs-lookup"><span data-stu-id="c7ca7-109">Binary classification</span></span>

<span data-ttu-id="c7ca7-110">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例所属的两个类（类别）。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="c7ca7-111">分类算法输入是一组标记示例，其中每个标签为整数 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="c7ca7-112">二元分类算法的输出是一个分类器，可用于预测未标记的新实例的类。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="c7ca7-113">二元分类方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="c7ca7-114">[了解 Twitter 评论的情绪](../tutorials/sentiment-analysis.md)，“正面”或“负面”。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="c7ca7-115">诊断患者是否患有某种疾病。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="c7ca7-116">决定是否要将电子邮件标记为“垃圾邮件”。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="c7ca7-117">确定照片是否包含狗或水果。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="c7ca7-118">有关详细信息，请参阅 Wikipedia 上的[二元分类](https://en.wikipedia.org/wiki/Binary_classification)一文。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="c7ca7-119">二元分类训练程序</span><span class="sxs-lookup"><span data-stu-id="c7ca7-119">Binary classification trainers</span></span>

<span data-ttu-id="c7ca7-120">可以使用以下算法训练二元分类模型：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer> 
* <xref:Microsoft.ML.Trainers.PriorTrainer> 
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="c7ca7-121">二元分类输入和输出</span><span class="sxs-lookup"><span data-stu-id="c7ca7-121">Binary classification inputs and outputs</span></span>

<span data-ttu-id="c7ca7-122">为了通过二元分类获得最佳结果，应平衡训练数据（即正训练数据和负训练数据的数量相等）。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-122">For best results with binary classification, the training data should be balanced (that is, equal numbers of positive and negative training data).</span></span> <span data-ttu-id="c7ca7-123">应在训练前处理缺失值。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-123">Missing values should be handled before training.</span></span>

<span data-ttu-id="c7ca7-124">输入标签列数据必须为 <xref:System.Boolean>。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-124">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="c7ca7-125">输入特征列数据必须为 <xref:System.Single> 的固定大小向量。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-125">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="c7ca7-126">这些训练程序输出以下列：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-126">These trainers outputs the following columns:</span></span>

| <span data-ttu-id="c7ca7-127">输出列名称</span><span class="sxs-lookup"><span data-stu-id="c7ca7-127">Output Column Name</span></span> | <span data-ttu-id="c7ca7-128">列名称</span><span class="sxs-lookup"><span data-stu-id="c7ca7-128">Column Type</span></span> | <span data-ttu-id="c7ca7-129">说明</span><span class="sxs-lookup"><span data-stu-id="c7ca7-129">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="c7ca7-130">由模型计算得出的原始分数</span><span class="sxs-lookup"><span data-stu-id="c7ca7-130">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="c7ca7-131">预测的标签，基于分数符号。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-131">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="c7ca7-132">负分数映射到 `false`，正分数映射到 `true`。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-132">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="c7ca7-133">多类分类</span><span class="sxs-lookup"><span data-stu-id="c7ca7-133">Multiclass classification</span></span>

<span data-ttu-id="c7ca7-134">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于预测数据实例的类（类别）。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-134">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="c7ca7-135">分类算法输入是一组标记示例。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-135">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="c7ca7-136">每个标签通常以文本形式开始。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-136">Each label normally starts as text.</span></span> <span data-ttu-id="c7ca7-137">然后通过 TermTransform 运行，它可将其转换为 Key（数字）类型。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-137">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="c7ca7-138">分类算法的输出是一个分类器，可用于预测未标记的新实例的类。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-138">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="c7ca7-139">多类分类方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-139">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="c7ca7-140">确定狗的品种是“西伯利亚哈士奇”、“金毛寻回犬”、“贵宾犬”等。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-140">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="c7ca7-141">了解电影评论是“正面”、“中立”还是“负面”。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-141">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="c7ca7-142">将酒店评语分类为“位置”、“价格”、“整洁度”等。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-142">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="c7ca7-143">有关详细信息，请参阅 Wikipedia 上的[多类分类](https://en.wikipedia.org/wiki/Multiclass_classification)一文。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-143">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="c7ca7-144">一个与所有升级任何[二元分类学习器](#binary-classification)，以便对多类数据集进行操作。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-144">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="c7ca7-145">有关详细信息，请参阅 [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest) 。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-145">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="c7ca7-146">多类分类训练程序</span><span class="sxs-lookup"><span data-stu-id="c7ca7-146">Multiclass classification trainers</span></span>

<span data-ttu-id="c7ca7-147">可以使用以下训练算法训练多类分类模型：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-147">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer> 

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="c7ca7-148">多类分类输入和输出</span><span class="sxs-lookup"><span data-stu-id="c7ca7-148">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="c7ca7-149">输入标签列数据必须为 [key](xref:Microsoft.ML.Data.KeyDataViewType) 类型。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-149">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="c7ca7-150">特征列必须为 <xref:System.Single> 的固定大小向量。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-150">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="c7ca7-151">该训练程序输出以下列：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-151">This trainer outputs the following:</span></span>

| <span data-ttu-id="c7ca7-152">输出名称</span><span class="sxs-lookup"><span data-stu-id="c7ca7-152">Output Name</span></span> | <span data-ttu-id="c7ca7-153">类型</span><span class="sxs-lookup"><span data-stu-id="c7ca7-153">Type</span></span> | <span data-ttu-id="c7ca7-154">说明</span><span class="sxs-lookup"><span data-stu-id="c7ca7-154">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="c7ca7-155"><xref:System.Single> 的向量</span><span class="sxs-lookup"><span data-stu-id="c7ca7-155">Vector of <xref:System.Single></span></span> | <span data-ttu-id="c7ca7-156">所有类的分数。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-156">The scores of all classes.</span></span> <span data-ttu-id="c7ca7-157">值越高意味着落入相关类的概率越高。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-157">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="c7ca7-158">如果第 i 个元素具有最大值，则预测的标签索引为 i。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-158">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="c7ca7-159">请注意，i 是从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-159">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="c7ca7-160">[key](xref:Microsoft.ML.Data.KeyDataViewType) 类型</span><span class="sxs-lookup"><span data-stu-id="c7ca7-160">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="c7ca7-161">预测标签的索引。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-161">The predicted label's index.</span></span> <span data-ttu-id="c7ca7-162">如果其值为 i，则实际标签为键值输入标签类型中的第 i 个类别。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-162">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="c7ca7-163">回归测试</span><span class="sxs-lookup"><span data-stu-id="c7ca7-163">Regression</span></span>

<span data-ttu-id="c7ca7-164">[监管式机器学习](glossary.md#supervised-machine-learning)任务，用于从一组相关特征中预测标签值。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-164">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="c7ca7-165">标签可以是任何实际值，而不是像在分类任务中那样来自一组有限的值。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-165">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="c7ca7-166">回归算法模拟其相关特征上的标签依赖关系，以确定标签将如何随着特征值的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-166">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="c7ca7-167">回归算法输入是一组带已知值标签的示例。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-167">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="c7ca7-168">回归算法输出是一个函数，可用于预测任何一组新输入特征的标签值。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-168">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="c7ca7-169">回归方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-169">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="c7ca7-170">基于房子特性（如卧室数量、位置或大小）来预测房价。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-170">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="c7ca7-171">基于历史数据和当前市场趋势预测将来的股票价格。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-171">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="c7ca7-172">基于广告预算预测产品销售。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-172">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="c7ca7-173">回归训练程序</span><span class="sxs-lookup"><span data-stu-id="c7ca7-173">Regression trainers</span></span>

<span data-ttu-id="c7ca7-174">可以使用以下算法训练回归模型：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-174">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="c7ca7-175">回归输入和输出</span><span class="sxs-lookup"><span data-stu-id="c7ca7-175">Regression inputs and outputs</span></span>

<span data-ttu-id="c7ca7-176">输入标签列数据必须为 <xref:System.Single>。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-176">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="c7ca7-177">此任务的训练程序输出以下列：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-177">The trainers for this task output the following:</span></span>

| <span data-ttu-id="c7ca7-178">输出名称</span><span class="sxs-lookup"><span data-stu-id="c7ca7-178">Output Name</span></span> | <span data-ttu-id="c7ca7-179">类型</span><span class="sxs-lookup"><span data-stu-id="c7ca7-179">Type</span></span> | <span data-ttu-id="c7ca7-180">说明</span><span class="sxs-lookup"><span data-stu-id="c7ca7-180">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="c7ca7-181">模型预测的原始分数</span><span class="sxs-lookup"><span data-stu-id="c7ca7-181">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="c7ca7-182">聚类分析</span><span class="sxs-lookup"><span data-stu-id="c7ca7-182">Clustering</span></span>

<span data-ttu-id="c7ca7-183">[非监管式机器学习](glossary.md#unsupervised-machine-learning)任务，用于将数据实例分组到包含类似特性的群集。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-183">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="c7ca7-184">聚类分析还可用来识别可能无法通过浏览或简单的观察以逻辑方式推导出的数据集中的关系。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-184">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="c7ca7-185">聚类分析算法的输入和输出取决于选择的方法。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-185">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="c7ca7-186">可以采取分发、质心、连接或基于密度的方法。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-186">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="c7ca7-187">ML.NET 当前支持使用 K 平均值聚类分析的基于质心的方法。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-187">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="c7ca7-188">聚类分析方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-188">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="c7ca7-189">基于酒店选择的习惯和特征来了解酒店来宾群。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-189">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="c7ca7-190">确定客户群和人口统计信息来帮助生成目标广告活动。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-190">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="c7ca7-191">基于生产指标对清单进行分类。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-191">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="c7ca7-192">聚类分析训练程序</span><span class="sxs-lookup"><span data-stu-id="c7ca7-192">Clustering trainer</span></span>

<span data-ttu-id="c7ca7-193">可以使用以下算法训练聚类分析模型：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-193">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer> 

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="c7ca7-194">聚类分析输入和输出</span><span class="sxs-lookup"><span data-stu-id="c7ca7-194">Clustering inputs and outputs</span></span>

<span data-ttu-id="c7ca7-195">输入特征数据必须为 <xref:System.Single>。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-195">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="c7ca7-196">无需标签。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-196">No labels are needed.</span></span>

<span data-ttu-id="c7ca7-197">该训练程序输出以下列：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-197">This trainer outputs the following:</span></span>

| <span data-ttu-id="c7ca7-198">输出名称</span><span class="sxs-lookup"><span data-stu-id="c7ca7-198">Output Name</span></span> | <span data-ttu-id="c7ca7-199">类型</span><span class="sxs-lookup"><span data-stu-id="c7ca7-199">Type</span></span> | <span data-ttu-id="c7ca7-200">说明</span><span class="sxs-lookup"><span data-stu-id="c7ca7-200">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="c7ca7-201"><xref:System.Single> 的向量</span><span class="sxs-lookup"><span data-stu-id="c7ca7-201">vector of <xref:System.Single></span></span> | <span data-ttu-id="c7ca7-202">给定数据点到所有群集的质心的距离</span><span class="sxs-lookup"><span data-stu-id="c7ca7-202">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="c7ca7-203">[key](xref:Microsoft.ML.Data.KeyDataViewType) 类型</span><span class="sxs-lookup"><span data-stu-id="c7ca7-203">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="c7ca7-204">模型预测的最接近的群集的索引。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-204">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="c7ca7-205">异常情况检测</span><span class="sxs-lookup"><span data-stu-id="c7ca7-205">Anomaly detection</span></span>

<span data-ttu-id="c7ca7-206">此任务使用主体组件分析 (PCA) 创建异常情况检测模型。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-206">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="c7ca7-207">基于 PCA 的异常情况检测有助于在以下场景中构建模型：可以很轻松地从一个类中获得定型数据（例如有效事务），但难以获得目标异常的足够示例。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-207">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="c7ca7-208">PCA 是机器学习中已建立的一种技术，由于它揭示了数据的内部结构，并解释了数据中的差异，因此经常被用于探索性数据分析。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-208">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="c7ca7-209">PCA 的工作方式是通过分析包含多个变量的数据。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-209">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="c7ca7-210">它查找变量之间的关联性，并确定最能捕捉结果差异的值的组合。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-210">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="c7ca7-211">这些组合的特性值用于创建一个更紧凑的特性空间，称为主体组件。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-211">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="c7ca7-212">异常情况检测包含机器学习中的许多重要任务：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-212">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="c7ca7-213">识别潜在的欺诈交易。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-213">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="c7ca7-214">指示发生了网络入侵的学习模式。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-214">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="c7ca7-215">发现异常的患者群集。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-215">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="c7ca7-216">检查输入系统的值。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-216">Checking values entered into a system.</span></span>

<span data-ttu-id="c7ca7-217">根据定义，异常情况属于罕见事件，因此很难收集具有代表性的数据样本用于建模。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-217">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="c7ca7-218">此类别中包含的算法是专门设计用来解决使用不平衡数据集建立和定型模型的核心挑战。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-218">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="c7ca7-219">异常情况检测训练程序</span><span class="sxs-lookup"><span data-stu-id="c7ca7-219">Anomaly detection trainer</span></span>

<span data-ttu-id="c7ca7-220">可以使用以下算法训练异常情况检测模型：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-220">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="c7ca7-221">异常情况检测输入和输出</span><span class="sxs-lookup"><span data-stu-id="c7ca7-221">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="c7ca7-222">输入特征必须为 <xref:System.Single> 的固定大小向量。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-222">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="c7ca7-223">该训练程序输出以下列：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-223">This trainer outputs the following:</span></span>

| <span data-ttu-id="c7ca7-224">输出名称</span><span class="sxs-lookup"><span data-stu-id="c7ca7-224">Output Name</span></span> | <span data-ttu-id="c7ca7-225">类型</span><span class="sxs-lookup"><span data-stu-id="c7ca7-225">Type</span></span> | <span data-ttu-id="c7ca7-226">说明</span><span class="sxs-lookup"><span data-stu-id="c7ca7-226">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="c7ca7-227">由异常情况检测模型计算得出的非负无界分数</span><span class="sxs-lookup"><span data-stu-id="c7ca7-227">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |

## <a name="ranking"></a><span data-ttu-id="c7ca7-228">排名</span><span class="sxs-lookup"><span data-stu-id="c7ca7-228">Ranking</span></span>

<span data-ttu-id="c7ca7-229">排名任务从一组标记的示例构建排名程序。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-229">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="c7ca7-230">该示例集由实例组组成，这些实例组可以使用给定的标准进行评分。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-230">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="c7ca7-231">每个实例的排名标签是 { 0, 1, 2, 3, 4 }。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-231">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="c7ca7-232">排名程序定型为用每个实例的未知分数对新实例组进行排名。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-232">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="c7ca7-233">ML.NET 排名学习器基于[机器已学习的排名](https://en.wikipedia.org/wiki/Learning_to_rank)。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-233">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="c7ca7-234">排名训练算法</span><span class="sxs-lookup"><span data-stu-id="c7ca7-234">Ranking training algorithms</span></span>

<span data-ttu-id="c7ca7-235">可以使用以下算法训练排名模型：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-235">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer> 

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="c7ca7-236">排名输入和输出</span><span class="sxs-lookup"><span data-stu-id="c7ca7-236">Ranking input and outputs</span></span>

<span data-ttu-id="c7ca7-237">输入标签数据类型必须为 [key](xref:Microsoft.ML.Data.KeyDataViewType) 类型或 <xref:System.Single>。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-237">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="c7ca7-238">标签的值决定相关性，其中较高的值表示较高的相关性。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-238">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="c7ca7-239">如果标签为 [key](xref:Microsoft.ML.Data.KeyDataViewType) 类型，则键索引为相关性值，其中最小索引是最不相关的。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-239">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="c7ca7-240">如果标签为 <xref:System.Single>，则较大的值表示较高的相关性。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-240">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="c7ca7-241">特征数据必须为 <xref:System.Single> 的固定大小向量，输入行组列必须为 [key](xref:Microsoft.ML.Data.KeyDataViewType) 类型。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-241">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="c7ca7-242">该训练程序输出以下列：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-242">This trainer outputs the following:</span></span>

| <span data-ttu-id="c7ca7-243">输出名称</span><span class="sxs-lookup"><span data-stu-id="c7ca7-243">Output Name</span></span> | <span data-ttu-id="c7ca7-244">类型</span><span class="sxs-lookup"><span data-stu-id="c7ca7-244">Type</span></span> | <span data-ttu-id="c7ca7-245">说明</span><span class="sxs-lookup"><span data-stu-id="c7ca7-245">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="c7ca7-246">由模型计算以确定预测的无界分数</span><span class="sxs-lookup"><span data-stu-id="c7ca7-246">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="c7ca7-247">建议</span><span class="sxs-lookup"><span data-stu-id="c7ca7-247">Recommendation</span></span>

<span data-ttu-id="c7ca7-248">推荐任务支持生成推荐产品或服务的列表。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-248">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="c7ca7-249">ML.NET 使用[矩阵因子分解 (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29)，这是一种[协作筛选](https://en.wikipedia.org/wiki/Collaborative_filtering)算法，当目录中有历史产品评级数据时，推荐使用该算法。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-249">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="c7ca7-250">例如，你为用户提供历史电影评级数据，并希望向他们推荐接下来可能观看的其他电影。</span><span class="sxs-lookup"><span data-stu-id="c7ca7-250">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="c7ca7-251">建议训练算法</span><span class="sxs-lookup"><span data-stu-id="c7ca7-251">Recommendation training algorithms</span></span>

<span data-ttu-id="c7ca7-252">可以使用以下算法训练建议模型：</span><span class="sxs-lookup"><span data-stu-id="c7ca7-252">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
