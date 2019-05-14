---
title: ML.NET 操作指南
description: 了解如何执行特定任务，以帮助自定义创建 AI 解决方案并将机器学习集成到 .NET 应用程序。
ms.custom: seodec18
ms.date: 03/01/2019
ms.openlocfilehash: 83188e65ccd02e6928cb4b87577105a75ee96245
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649150"
---
# <a name="net-machine-learning-how-to-guides"></a><span data-ttu-id="8a7f3-103">.NET 机器学习操作指南</span><span class="sxs-lookup"><span data-stu-id="8a7f3-103">.NET Machine learning how-to guides</span></span> 

<span data-ttu-id="8a7f3-104">在 ML.NET 指南中的操作指南部分快速了解常见问题的答案。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="8a7f3-105">在某些情况下，可能会在多个部分列出相关文章以便查找。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="8a7f3-106">加载数据</span><span class="sxs-lookup"><span data-stu-id="8a7f3-106">Load the data</span></span>

* [<span data-ttu-id="8a7f3-107">从 CSV 文件中加载包含多个列的数据，以便进行机器学习处理。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-107">Load data with many columns from a CSV file for machine learning processing.</span></span>](load-data-from-mult-column-csv-ml-net.md)

* [<span data-ttu-id="8a7f3-108">从多个文件加载数据用于机器学习处理。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-108">Load data from multiple files for machine learning processing.</span></span>](load-data-from-multiple-files-ml-net.md)

* [<span data-ttu-id="8a7f3-109">从文本文件加载数据用于机器学习处理。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-109">Load data from a text file for machine learning processing.</span></span>](load-data-from-text-file-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="8a7f3-110">准备数据</span><span class="sxs-lookup"><span data-stu-id="8a7f3-110">Prepare the data</span></span>

* [<span data-ttu-id="8a7f3-111">使用规范化程序来预处理要在数据处理过程中使用的定型数据。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-111">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="8a7f3-112">定型模型</span><span class="sxs-lookup"><span data-stu-id="8a7f3-112">Train the model</span></span>

* [<span data-ttu-id="8a7f3-113">使用非文本文件数据定型机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-113">Train a machine learning model with data that's not in a text file.</span></span>](load-non-file-training-data-ml-net.md)

* [<span data-ttu-id="8a7f3-114">使用交叉验证来定型机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-114">Train a machine learning model using cross-validation.</span></span>](train-cross-validation-ml-net.md)

* [<span data-ttu-id="8a7f3-115">使用 ML.NET 定型回归模型来预测某个值。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-115">Train a regression model to predict a value using ML.NET.</span></span>](train-regression-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="8a7f3-116">评估模型质量</span><span class="sxs-lookup"><span data-stu-id="8a7f3-116">Evaluate the model quality</span></span>

* [<span data-ttu-id="8a7f3-117">计算指标来评估模型质量。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-117">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="8a7f3-118">模型可解释性</span><span class="sxs-lookup"><span data-stu-id="8a7f3-118">Model explainability</span></span>

* [<span data-ttu-id="8a7f3-119">使用排列特征的重要性来确定模型特征的重要性。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-119">Determine the feature importance of models with Permutation Feature Importance.</span></span>](determine-global-feature-importance-in-model.md)

* [<span data-ttu-id="8a7f3-120">使用广义加性模型和形状函数来解释模型。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-120">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

### <a name="feature-engineering"></a><span data-ttu-id="8a7f3-121">特征工程</span><span class="sxs-lookup"><span data-stu-id="8a7f3-121">Feature engineering</span></span>

* [<span data-ttu-id="8a7f3-122">应用特征工程学来进行分类数据模型定型。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-122">Apply feature engineering for model training on categorical data.</span></span>](train-model-categorical-ml-net.md)

* [<span data-ttu-id="8a7f3-123">使用 ML.NET 应用特征工程学来进行文本数据模型定型。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-123">Apply feature engineering for model training on textual data with ML.NET.</span></span>](train-model-textual-ml-net.md)

## <a name="run"></a><span data-ttu-id="8a7f3-124">运行</span><span class="sxs-lookup"><span data-stu-id="8a7f3-124">Run</span></span>

* [<span data-ttu-id="8a7f3-125">在 ML.NET 管道处理期间检查中间数据值。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-125">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="8a7f3-126">在应用程序中操作定型的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-126">Operationalize a trained machine learning model in apps.</span></span>](consuming-model-ml-net.md)

* [<span data-ttu-id="8a7f3-127">使用 PredictionFunction 一次执行一个预测。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-127">Use the PredictionFunction to make one prediction at a time.</span></span>](single-predict-model-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="8a7f3-128">概率 (Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="8a7f3-128">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="8a7f3-129">使用 Infer.NET 和概率性编程创建游戏匹配列表。</span><span class="sxs-lookup"><span data-stu-id="8a7f3-129">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)