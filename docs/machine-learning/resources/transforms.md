---
title: 数据转换
description: 了解在 ML.NET 中受支持的特征工程组件。
author: natke
ms.author: nakersha
ms.date: 04/02/2019
ms.openlocfilehash: 7ea06e19b4651017079a6ae57136f033e0ce981c
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "65558018"
---
# <a name="data-transformations"></a><span data-ttu-id="1d5cd-103">数据转换</span><span class="sxs-lookup"><span data-stu-id="1d5cd-103">Data transformations</span></span>

<span data-ttu-id="1d5cd-104">数据转换用于为定型模型准备数据。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-104">Data transformations are used to prepare data for model training.</span></span> <span data-ttu-id="1d5cd-105">本指南中的数据转换返回实现 [IEstimator](xref:Microsoft.ML.IEstimator%601) 接口的类。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-105">The transformations in this guide return classes that implement the [IEstimator](xref:Microsoft.ML.IEstimator%601) interface.</span></span> <span data-ttu-id="1d5cd-106">数据转换可以链接在一起。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-106">Data transformations can be chained together.</span></span> <span data-ttu-id="1d5cd-107">每个数据转换都需要获取并生成特定类型和格式的数据，链接的参考文档中规定了具体类型和格式。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-107">Each transformation both expects and produces data of specific types and formats, which are specified in the linked reference documentation.</span></span>

<span data-ttu-id="1d5cd-108">一些数据转换需要通过定型数据来计算参数。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-108">Some data transformations require training data to calculate their parameters.</span></span> <span data-ttu-id="1d5cd-109">例如，<xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> 转换器计算 `Fit()` 操作期间定型数据的平均值和方差，并在 `Transform()` 操作中使用这些参数。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-109">For example: the <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> transformer calculates the mean and variance of the training data during the `Fit()` operation, and uses those parameters in the `Transform()` operation.</span></span> 

<span data-ttu-id="1d5cd-110">另一些数据转换不需要定型数据。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-110">Other data transformations don't require training data.</span></span> <span data-ttu-id="1d5cd-111">例如，<xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> 转换可以执行 `Transform()` 操作，而无需在 `Fit()` 操作期间看到任何定型数据。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-111">For example: the <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> transformation can perform the `Transform()` operation without having seen any training data during the `Fit()` operation.</span></span>

## <a name="column-mapping-and-grouping"></a><span data-ttu-id="1d5cd-112">列映射和分组</span><span class="sxs-lookup"><span data-stu-id="1d5cd-112">Column mapping and grouping</span></span>

| <span data-ttu-id="1d5cd-113">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-113">Transform</span></span> | <span data-ttu-id="1d5cd-114">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-114">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | <span data-ttu-id="1d5cd-115">将一个或多个输入列连接到新输出列中</span><span class="sxs-lookup"><span data-stu-id="1d5cd-115">Concatenate one or more input columns into a new output column</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | <span data-ttu-id="1d5cd-116">复制和重命名一个或多个输入列</span><span class="sxs-lookup"><span data-stu-id="1d5cd-116">Copy and rename one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | <span data-ttu-id="1d5cd-117">删除一个或多个输入列</span><span class="sxs-lookup"><span data-stu-id="1d5cd-117">Drop one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | <span data-ttu-id="1d5cd-118">选择一个或多个不包含输入数据的列</span><span class="sxs-lookup"><span data-stu-id="1d5cd-118">Select one or more columns to keep from the input data</span></span> |

## <a name="normalization-and-scaling"></a><span data-ttu-id="1d5cd-119">规范化和缩放</span><span class="sxs-lookup"><span data-stu-id="1d5cd-119">Normalization and scaling</span></span>

| <span data-ttu-id="1d5cd-120">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-120">Transform</span></span> | <span data-ttu-id="1d5cd-121">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-121">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | <span data-ttu-id="1d5cd-122">减去（定型数据的）平均值，再除以（定型数据的）方差</span><span class="sxs-lookup"><span data-stu-id="1d5cd-122">Subtract the mean (of the training data) and divide by the variance (of the training data)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | <span data-ttu-id="1d5cd-123">根据定型数据的对数进行规范化</span><span class="sxs-lookup"><span data-stu-id="1d5cd-123">Normalize based on the logarithm of the training data</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | <span data-ttu-id="1d5cd-124">按 [lp 范数](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions)缩放输入向量，其中 p 为 1、2 或无穷大。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-124">Scale input vectors by their [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), where p is 1, 2 or infinity.</span></span> <span data-ttu-id="1d5cd-125">默认为 l2（欧几里得距离）范数</span><span class="sxs-lookup"><span data-stu-id="1d5cd-125">Defaults to the l2 (Euclidean distance) norm</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | <span data-ttu-id="1d5cd-126">缩放行中的每个值，具体方法是减去行数据的平均值，除以（行数据的）标准差或 l2 范数，再乘以可配置的比例因子（默认值为 2）</span><span class="sxs-lookup"><span data-stu-id="1d5cd-126">Scale each value in a row by subtracting the mean of the row data and divide by either the standard deviation or l2-norm (of the row data), and multiply by a configurable scale factor (default 2)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | <span data-ttu-id="1d5cd-127">将输入值分配到箱索引，并除以箱数量，以生成介于 0 和 1 之间的浮点值。</span><span class="sxs-lookup"><span data-stu-id="1d5cd-127">Assign the input value to a bin index and divide by the number of bins to produce a float value between 0 and 1.</span></span> <span data-ttu-id="1d5cd-128">计算箱边界是为了在各个箱中均匀分布定型数据</span><span class="sxs-lookup"><span data-stu-id="1d5cd-128">The bin boundaries are calculated to evenly distribute the training data across bins</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | <span data-ttu-id="1d5cd-129">根据与标签列的相关性，将输入值分配到箱</span><span class="sxs-lookup"><span data-stu-id="1d5cd-129">Assign the input value to a bin based on its correlation with label column</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | <span data-ttu-id="1d5cd-130">按定型数据最小值和最大值的差值缩放输入</span><span class="sxs-lookup"><span data-stu-id="1d5cd-130">Scale the input by the difference between the minimum and maximum values in the training data</span></span> |

## <a name="conversions-between-data-types"></a><span data-ttu-id="1d5cd-131">数据类型转换</span><span class="sxs-lookup"><span data-stu-id="1d5cd-131">Conversions between data types</span></span>

| <span data-ttu-id="1d5cd-132">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-132">Transform</span></span> | <span data-ttu-id="1d5cd-133">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-133">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | <span data-ttu-id="1d5cd-134">将输入列的类型转换为新类型</span><span class="sxs-lookup"><span data-stu-id="1d5cd-134">Convert the type of an input column to a new type</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue*> | <span data-ttu-id="1d5cd-135">根据提供的映射字典将值映射到键（类别）</span><span class="sxs-lookup"><span data-stu-id="1d5cd-135">Map values to keys (categories) based on the supplied dictionary of mappings</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*> | <span data-ttu-id="1d5cd-136">通过从输入数据创建映射，将值映射到键（类别）</span><span class="sxs-lookup"><span data-stu-id="1d5cd-136">Map values to keys (categories) by creating the mapping from the input data</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue*> | <span data-ttu-id="1d5cd-137">将键转换回原始值</span><span class="sxs-lookup"><span data-stu-id="1d5cd-137">Convert keys back to their original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector*> | <span data-ttu-id="1d5cd-138">将键转换回原始值的向量</span><span class="sxs-lookup"><span data-stu-id="1d5cd-138">Convert keys back to vectors of original values</span></span> |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector*> | <span data-ttu-id="1d5cd-139">将键转换回原始值的二元向量</span><span class="sxs-lookup"><span data-stu-id="1d5cd-139">Convert keys back to a binary vector of original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash*> | <span data-ttu-id="1d5cd-140">哈希处理输入列中的值</span><span class="sxs-lookup"><span data-stu-id="1d5cd-140">Hash the value in the input column</span></span> |

## <a name="text-transformations"></a><span data-ttu-id="1d5cd-141">文本转换</span><span class="sxs-lookup"><span data-stu-id="1d5cd-141">Text transformations</span></span>

| <span data-ttu-id="1d5cd-142">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-142">Transform</span></span> | <span data-ttu-id="1d5cd-143">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-143">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText*> | <span data-ttu-id="1d5cd-144">将文本列转换为规范化 ngram 和 char-gram 计数的浮点数组</span><span class="sxs-lookup"><span data-stu-id="1d5cd-144">Transform a text column into a float array of normalized ngrams and char-grams counts</span></span> | 
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords*> | <span data-ttu-id="1d5cd-145">将一个或多个文本列拆分为各个字词</span><span class="sxs-lookup"><span data-stu-id="1d5cd-145">Split one or more text columns into individual words</span></span> |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys*> | <span data-ttu-id="1d5cd-146">将一个或多个文本列拆分为关于一组主题的各个字符浮点数</span><span class="sxs-lookup"><span data-stu-id="1d5cd-146">Split one or more text columns into individual characters floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.NormalizeText*> | <span data-ttu-id="1d5cd-147">更改大小写，删除标注字符、标点符号和数字</span><span class="sxs-lookup"><span data-stu-id="1d5cd-147">Change case, remove diacritical marks, punctuation marks and numbers</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams*> | <span data-ttu-id="1d5cd-148">将文本列转换为一组 ngram 计数（连续单词的序列）</span><span class="sxs-lookup"><span data-stu-id="1d5cd-148">Transform text column into a bag of counts of ngrams (sequences of consecutive words)</span></span>|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags*> | <span data-ttu-id="1d5cd-149">将文本列转换为一组 ngram 向量计数</span><span class="sxs-lookup"><span data-stu-id="1d5cd-149">Transform text column into a bag of counts of ngrams vector</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams*> | <span data-ttu-id="1d5cd-150">将文本列转换为已哈希处理的 ngram 计数向量</span><span class="sxs-lookup"><span data-stu-id="1d5cd-150">Transform text column into a vector of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags*> | <span data-ttu-id="1d5cd-151">将文本列转换为一组已哈希处理的 ngram 计数</span><span class="sxs-lookup"><span data-stu-id="1d5cd-151">Transform text column into a bag of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords*>  | <span data-ttu-id="1d5cd-152">从输入列中删除指定语言的默认停用词</span><span class="sxs-lookup"><span data-stu-id="1d5cd-152">Remove default stop words for the specified language from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords*> | <span data-ttu-id="1d5cd-153">从输入列中删除指定的停用词</span><span class="sxs-lookup"><span data-stu-id="1d5cd-153">Removes specified stop words from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation*> | <span data-ttu-id="1d5cd-154">将文档（表示为浮点数向量）转换为关于一组主题的浮点数向量</span><span class="sxs-lookup"><span data-stu-id="1d5cd-154">Transform a document (represented as a vector of floats) into a vector of floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding*> | <span data-ttu-id="1d5cd-155">使用预定型模型将文本令牌向量转换为句向量</span><span class="sxs-lookup"><span data-stu-id="1d5cd-155">Convert vectors of text tokens into sentence vectors using a pre-trained model</span></span> |

## <a name="image-transformations"></a><span data-ttu-id="1d5cd-156">图像转换</span><span class="sxs-lookup"><span data-stu-id="1d5cd-156">Image transformations</span></span>

| <span data-ttu-id="1d5cd-157">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-157">Transform</span></span> | <span data-ttu-id="1d5cd-158">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-158">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> | <span data-ttu-id="1d5cd-159">将图像转换为灰度图像</span><span class="sxs-lookup"><span data-stu-id="1d5cd-159">Convert an image to grayscale</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage*> | <span data-ttu-id="1d5cd-160">将像素向量转换为 <xref:Microsoft.ML.Transforms.Image.ImageDataViewType></span><span class="sxs-lookup"><span data-stu-id="1d5cd-160">Convert a vector of pixels to <xref:Microsoft.ML.Transforms.Image.ImageDataViewType></span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*> | <span data-ttu-id="1d5cd-161">将输入图像中的像素转换为数字向量</span><span class="sxs-lookup"><span data-stu-id="1d5cd-161">Convert pixels from input image into a vector of numbers</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*> | <span data-ttu-id="1d5cd-162">将图像从文件夹加载到内存中</span><span class="sxs-lookup"><span data-stu-id="1d5cd-162">Load images from a folder into memory</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*> | <span data-ttu-id="1d5cd-163">调整图像大小</span><span class="sxs-lookup"><span data-stu-id="1d5cd-163">Resize images</span></span> |

## <a name="categorical-data-transformations"></a><span data-ttu-id="1d5cd-164">分类数据转换</span><span class="sxs-lookup"><span data-stu-id="1d5cd-164">Categorical data transformations</span></span>

| <span data-ttu-id="1d5cd-165">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-165">Transform</span></span> | <span data-ttu-id="1d5cd-166">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-166">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*> | <span data-ttu-id="1d5cd-167">将一个或多个文本列转换为[单热](https://en.wikipedia.org/wiki/One-hot)编码向量</span><span class="sxs-lookup"><span data-stu-id="1d5cd-167">Convert one or more text columns into [one-hot](https://en.wikipedia.org/wiki/One-hot) encoded vectors</span></span> |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding*> | <span data-ttu-id="1d5cd-168">将一个或多个文本列转换为基于哈希的单热编码向量</span><span class="sxs-lookup"><span data-stu-id="1d5cd-168">Convert one more text columns into hash-based one-hot encoded vectors</span></span> |

## <a name="missing-values"></a><span data-ttu-id="1d5cd-169">缺失值</span><span class="sxs-lookup"><span data-stu-id="1d5cd-169">Missing values</span></span>

| <span data-ttu-id="1d5cd-170">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-170">Transform</span></span> | <span data-ttu-id="1d5cd-171">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-171">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues*> | <span data-ttu-id="1d5cd-172">新建布尔输出列：如果输入列中缺少值，输出列的值为 true</span><span class="sxs-lookup"><span data-stu-id="1d5cd-172">Create a new boolean output column, the value of which is true when the value in the input column is missing</span></span> |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*> | <span data-ttu-id="1d5cd-173">新建输出列：如果输入列中缺少值，输出列的值设置为默认值，否则设置为输入值</span><span class="sxs-lookup"><span data-stu-id="1d5cd-173">Create a new output column, the value of which is set to a default value if the value is missing from the input column, and the input value otherwise</span></span> |

## <a name="feature-selection"></a><span data-ttu-id="1d5cd-174">功能选择</span><span class="sxs-lookup"><span data-stu-id="1d5cd-174">Feature selection</span></span>

| <span data-ttu-id="1d5cd-175">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-175">Transform</span></span> | <span data-ttu-id="1d5cd-176">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-176">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount*> | <span data-ttu-id="1d5cd-177">选择非默认值大于阈值的功能</span><span class="sxs-lookup"><span data-stu-id="1d5cd-177">Select features whose non-default values are greater than a threshold</span></span> |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation*> | <span data-ttu-id="1d5cd-178">选择标签列中的数据最依赖的功能</span><span class="sxs-lookup"><span data-stu-id="1d5cd-178">Select the features on which the data in the label column is most dependent</span></span> |

## <a name="custom-transformations"></a><span data-ttu-id="1d5cd-179">自定义转换</span><span class="sxs-lookup"><span data-stu-id="1d5cd-179">Custom transformations</span></span>

| <span data-ttu-id="1d5cd-180">Transform</span><span class="sxs-lookup"><span data-stu-id="1d5cd-180">Transform</span></span> | <span data-ttu-id="1d5cd-181">定义</span><span class="sxs-lookup"><span data-stu-id="1d5cd-181">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping*> | <span data-ttu-id="1d5cd-182">使用用户定义映射将现有列转换为新列</span><span class="sxs-lookup"><span data-stu-id="1d5cd-182">Transform existing columns onto new ones with a user-defined mapping</span></span> |
