---
title: 机器学习术语表 - ML.NET
description: 一个重要的机器学习术语表，可在 ML.NET 中生成自定义模型时使用。
ms.custom: seodec18
ms.date: 12/06/2018
ms.openlocfilehash: 4db28a62fccca2e8bedc9f48485a61b6f4ab1801
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150571"
---
# <a name="machine-learning-glossary-of-important-terms"></a><span data-ttu-id="f6c20-103">机器学习重要术语词汇表</span><span class="sxs-lookup"><span data-stu-id="f6c20-103">Machine learning glossary of important terms</span></span>

<span data-ttu-id="f6c20-104">以下列表是重要的机器学习术语编译，可在 ML.NET 中生成自定义模型时使用。</span><span class="sxs-lookup"><span data-stu-id="f6c20-104">The following list is a compilation of important machine learning terms that are useful as you build your custom models in ML.NET.</span></span>

## <a name="accuracy"></a><span data-ttu-id="f6c20-105">准确性</span><span class="sxs-lookup"><span data-stu-id="f6c20-105">Accuracy</span></span>

<span data-ttu-id="f6c20-106">在[分类](#classification)中，准确性是正确分类的项数目除以测试集内的项总数。</span><span class="sxs-lookup"><span data-stu-id="f6c20-106">In [classification](#classification), accuracy is the number of correctly classified items divided by the total number of items in the test set.</span></span> <span data-ttu-id="f6c20-107">范围从 0（最不准确）到 1（最准确）。</span><span class="sxs-lookup"><span data-stu-id="f6c20-107">Ranges from 0 (least accurate) to 1 (most accurate).</span></span> <span data-ttu-id="f6c20-108">准确性是模型性能的评估指标之一。</span><span class="sxs-lookup"><span data-stu-id="f6c20-108">Accuracy is one of evaluation metrics of the performance of your model.</span></span> <span data-ttu-id="f6c20-109">将其与[精度](#precision)、[撤回](#recall)和 [F 分数](#f-score)结合考虑。</span><span class="sxs-lookup"><span data-stu-id="f6c20-109">Consider it in conjunction with [precision](#precision), [recall](#recall), and [F-score](#f-score).</span></span>

<span data-ttu-id="f6c20-110">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.Accuracy?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-110">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.Accuracy?displayProperty=nameWithType>.</span></span>

## <a name="area-under-the-curve-auc"></a><span data-ttu-id="f6c20-111">曲线下面积 (AUC)</span><span class="sxs-lookup"><span data-stu-id="f6c20-111">Area under the curve (AUC)</span></span>

<span data-ttu-id="f6c20-112">[二元分类](#binary-classification)中的一项评估指标，即曲线下面积值，它绘制真阳性率（y 轴）与误报率（x 轴）进行对照。</span><span class="sxs-lookup"><span data-stu-id="f6c20-112">In [binary classification](#binary-classification), an evaluation metric that is the value of the area under the curve that plots the true positives rate (on the y-axis) against the false positives rate (on the x-axis).</span></span> <span data-ttu-id="f6c20-113">范围从 0.5（最差）到 1（最佳）。</span><span class="sxs-lookup"><span data-stu-id="f6c20-113">Ranges from 0.5 (worst) to 1 (best).</span></span> <span data-ttu-id="f6c20-114">也称为 ROC 曲线下面积，即，接受者操作特征曲线。</span><span class="sxs-lookup"><span data-stu-id="f6c20-114">Also known as the area under the ROC curve, i.e., receiver operating characteristic curve.</span></span> <span data-ttu-id="f6c20-115">有关详细信息，请参阅 Wikipedia 上的[接受者操作特征](https://en.wikipedia.org/wiki/Receiver_operating_characteristic)一文。</span><span class="sxs-lookup"><span data-stu-id="f6c20-115">For more information, see the [Receiver operating characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) article on Wikipedia.</span></span>

<span data-ttu-id="f6c20-116">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.Auc?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-116">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.Auc?displayProperty=nameWithType>.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="f6c20-117">二元分类</span><span class="sxs-lookup"><span data-stu-id="f6c20-117">Binary classification</span></span>

<span data-ttu-id="f6c20-118">一个[分类](#classification)事例，其中[标签](#label)仅为两个类中的一个。</span><span class="sxs-lookup"><span data-stu-id="f6c20-118">A [classification](#classification) case where the [label](#label) is only one out of two classes.</span></span> <span data-ttu-id="f6c20-119">有关详细信息，请参阅[机器学习任务](tasks.md)主题的[二元分类](tasks.md#binary-classification)部分。</span><span class="sxs-lookup"><span data-stu-id="f6c20-119">For more information, see the [Binary classification](tasks.md#binary-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="classification"></a><span data-ttu-id="f6c20-120">分类</span><span class="sxs-lookup"><span data-stu-id="f6c20-120">Classification</span></span>

<span data-ttu-id="f6c20-121">当使用这些数据来预测某一类别，[监管式机器学习](#supervised-machine-learning)任务被称为“分类”。</span><span class="sxs-lookup"><span data-stu-id="f6c20-121">When the data is used to predict a category, [supervised machine learning](#supervised-machine-learning) task is called classification.</span></span> <span data-ttu-id="f6c20-122">[二元分类](#binary-classification)指的是仅预测两个类别（例如，将图像划分为“猫”或“狗”图片）。</span><span class="sxs-lookup"><span data-stu-id="f6c20-122">[Binary classification](#binary-classification) refers to predicting only two categories (for example, classifying an image as a picture of either a 'cat' or a 'dog').</span></span> <span data-ttu-id="f6c20-123">[多类分类](#multiclass-classification)指的是预测多个类别（例如，当将图像划分为特定品种狗的图片）。</span><span class="sxs-lookup"><span data-stu-id="f6c20-123">[Multiclass classification](#multiclass-classification) refers to predicting multiple categories (for example, when classifying an image as a picture of a specific breed of dog).</span></span>

## <a name="coefficient-of-determination"></a><span data-ttu-id="f6c20-124">决定系数</span><span class="sxs-lookup"><span data-stu-id="f6c20-124">Coefficient of determination</span></span>

<span data-ttu-id="f6c20-125">[回归](#regression)中的一项评估指标，表明数据与模型的匹配程度。</span><span class="sxs-lookup"><span data-stu-id="f6c20-125">In [regression](#regression), an evaluation metric that indicates how well data fits a model.</span></span> <span data-ttu-id="f6c20-126">范围从 0 到 1。</span><span class="sxs-lookup"><span data-stu-id="f6c20-126">Ranges from 0 to 1.</span></span> <span data-ttu-id="f6c20-127">值 0 表示数据是随机的，否则就无法与模型相匹配。</span><span class="sxs-lookup"><span data-stu-id="f6c20-127">A value of 0 means that the data is random or otherwise cannot be fit to the model.</span></span> <span data-ttu-id="f6c20-128">值 1 表示模型与数据完全匹配。</span><span class="sxs-lookup"><span data-stu-id="f6c20-128">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="f6c20-129">这通常称为 <sup>2</sup>、R<sup>2</sup> 或 r 平方值。</span><span class="sxs-lookup"><span data-stu-id="f6c20-129">This is often referred to as r<sup>2</sup>, R<sup>2</sup>, or r-squared.</span></span>

<span data-ttu-id="f6c20-130">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.RegressionMetrics.RSquared?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-130">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.RegressionMetrics.RSquared?displayProperty=nameWithType>.</span></span>

## <a name="feature"></a><span data-ttu-id="f6c20-131">功能</span><span class="sxs-lookup"><span data-stu-id="f6c20-131">Feature</span></span>

<span data-ttu-id="f6c20-132">正在对其进行度量的现象的一个可度量属性，通常是一个数（双精度）值。</span><span class="sxs-lookup"><span data-stu-id="f6c20-132">A measurable property of the phenomenon being measured, typically a numeric (double) value.</span></span> <span data-ttu-id="f6c20-133">多个特征被称为“特征向量”且通常存储为 `double[]`。</span><span class="sxs-lookup"><span data-stu-id="f6c20-133">Multiple features are referred to as a **Feature vector** and typically stored as `double[]`.</span></span> <span data-ttu-id="f6c20-134">这些特征定义所度量现象的重要特性。</span><span class="sxs-lookup"><span data-stu-id="f6c20-134">Features define the important characteristics of the phenomenon being measured.</span></span> <span data-ttu-id="f6c20-135">有关详细信息，请参阅 Wikipedia 上的[特征](https://en.wikipedia.org/wiki/Feature_(machine_learning))一文。</span><span class="sxs-lookup"><span data-stu-id="f6c20-135">For more information, see the [Feature](https://en.wikipedia.org/wiki/Feature_(machine_learning)) article on Wikipedia.</span></span>

## <a name="feature-engineering"></a><span data-ttu-id="f6c20-136">特征工程</span><span class="sxs-lookup"><span data-stu-id="f6c20-136">Feature engineering</span></span>

<span data-ttu-id="f6c20-137">特征工程是涉及定义一组[特征](#feature)和开发软件以从可用现象数据中生成特征向量（即特征提取）的过程。</span><span class="sxs-lookup"><span data-stu-id="f6c20-137">Feature engineering is the process that involves defining a set of [features](#feature) and developing software that produces feature vectors from available phenomenon data, i.e., feature extraction.</span></span> <span data-ttu-id="f6c20-138">有关详细信息，请参阅 Wikipedia 上的[特征工程](https://en.wikipedia.org/wiki/Feature_engineering)一文。</span><span class="sxs-lookup"><span data-stu-id="f6c20-138">For more information, see the [Feature engineering](https://en.wikipedia.org/wiki/Feature_engineering) article on Wikipedia.</span></span>

## <a name="f-score"></a><span data-ttu-id="f6c20-139">F 分数</span><span class="sxs-lookup"><span data-stu-id="f6c20-139">F-score</span></span>

<span data-ttu-id="f6c20-140">[分类](#classification)中的一项评估指标，它平衡[精度](#precision)和[撤回](#recall)。</span><span class="sxs-lookup"><span data-stu-id="f6c20-140">In [classification](#classification), an evaluation metric that balances [precision](#precision) and [recall](#recall).</span></span>

<span data-ttu-id="f6c20-141">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.F1Score?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-141">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.F1Score?displayProperty=nameWithType>.</span></span>

## <a name="hyperparameter"></a><span data-ttu-id="f6c20-142">超参数</span><span class="sxs-lookup"><span data-stu-id="f6c20-142">Hyperparameter</span></span>

<span data-ttu-id="f6c20-143">机器学习算法的参数。</span><span class="sxs-lookup"><span data-stu-id="f6c20-143">A parameter of a machine learning algorithm.</span></span> <span data-ttu-id="f6c20-144">示例包括在决策林中学习的树的数量，或者梯度下降算法中的步长。</span><span class="sxs-lookup"><span data-stu-id="f6c20-144">Examples include the number of trees to learn in a decision forest or the step size in a gradient descent algorithm.</span></span> <span data-ttu-id="f6c20-145">在对模型进行定型之前，先设置超参数的值，并控制查找预测函数参数的过程，例如，决策树中的比较点或线性回归模型中的权重。</span><span class="sxs-lookup"><span data-stu-id="f6c20-145">Values of *Hyperparameters* are set before training the model and govern the process of finding the parameters of the prediction function, for example, the comparison points in a decision tree or the weights in a linear regression model.</span></span> <span data-ttu-id="f6c20-146">有关详细信息，请参阅 Wikipedia 上的[超参数](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning))一文。</span><span class="sxs-lookup"><span data-stu-id="f6c20-146">For more information, see the [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)) article on Wikipedia.</span></span>

## <a name="label"></a><span data-ttu-id="f6c20-147">Label</span><span class="sxs-lookup"><span data-stu-id="f6c20-147">Label</span></span>

<span data-ttu-id="f6c20-148">使用机器学习模型进行预测的元素。</span><span class="sxs-lookup"><span data-stu-id="f6c20-148">The element to be predicted with the machine learning model.</span></span> <span data-ttu-id="f6c20-149">例如，狗的品种或将来的股票价格。</span><span class="sxs-lookup"><span data-stu-id="f6c20-149">For example, the breed of dog or a future stock price.</span></span>

## <a name="log-loss"></a><span data-ttu-id="f6c20-150">对数损失</span><span class="sxs-lookup"><span data-stu-id="f6c20-150">Log loss</span></span>

<span data-ttu-id="f6c20-151">在[分类](#classification)中，描述分类器准确性的评估指标。</span><span class="sxs-lookup"><span data-stu-id="f6c20-151">In [classification](#classification), an evaluation metric that characterizes the accuracy of a classifier.</span></span> <span data-ttu-id="f6c20-152">对数损失越小，分类器越准确。</span><span class="sxs-lookup"><span data-stu-id="f6c20-152">The smaller log loss is, the more accurate a classifier is.</span></span>

<span data-ttu-id="f6c20-153">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.LogLoss?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-153">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.LogLoss?displayProperty=nameWithType>.</span></span>

## <a name="mean-absolute-error-mae"></a><span data-ttu-id="f6c20-154">平均绝对误差 (MAE)</span><span class="sxs-lookup"><span data-stu-id="f6c20-154">Mean absolute error (MAE)</span></span>

<span data-ttu-id="f6c20-155">[回归](#regression)中的一项评估指标，即所有模型误差的平均值，其中模型误差是预测[标签](#label)值和正确标签值之间的差距。</span><span class="sxs-lookup"><span data-stu-id="f6c20-155">In [regression](#regression), an evaluation metric that is the average of all the model errors, where model error is the distance between the predicted [label](#label) value and the correct label value.</span></span>

<span data-ttu-id="f6c20-156">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.RegressionMetrics.L1?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-156">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.RegressionMetrics.L1?displayProperty=nameWithType>.</span></span>

## <a name="model"></a><span data-ttu-id="f6c20-157">模型</span><span class="sxs-lookup"><span data-stu-id="f6c20-157">Model</span></span>

<span data-ttu-id="f6c20-158">就传统意义而言，它是预测函数的参数。</span><span class="sxs-lookup"><span data-stu-id="f6c20-158">Traditionally, the parameters for the prediction function.</span></span> <span data-ttu-id="f6c20-159">例如，线性回归模型中的权重或决策树中的拆分点。</span><span class="sxs-lookup"><span data-stu-id="f6c20-159">For example, the weights in a linear regression model or the split points in a decision tree.</span></span> <span data-ttu-id="f6c20-160">在 ML.NET 中，一个模型包含预测域对象[标签](#label)所需的所有信息（例如，图像或文本）。</span><span class="sxs-lookup"><span data-stu-id="f6c20-160">In ML.NET, a model contains all the information necessary to predict the [label](#label) of a domain object (for example, image or text).</span></span> <span data-ttu-id="f6c20-161">这意味着 ML.NET 模型包括所需的特征化步骤以及预测函数参数。</span><span class="sxs-lookup"><span data-stu-id="f6c20-161">This means that ML.NET models include the featurization steps necessary as well as the parameters for the prediction function.</span></span>

## <a name="multiclass-classification"></a><span data-ttu-id="f6c20-162">多类分类</span><span class="sxs-lookup"><span data-stu-id="f6c20-162">Multiclass classification</span></span>

<span data-ttu-id="f6c20-163">一个[分类](#classification)事例，其中[标签](#label)是三个或更多类中的一个。</span><span class="sxs-lookup"><span data-stu-id="f6c20-163">A [classification](#classification) case where the [label](#label) is one out of three or more classes.</span></span> <span data-ttu-id="f6c20-164">有关详细信息，请参阅[机器学习任务](tasks.md)主题的[多类分类](tasks.md#multiclass-classification)部分。</span><span class="sxs-lookup"><span data-stu-id="f6c20-164">For more information, see the [Multiclass classification](tasks.md#multiclass-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="n-gram"></a><span data-ttu-id="f6c20-165">N 元语法</span><span class="sxs-lookup"><span data-stu-id="f6c20-165">N-gram</span></span>

<span data-ttu-id="f6c20-166">文本数据的特征提取方案：N 个单词的任何序列都将转变为[特征](#feature)值。</span><span class="sxs-lookup"><span data-stu-id="f6c20-166">A feature extraction scheme for text data: any sequence of N words turns into a [feature](#feature) value.</span></span>

## <a name="numerical-feature-vector"></a><span data-ttu-id="f6c20-167">数字特征向量</span><span class="sxs-lookup"><span data-stu-id="f6c20-167">Numerical feature vector</span></span>

<span data-ttu-id="f6c20-168">只包含数值的[特征](#feature)向量。</span><span class="sxs-lookup"><span data-stu-id="f6c20-168">A [feature](#feature) vector consisting only of numerical values.</span></span> <span data-ttu-id="f6c20-169">这与 `double[]` 非常类似。</span><span class="sxs-lookup"><span data-stu-id="f6c20-169">This is similar to `double[]`.</span></span>

## <a name="pipeline"></a><span data-ttu-id="f6c20-170">管道</span><span class="sxs-lookup"><span data-stu-id="f6c20-170">Pipeline</span></span>

<span data-ttu-id="f6c20-171">要将模型与数据集相匹配所需的所有操作。</span><span class="sxs-lookup"><span data-stu-id="f6c20-171">All of the operations needed to fit a model to a data set.</span></span> <span data-ttu-id="f6c20-172">管道由数据导入、转换、特征化和学习步骤组成。</span><span class="sxs-lookup"><span data-stu-id="f6c20-172">A pipeline consists of data import, transformation, featurization, and learning steps.</span></span> <span data-ttu-id="f6c20-173">对管道进行定型后，它会转变为模型。</span><span class="sxs-lookup"><span data-stu-id="f6c20-173">Once a pipeline is trained, it turns into a model.</span></span>

## <a name="precision"></a><span data-ttu-id="f6c20-174">精度</span><span class="sxs-lookup"><span data-stu-id="f6c20-174">Precision</span></span>

<span data-ttu-id="f6c20-175">在[分类](#classification)中，类的精度是正确预测为属于该类的项目的数量，除以预测为属于该类的项目的总数。</span><span class="sxs-lookup"><span data-stu-id="f6c20-175">In [classification](#classification), the precision for a class is the number of items correctly predicted as belonging to that class divided by the total number of items predicted as belonging to the class.</span></span>

<span data-ttu-id="f6c20-176">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.NegativePrecision?displayProperty=nameWithType>、<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.PositivePrecision?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-176">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.NegativePrecision?displayProperty=nameWithType>, <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.PositivePrecision?displayProperty=nameWithType>.</span></span>

## <a name="recall"></a><span data-ttu-id="f6c20-177">撤回</span><span class="sxs-lookup"><span data-stu-id="f6c20-177">Recall</span></span>

<span data-ttu-id="f6c20-178">在[分类](#classification)中，类的撤回是正确预测为属于该类的项目的数量，除以实际属于该类的项目的总数。</span><span class="sxs-lookup"><span data-stu-id="f6c20-178">In [classification](#classification), the recall for a class is the number of items correctly predicted as belonging to that class divided by the total number of items that actually belong to the class.</span></span>

<span data-ttu-id="f6c20-179">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.NegativeRecall?displayProperty=nameWithType>、<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.PositiveRecall?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-179">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.NegativeRecall?displayProperty=nameWithType>, <xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics.PositiveRecall?displayProperty=nameWithType>.</span></span>

## <a name="regression"></a><span data-ttu-id="f6c20-180">回归</span><span class="sxs-lookup"><span data-stu-id="f6c20-180">Regression</span></span>

<span data-ttu-id="f6c20-181">[监管式机器学习](#supervised-machine-learning)任务，其中输出是一个实际值，例如，双精度值。</span><span class="sxs-lookup"><span data-stu-id="f6c20-181">A [supervised machine learning](#supervised-machine-learning) task where the output is a real value, for example, double.</span></span> <span data-ttu-id="f6c20-182">示例包括预测股票价格。</span><span class="sxs-lookup"><span data-stu-id="f6c20-182">Examples include predicting stock prices.</span></span> <span data-ttu-id="f6c20-183">有关详细信息，请参阅[机器学习任务](tasks.md)主题的[回归](tasks.md#regression)部分。</span><span class="sxs-lookup"><span data-stu-id="f6c20-183">For more information, see the [Regression](tasks.md#regression) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="relative-absolute-error"></a><span data-ttu-id="f6c20-184">相对绝对误差</span><span class="sxs-lookup"><span data-stu-id="f6c20-184">Relative absolute error</span></span>

<span data-ttu-id="f6c20-185">[回归](#regression)中的一项评估指标，即所有绝对误差总和除以正确[标签](#label)值和所有正确标签值的平均值之间的差值总和。</span><span class="sxs-lookup"><span data-stu-id="f6c20-185">In [regression](#regression), an evaluation metric that is the sum of all absolute errors divided by the sum of distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="relative-squared-error"></a><span data-ttu-id="f6c20-186">相对平方误差</span><span class="sxs-lookup"><span data-stu-id="f6c20-186">Relative squared error</span></span>

<span data-ttu-id="f6c20-187">[回归](#regression)中的一项评估指标，即所有绝对平方误差总和除以正确[标签](#label)值和所有正确标签值的平均值之间的平方差值总和。</span><span class="sxs-lookup"><span data-stu-id="f6c20-187">In [regression](#regression), an evaluation metric that is the sum of all squared absolute errors divided by the sum of squared distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="root-of-mean-squared-error-rmse"></a><span data-ttu-id="f6c20-188">均方误差根 (RMSE)</span><span class="sxs-lookup"><span data-stu-id="f6c20-188">Root of mean squared error (RMSE)</span></span>

<span data-ttu-id="f6c20-189">[回归](#regression)中的一项评估指标，即误差平方平均值的平方根。</span><span class="sxs-lookup"><span data-stu-id="f6c20-189">In [regression](#regression), an evaluation metric that is the square root of the average of the squares of the errors.</span></span>

<span data-ttu-id="f6c20-190">相关 ML.NET API：<xref:Microsoft.ML.Legacy.Models.RegressionMetrics.Rms?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6c20-190">Related ML.NET API: <xref:Microsoft.ML.Legacy.Models.RegressionMetrics.Rms?displayProperty=nameWithType>.</span></span>

## <a name="supervised-machine-learning"></a><span data-ttu-id="f6c20-191">监管式机器学习</span><span class="sxs-lookup"><span data-stu-id="f6c20-191">Supervised machine learning</span></span>

<span data-ttu-id="f6c20-192">机器学习的一个子类，其中所需的模型预测尚不可见的数据标签。</span><span class="sxs-lookup"><span data-stu-id="f6c20-192">A subclass of machine learning in which a desired model predicts the label for yet-unseen data.</span></span> <span data-ttu-id="f6c20-193">示例包括分类、回归以及结构化预测。</span><span class="sxs-lookup"><span data-stu-id="f6c20-193">Examples include classification, regression, and structured prediction.</span></span> <span data-ttu-id="f6c20-194">有关详细信息，请参阅 Wikipedia 上的[监管式学习](https://en.wikipedia.org/wiki/Supervised_learning)一文。</span><span class="sxs-lookup"><span data-stu-id="f6c20-194">For more information, see the  [Supervised learning](https://en.wikipedia.org/wiki/Supervised_learning) article on Wikipedia.</span></span>

## <a name="training"></a><span data-ttu-id="f6c20-195">训练</span><span class="sxs-lookup"><span data-stu-id="f6c20-195">Training</span></span>

<span data-ttu-id="f6c20-196">识别给定定型数据集[模型](#model)的过程。</span><span class="sxs-lookup"><span data-stu-id="f6c20-196">The process of identifying a [model](#model) for a given training data set.</span></span> <span data-ttu-id="f6c20-197">对于线性模型，这意味着查找权重。</span><span class="sxs-lookup"><span data-stu-id="f6c20-197">For a linear model, this means finding the weights.</span></span> <span data-ttu-id="f6c20-198">有关树信息，这涉及到标识拆分点。</span><span class="sxs-lookup"><span data-stu-id="f6c20-198">For a tree, it involves the identifying the split points.</span></span>

## <a name="transform"></a><span data-ttu-id="f6c20-199">Transform</span><span class="sxs-lookup"><span data-stu-id="f6c20-199">Transform</span></span>

<span data-ttu-id="f6c20-200">转换数据的[管道](#pipeline)组件。</span><span class="sxs-lookup"><span data-stu-id="f6c20-200">A [pipeline](#pipeline) component that transforms data.</span></span> <span data-ttu-id="f6c20-201">例如，从文本到数字向量。</span><span class="sxs-lookup"><span data-stu-id="f6c20-201">For example, from text to vector of numbers.</span></span>

## <a name="unsupervised-machine-learning"></a><span data-ttu-id="f6c20-202">非监管式机器学习</span><span class="sxs-lookup"><span data-stu-id="f6c20-202">Unsupervised machine learning</span></span>

<span data-ttu-id="f6c20-203">机器学习的子类，其中所需的模型查找数据中的隐藏（或潜在）结构。</span><span class="sxs-lookup"><span data-stu-id="f6c20-203">A subclass of machine learning in which a desired model finds hidden (or latent) structure in data.</span></span> <span data-ttu-id="f6c20-204">示例包括聚类分析、主题建模和维数约简。</span><span class="sxs-lookup"><span data-stu-id="f6c20-204">Examples include clustering, topic modeling, and dimensionality reduction.</span></span> <span data-ttu-id="f6c20-205">有关详细信息，请参阅 Wikipedia 上的[非监管式学习](https://en.wikipedia.org/wiki/Unsupervised_learning)一文。</span><span class="sxs-lookup"><span data-stu-id="f6c20-205">For more information, see the [Unsupervised learning](https://en.wikipedia.org/wiki/Unsupervised_learning) article on Wikipedia.</span></span>
