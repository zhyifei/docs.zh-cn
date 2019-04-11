---
title: .NET 机器学习操作指南 - ML.NET
description: 了解如何执行特定任务，以帮助自定义创建 AI 解决方案并将机器学习集成到 .NET 应用程序。
ms.custom: seodec18
ms.date: 03/01/2019
ms.openlocfilehash: c8d1258629f777cd8bced47e4b956c9cf100a682
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427545"
---
# <a name="net-machine-learning-how-to-guides---mlnet"></a><span data-ttu-id="add8c-103">.NET 机器学习操作指南 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="add8c-103">.NET Machine learning how-to guides - ML.NET</span></span>

<span data-ttu-id="add8c-104">在 ML.NET 指南中的操作指南部分快速了解常见问题的答案。</span><span class="sxs-lookup"><span data-stu-id="add8c-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="add8c-105">在某些情况下，可能会在多个部分列出相关文章以便查找。</span><span class="sxs-lookup"><span data-stu-id="add8c-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="add8c-106">加载数据</span><span class="sxs-lookup"><span data-stu-id="add8c-106">Load the data</span></span>

* [<span data-ttu-id="add8c-107">从 CSV 文件中加载包含多个列的数据，以便进行机器学习处理。</span><span class="sxs-lookup"><span data-stu-id="add8c-107">Load data with many columns from a CSV file for machine learning processing.</span></span>](load-data-from-mult-column-csv-ml-net.md)

* [<span data-ttu-id="add8c-108">从多个文件加载数据以便进行机器学习处理。</span><span class="sxs-lookup"><span data-stu-id="add8c-108">Load data from multiple files for machine learning processing.</span></span>](load-data-from-multiple-files-ml-net.md)

* [<span data-ttu-id="add8c-109">从文本文件加载数据以便进行机器学习处理。</span><span class="sxs-lookup"><span data-stu-id="add8c-109">Load data from a text file for machine learning processing.</span></span>](load-data-from-text-file-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="add8c-110">准备数据</span><span class="sxs-lookup"><span data-stu-id="add8c-110">Prepare the data</span></span>

* [<span data-ttu-id="add8c-111">使用规范化程序来预处理要在数据处理过程中使用的定型数据。</span><span class="sxs-lookup"><span data-stu-id="add8c-111">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="add8c-112">定型模型</span><span class="sxs-lookup"><span data-stu-id="add8c-112">Train the model</span></span>

* [<span data-ttu-id="add8c-113">使用非文本文件数据定型机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="add8c-113">Train a machine learning model with data that's not in a text file.</span></span>](load-non-file-training-data-ml-net.md)

* [<span data-ttu-id="add8c-114">使用交叉验证来定型机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="add8c-114">Train a machine learning model using cross-validation.</span></span>](train-cross-validation-ml-net.md)

* [<span data-ttu-id="add8c-115">使用 ML.NET 定型回归模型以预测某个值。</span><span class="sxs-lookup"><span data-stu-id="add8c-115">Train a regression model to predict a value using ML.NET.</span></span>](train-regression-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="add8c-116">评估模型质量</span><span class="sxs-lookup"><span data-stu-id="add8c-116">Evaluate the model quality</span></span>

* [<span data-ttu-id="add8c-117">计算指标来评估模型质量。</span><span class="sxs-lookup"><span data-stu-id="add8c-117">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="add8c-118">模型可解释性</span><span class="sxs-lookup"><span data-stu-id="add8c-118">Model explainability</span></span>

* [<span data-ttu-id="add8c-119">使用排列特征的重要性来确定模型特征的重要性。</span><span class="sxs-lookup"><span data-stu-id="add8c-119">Determine the feature importance of models with Permutation Feature Importance.</span></span>](determine-global-feature-importance-in-model.md)

* [<span data-ttu-id="add8c-120">使用广义加性模型和形状函数来解释模型。</span><span class="sxs-lookup"><span data-stu-id="add8c-120">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

### <a name="feature-engineering"></a><span data-ttu-id="add8c-121">特征工程</span><span class="sxs-lookup"><span data-stu-id="add8c-121">Feature engineering</span></span>

* [<span data-ttu-id="add8c-122">应用特征工程学来进行分类数据模型定型。</span><span class="sxs-lookup"><span data-stu-id="add8c-122">Apply feature engineering for model training on categorical data.</span></span>](train-model-categorical-ml-net.md)

* [<span data-ttu-id="add8c-123">使用 ML.NET 应用特征工程学来进行文本数据模型定型。</span><span class="sxs-lookup"><span data-stu-id="add8c-123">Apply feature engineering for model training on textual data with ML.NET.</span></span>](train-model-textual-ml-net.md)

## <a name="run"></a><span data-ttu-id="add8c-124">运行</span><span class="sxs-lookup"><span data-stu-id="add8c-124">Run</span></span>

* [<span data-ttu-id="add8c-125">在 ML.NET 管道处理期间检查中间数据值。</span><span class="sxs-lookup"><span data-stu-id="add8c-125">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="add8c-126">在应用中操作定型的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="add8c-126">Operationalize a trained machine learning model in apps.</span></span>](consuming-model-ml-net.md)

* [<span data-ttu-id="add8c-127">使用 PredictionFunction 一次执行一个预测。</span><span class="sxs-lookup"><span data-stu-id="add8c-127">Use the PredictionFunction to make one prediction at a time.</span></span>](single-predict-model-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="add8c-128">概率 (Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="add8c-128">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="add8c-129">使用 Infer.NET 和概率性编程创建游戏匹配列表应用。</span><span class="sxs-lookup"><span data-stu-id="add8c-129">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)