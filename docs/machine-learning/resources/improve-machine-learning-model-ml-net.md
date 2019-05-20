---
title: 操作说明：提高模型准确性
description: 了解如何提高模型准确性
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc
ms.openlocfilehash: 8bb47102ede8e135090b1381eb815dccd512e03d
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557803"
---
# <a name="improve-mlnet-model-accuracy"></a><span data-ttu-id="2be48-103">提高 ML.NET 模型准确性</span><span class="sxs-lookup"><span data-stu-id="2be48-103">Improve ML.NET Model Accuracy</span></span>

<span data-ttu-id="2be48-104">了解如何提高模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="2be48-104">Learn how to improve the accuracy of your model.</span></span>

## <a name="reframe-the-problem"></a><span data-ttu-id="2be48-105">重新定义问题</span><span class="sxs-lookup"><span data-stu-id="2be48-105">Reframe the problem</span></span>

<span data-ttu-id="2be48-106">有时，改进模型可能与用于训练模型的数据或技术无关。</span><span class="sxs-lookup"><span data-stu-id="2be48-106">Sometimes, improving a model may have nothing to do with the data or techniques used to train the model.</span></span> <span data-ttu-id="2be48-107">相反，可能只是提出了错误的问题。</span><span class="sxs-lookup"><span data-stu-id="2be48-107">Instead, it may just be that the wrong question is being asked.</span></span> <span data-ttu-id="2be48-108">考虑从不同的角度看待问题，并利用数据提取潜在指示和隐藏关系，以便优化问题。</span><span class="sxs-lookup"><span data-stu-id="2be48-108">Consider looking at the problem from different angles and leverage the data to extract latent indicators and hidden relationships in order to refine the question.</span></span>

## <a name="provide-more-data-samples"></a><span data-ttu-id="2be48-109">提供更多数据示例</span><span class="sxs-lookup"><span data-stu-id="2be48-109">Provide more data samples</span></span>

<span data-ttu-id="2be48-110">与人类一样，训练算法获得的信息越多，性能更好的可能性就越大。</span><span class="sxs-lookup"><span data-stu-id="2be48-110">Like humans, the more training algorithms get, the likelihood of better performance increases.</span></span> <span data-ttu-id="2be48-111">提高模型性能的方法之一是为算法提供更多训练数据示例。</span><span class="sxs-lookup"><span data-stu-id="2be48-111">One way to improve model performance is to provide more training data samples to the algorithms.</span></span> <span data-ttu-id="2be48-112">模型从中进行学习的数据越多，模型能够正确识别的案例就越多。</span><span class="sxs-lookup"><span data-stu-id="2be48-112">The more data it learns from, the more cases it is able to correctly identify.</span></span>

## <a name="add-context-to-the-data"></a><span data-ttu-id="2be48-113">为数据添加上下文</span><span class="sxs-lookup"><span data-stu-id="2be48-113">Add context to the data</span></span>

<span data-ttu-id="2be48-114">单个数据点的含义可能难以解读。</span><span class="sxs-lookup"><span data-stu-id="2be48-114">The meaning of a single data point can be difficult to interpret.</span></span> <span data-ttu-id="2be48-115">围绕数据点生成上下文有助于算法和主题专家更好地做出决策。</span><span class="sxs-lookup"><span data-stu-id="2be48-115">Building context around the data points helps algorithms as well as subject matter experts better make decisions.</span></span> <span data-ttu-id="2be48-116">例如，房屋拥有三间卧室这一事实本身并不能很好地说明其价格。</span><span class="sxs-lookup"><span data-stu-id="2be48-116">For example, the fact that a house has three bedrooms does not on its own give a good indication of its price.</span></span> <span data-ttu-id="2be48-117">但是，如果在添加上下文之后，现在知道它位于大都市圈附近的郊区，屋主平均年龄为 38 岁，家庭平均收入为 80,000 美元，附近学校的排名在前 20%，那么算法可在更多信息的基础之上做出自己的决策。</span><span class="sxs-lookup"><span data-stu-id="2be48-117">However, if you add context and now know that it is in a suburban neighborhood outside of a major metropolitan area where average age is 38, average household income is $80,000 and schools are in the top 20th percentile then the algorithm has more information to base its decisions on.</span></span> <span data-ttu-id="2be48-118">所有这些上下文都可以作为特征添加到机器学习模型的输入中。</span><span class="sxs-lookup"><span data-stu-id="2be48-118">All of this context can be added as input to the machine learning model as features.</span></span>

## <a name="use-meaningful-data-and-features"></a><span data-ttu-id="2be48-119">使用有意义的数据和特征</span><span class="sxs-lookup"><span data-stu-id="2be48-119">Use meaningful data and features</span></span>

<span data-ttu-id="2be48-120">虽然更多的数据示例和特征可以帮助提高模型的准确性，但它们也可能会引入干扰，因为并非所有数据和特征都有意义。</span><span class="sxs-lookup"><span data-stu-id="2be48-120">Although more data samples and features can help improve the accuracy of the model, they may also introduce noise since not all data and features are meaningful.</span></span> <span data-ttu-id="2be48-121">因此，了解哪些特征对算法所做的决策具有最大影响非常重要。</span><span class="sxs-lookup"><span data-stu-id="2be48-121">Therefore, it is important to understand which features are the ones that most heavily impact decisions made by the algorithm.</span></span> <span data-ttu-id="2be48-122">使用排列特征重要性 (PFI) 等技术可以帮助识别这些突出的特征，这不仅有助于解释模型，还可以使用输出作为特征选择方法来减少进入训练过程的干扰特征的数量。</span><span class="sxs-lookup"><span data-stu-id="2be48-122">Using techniques like Permutation Feature Importance (PFI) can help identify those salient features and not only help explain the model but also use the output as a feature selection method to reduce the amount of noisy features going into the training process.</span></span>

<span data-ttu-id="2be48-123">访问以下[链接](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md)，了解如何使用 PFI</span><span class="sxs-lookup"><span data-stu-id="2be48-123">Learn to use PFI by visiting the following [link](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md)</span></span>

## <a name="cross-validation"></a><span data-ttu-id="2be48-124">交叉验证</span><span class="sxs-lookup"><span data-stu-id="2be48-124">Cross-validation</span></span>

<span data-ttu-id="2be48-125">交叉验证是一种训练和模型评估技术，可将数据拆分为多个分区，并利用这些分区训练多个算法。</span><span class="sxs-lookup"><span data-stu-id="2be48-125">Cross-validation is a training and model evaluation technique that splits the data into several partitions and trains multiple algorithms on these partitions.</span></span> <span data-ttu-id="2be48-126">此技术通过保留来自训练过程的数据来提高模型的可靠性。</span><span class="sxs-lookup"><span data-stu-id="2be48-126">This technique improves the robustness of the model by holding out data from the training process.</span></span> <span data-ttu-id="2be48-127">除提高不可见观测的性能之外，在数据受限的环境中，它还可用作使用较小数据集训练模型的有效工具。</span><span class="sxs-lookup"><span data-stu-id="2be48-127">In addition to improving performance on unseen observations, in data-constrained environments it can be an effective tool for training models with a smaller dataset.</span></span>

<span data-ttu-id="2be48-128">访问以下链接，了解[如何在 ML.NET 中使用交叉验证](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md)</span><span class="sxs-lookup"><span data-stu-id="2be48-128">Visit the following link to learn [how to use cross validation in ML.NET](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md)</span></span>

## <a name="hyperparameter-tuning"></a><span data-ttu-id="2be48-129">超参数调整</span><span class="sxs-lookup"><span data-stu-id="2be48-129">Hyperparameter tuning</span></span>

<span data-ttu-id="2be48-130">训练机器学习模型是一个迭代和探索的过程。</span><span class="sxs-lookup"><span data-stu-id="2be48-130">Training machine learning models is an iterative and exploratory process.</span></span> <span data-ttu-id="2be48-131">例如，使用 K-Means 算法训练模型时，最优群集数是多少？</span><span class="sxs-lookup"><span data-stu-id="2be48-131">For example, what is the optimal number of clusters when training a model using the K-Means algorithm?</span></span> <span data-ttu-id="2be48-132">答案取决于许多因素，例如数据的结构。</span><span class="sxs-lookup"><span data-stu-id="2be48-132">The answer depends on many factors such as the structure of the data.</span></span> <span data-ttu-id="2be48-133">找到该数字需要尝试不同的 k 值，然后通过评估性能来确定最佳值。</span><span class="sxs-lookup"><span data-stu-id="2be48-133">Finding that number would require experimenting with different values for k and then evaluating performance to determine which value is best.</span></span> <span data-ttu-id="2be48-134">调整这些参数以找到最佳模型的做法称为超参数调整。</span><span class="sxs-lookup"><span data-stu-id="2be48-134">The practice of tuning these parameters to find an optimal model is known as hyper-parameter tuning.</span></span>

## <a name="choose-a-different-algorithm"></a><span data-ttu-id="2be48-135">选择其他算法</span><span class="sxs-lookup"><span data-stu-id="2be48-135">Choose a different algorithm</span></span>

<span data-ttu-id="2be48-136">回归和分类等机器学习任务包含各种算法实现。</span><span class="sxs-lookup"><span data-stu-id="2be48-136">Machine learning tasks like regression and classification contain various algorithm implementations.</span></span> <span data-ttu-id="2be48-137">可能出现尝试解决的问题和数据的构造方式与当前算法不能很好地匹配的情况。</span><span class="sxs-lookup"><span data-stu-id="2be48-137">It may be the case that the problem you are trying to solve and the way your data is structured does not fit well into the current algorithm.</span></span> <span data-ttu-id="2be48-138">在此类情况下，请考虑为任务使用其他算法，查看它是否能够从数据中更好地学习。</span><span class="sxs-lookup"><span data-stu-id="2be48-138">In such case, consider using a different algorithm for your task to see if it learns better from your data.</span></span>

<span data-ttu-id="2be48-139">以下链接提供[有关如何选择算法的更多指导](../how-to-choose-an-ml-net-algorithm.md)。</span><span class="sxs-lookup"><span data-stu-id="2be48-139">The following link provides more [guidance on which algorithm to choose](../how-to-choose-an-ml-net-algorithm.md).</span></span>
