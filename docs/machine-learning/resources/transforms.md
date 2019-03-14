---
title: 机器学习数据转换 - ML.NET
description: 了解在 ML.NET 中受支持的特征工程组件。
author: JRAlexander
ms.custom: seodec18
ms.date: 01/14/2019
ms.openlocfilehash: e649c9a27f0409cb9cdfb554963b5c0e732991f2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355399"
---
# <a name="machine-learning-data-transforms---mlnet"></a><span data-ttu-id="ab5b6-103">机器学习数据转换 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="ab5b6-103">Machine learning data transforms - ML.NET</span></span>

<span data-ttu-id="ab5b6-104">下表包含在 ML.NET 中受支持的数据转换的所有信息。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-104">The following tables contain information about all of the data transforms supported in ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b6-105">ML.NET 当前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-105">ML.NET is currently in Preview.</span></span> <span data-ttu-id="ab5b6-106">当前并不支持所有数据转换。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-106">Not all data transforms are currently supported.</span></span> <span data-ttu-id="ab5b6-107">要提交某项转换请求，请在 [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues) GitHub 存储库中发起一个问题。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-107">To submit a request for a certain transform, open an issue in the [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues) GitHub repository.</span></span>

## <a name="combiners-and-segregators"></a><span data-ttu-id="ab5b6-108">合并器和分离器</span><span class="sxs-lookup"><span data-stu-id="ab5b6-108">Combiners and segregators</span></span>

| <span data-ttu-id="ab5b6-109">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-109">Transform</span></span> | <span data-ttu-id="ab5b6-110">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-110">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.GroupTransform> | <span data-ttu-id="ab5b6-111">根据相邻的组 ID，将标量列的值汇集到矢量中。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-111">Groups values of a scalar column into a vector based on a contiguous group ID.</span></span> |
| <xref:Microsoft.ML.Transforms.UngroupTransform> | <span data-ttu-id="ab5b6-112">将矢量列取消组合为一系列行；组转换的逆向。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-112">Un-groups vector columns into sequences of rows, inverse of Group transform.</span></span> |

## <a name="conversions"></a><span data-ttu-id="ab5b6-113">转换</span><span class="sxs-lookup"><span data-stu-id="ab5b6-113">Conversions</span></span>

| <span data-ttu-id="ab5b6-114">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-114">Transform</span></span> | <span data-ttu-id="ab5b6-115">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-115">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Conversions.HashingTransformer> | <span data-ttu-id="ab5b6-116">哈希为单值列或矢量列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-116">Hashes either single valued columns or vector columns.</span></span> <span data-ttu-id="ab5b6-117">对于矢量列，它分别散列每个槽。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-117">For vector columns, it hashes each slot separately.</span></span> <span data-ttu-id="ab5b6-118">它可以散列文本值或键值。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-118">It can hash either text values or key values.</span></span> |
| <xref:Microsoft.ML.Transforms.Conversions.HashJoiningTransform> | <span data-ttu-id="ab5b6-119">将多个列值转换为哈希。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-119">Converts multiple column values into hashes.</span></span> <span data-ttu-id="ab5b6-120">此转换接受数字和文本输入，包括单值和矢量值列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-120">This transform accepts both numeric and text inputs, both single and vector-valued columns.</span></span> |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToBinaryVectorMappingTransformer> | <span data-ttu-id="ab5b6-121">将键转换为二进制矢量列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-121">Converts a key to a binary vector column.</span></span> |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToValueMappingTransformer > | <span data-ttu-id="ab5b6-122">利用 KeyValues 元数据将键索引映射到 KeyValues 元数据中的相应值。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-122">Utilizes KeyValues metadata to map key indices to the corresponding values in the KeyValues metadata.</span></span> |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToVectorMappingTransformer> | <span data-ttu-id="ab5b6-123">将键转换为矢量列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-123">Converts a key to a vector column.</span></span> |
| <xref:Microsoft.ML.Transforms.Conversions.TypeConvertingTransformer> | <span data-ttu-id="ab5b6-124">如果可以转换类型，则更改基础列类型。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-124">Changes underlying column type provided the type can be converted.</span></span> |
| <xref:Microsoft.ML.Transforms.Conversions.ValueToKeyMappingTransformer> | <span data-ttu-id="ab5b6-125">将输入值（单词、数字等）转换为字典中的索引。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-125">Converts input values (words, numbers, etc.) to index in a dictionary.</span></span> |

## <a name="deep-learning"></a><span data-ttu-id="ab5b6-126">深度学习</span><span class="sxs-lookup"><span data-stu-id="ab5b6-126">Deep learning</span></span>

| <span data-ttu-id="ab5b6-127">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-127">Transform</span></span> | <span data-ttu-id="ab5b6-128">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-128">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | <span data-ttu-id="ab5b6-129">为现有 ONNX 模型提供数据并返回分数（预测）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-129">Provides data to an existing ONNX model and returns the score (prediction).</span></span> |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | <span data-ttu-id="ab5b6-130">可以使用预定型的 TensorFlow 模型进行评分或重新定型 TensorFlow 模型。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-130">Can either score with pretrained TensorFlow model or retrain TensorFlow model.</span></span> |

## <a name="feature-extraction"></a><span data-ttu-id="ab5b6-131">特征提取</span><span class="sxs-lookup"><span data-stu-id="ab5b6-131">Feature extraction</span></span>

| <span data-ttu-id="ab5b6-132">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-132">Transform</span></span> | <span data-ttu-id="ab5b6-133">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-133">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.CustomStopWordsRemovingTransform> | <span data-ttu-id="ab5b6-134">通过将单个令牌（比较不区分大小写）与非索引字进行比较，删除指定的非索引字列表。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-134">Removes specified list of stop words by comparing individual tokens (case-insensitive comparison) to the stopwords.</span></span>|
| <xref:Microsoft.ML.ImageAnalytics.ImageGrayscaleTransform> | <span data-ttu-id="ab5b6-135">获取一个或多个 ImageType 列，并将其转换为同一图像的灰度表示形式。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-135">Takes one or more ImageType columns and converts them to a grayscale representation of the same image.</span></span>|
| <xref:Microsoft.ML.ImageAnalytics.ImageLoaderTransform> | <span data-ttu-id="ab5b6-136">获取一个或多个 ReadOnlyMemory 列，并将其作为 ImageType 加载。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-136">Takes one or more ReadOnlyMemory columns and loads them as an ImageType.</span></span> |
| <xref:Microsoft.ML.ImageAnalytics.ImagePixelExtractorTransform> | <span data-ttu-id="ab5b6-137">获取一个或多个 ImageType 列，并将其转换为矢量表示形式。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-137">Takes one or more ImageType columns and converts them into a vector representation.</span></span>|
| <xref:Microsoft.ML.ImageAnalytics.ImageResizerTransform> | <span data-ttu-id="ab5b6-138">采用一个或多个 ImageType 列，并将其大小调整为提供的高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-138">Takes one or more ImageType columns and resizes them to  the provided height and width.</span></span>|
| <xref:Microsoft.ML.Transforms.Text.LatentDirichletAllocationTransformer> | <span data-ttu-id="ab5b6-139">实现 LightLDA，这是潜在狄利克雷分布的最先进的实现。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-139">Implements LightLDA, a state-of-the-art implementation of Latent Dirichlet Allocation.</span></span>|
| <xref:Microsoft.ML.Transforms.LoadTransform> | <span data-ttu-id="ab5b6-140">从指定的模型文件加载特定转换。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-140">Loads specific transforms from the specified model file.</span></span> <span data-ttu-id="ab5b6-141">允许从序列化链中挑选转换，或将预定型的转换应用于不同（但仍然符合）的数据视图。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-141">Allows for 'cherry picking' transforms from a serialized chain, or to apply a pre-trained transform to a different (but still compatible) data view.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractingTransformer> | <span data-ttu-id="ab5b6-142">在给定的键矢量中生成一组 ngrams 计数（长度为 1-n 的连续值的序列）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-142">Produces a bag of counts of ngrams (sequences of consecutive values of length 1-n) in a given vector of keys.</span></span> <span data-ttu-id="ab5b6-143">它通过生成 ngram 字典并使用字典中的 ID 作为包中的索引来实现。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-143">It does so by building a dictionary of ngrams and using the id in the dictionary as the index in the bag.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractorTransform> | <span data-ttu-id="ab5b6-144">将标记化文本（ReadOnlyMemory 的矢量）或键矢量的集合转换为数字特征矢量。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-144">Turns a collection of tokenized text (vector of ReadOnlyMemory), or vectors of keys into numerical feature vectors.</span></span> <span data-ttu-id="ab5b6-145">特征矢量是 ngrams 的计数（长度为 1-n 的连续令牌、单词或键的序列）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-145">The feature vectors are counts of ngrams (sequences of consecutive tokens -words or keys- of length 1-n).</span></span> |
| <xref:Microsoft.ML.Transforms.Text.NgramHashExtractingTransformer> | <span data-ttu-id="ab5b6-146">使用哈希代码将标记化文本（ReadOnlyMemory 的矢量）集合转换为数字特征矢量。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-146">Turns a collection of tokenized text (vector of ReadOnlyMemory) into numerical feature vectors using hashing.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.NgramHashingTransformer> | <span data-ttu-id="ab5b6-147">在给定的文本中生成一组 ngrams 计数（长度为 1-n 的连续单词的序列）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-147">Produces a bag of counts of ngrams (sequences of consecutive words of length 1-n) in a given text.</span></span> |
| <xref:Microsoft.ML.Transforms.Categorical.OneHotEncodingTransformer> | <span data-ttu-id="ab5b6-148">通过基于数据生成类别字典并使用字典中的 ID 作为数组中的索引，将分类值转换为指标数组</span><span class="sxs-lookup"><span data-stu-id="ab5b6-148">Converts the categorical value into an indicator array by building a dictionary of categories based on the data and using the id in the dictionary as the index in the array</span></span> |
| <xref:Microsoft.ML.Transforms.Projections.PcaTransform> | <span data-ttu-id="ab5b6-149">计算特征矢量到低秩子空间的投影。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-149">Computes the projection of the feature vector onto a low-rank subspace.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.SentimentAnalyzingTransformer> | <span data-ttu-id="ab5b6-150">使用预先训练的情绪模型对输入字符串进行评分。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-150">Uses a pretrained sentiment model to score input strings.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.StopWordsRemovingTransformer> | <span data-ttu-id="ab5b6-151">通过将单个令牌（比较不区分大小写）与非索引字进行比较，以删除特定语言的非索引字列表（最常见的单词）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-151">Removes language-specific list of stop words (most common words) by comparing individual tokens (case-insensitive comparison) to the stopwords.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.WordBagBuildingTransformer> | <span data-ttu-id="ab5b6-152">在给定的文本中生成一组 ngrams 计数（连续单词的序列）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-152">Produces a bag of counts of ngrams (sequences of consecutive words) in a given text.</span></span> <span data-ttu-id="ab5b6-153">它通过生成 ngram 字典并使用字典中的 ID 作为包中的索引来实现。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-153">It does so by building a dictionary of ngrams and using the id in the dictionary as the index in the bag.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.WordHashBagProducingTransformer> | <span data-ttu-id="ab5b6-154">在给定的文本中生成一组 ngrams 计数（长度为 1-n 的连续单词的序列）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-154">Produces a bag of counts of ngrams (sequences of consecutive words of length 1-n) in a given text.</span></span> <span data-ttu-id="ab5b6-155">它通过散列每个 ngram 并使用哈希值作为包中的索引来实现。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-155">It does so by hashing each ngram and using the hash value as the index in the bag.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.WordTokenizingTransformer> | <span data-ttu-id="ab5b6-156">使用分隔符字符将文本拆分成单词。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-156">Splits the text into words using the separator character(s).</span></span> |


## <a name="image-model-featurizers"></a><span data-ttu-id="ab5b6-157">图像模型特征器</span><span class="sxs-lookup"><span data-stu-id="ab5b6-157">Image model featurizers</span></span>

| <span data-ttu-id="ab5b6-158">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-158">Transform</span></span> | <span data-ttu-id="ab5b6-159">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-159">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.AlexNetExtension> | <span data-ttu-id="ab5b6-160">这是与 <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> 一起使用的扩展方法，以便使用预定型的 [AlexNet](https://en.wikipedia.org/wiki/AlexNet) 模型。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-160">This is an extension method to be used with the <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> in order to use a pretrained [AlexNet](https://en.wikipedia.org/wiki/AlexNet) model.</span></span> <span data-ttu-id="ab5b6-161">包含此扩展的 NuGet 还保证包含二进制模型文件。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-161">The NuGet containing this extension is also guaranteed to include the binary model file.</span></span> |
| <xref:Microsoft.ML.Transforms.ResNet18Extension> | <span data-ttu-id="ab5b6-162">这是与 <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> 一起使用的扩展方法，以使用预定型的 ResNet18 模型。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-162">This is an extension method to be used with the <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> to use a pretrained ResNet18 model.</span></span> <span data-ttu-id="ab5b6-163">包含此扩展的 NuGet 还保证包含二进制模型文件。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-163">The NuGet containing this extension is also guaranteed to include the binary model file.</span></span> |
| <xref:Microsoft.ML.Transforms.ResNet50Extension> | <span data-ttu-id="ab5b6-164">这是与 <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> 一起使用的扩展方法，以使用预定型的 ResNet50 模型。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-164">This is an extension method to be used with the <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> to use a pretrained ResNet50model.</span></span> <span data-ttu-id="ab5b6-165">包含此扩展的 NuGet 还保证包含二进制模型文件。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-165">The NuGet containing this extension is also guaranteed to include the binary model file.</span></span> |
| <xref:Microsoft.ML.Transforms.ResNet101Extension> | <span data-ttu-id="ab5b6-166">这是与 <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> 一起使用的扩展方法，以使用预定型的 ResNet101 模型。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-166">This is an extension method to be used with the <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> to use a pretrained ResNet101 model.</span></span> <span data-ttu-id="ab5b6-167">包含此扩展的 NuGet 还保证包含二进制模型文件。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-167">The NuGet containing this extension is also guaranteed to include the binary model file.</span></span> |

## <a name="label-parsing"></a><span data-ttu-id="ab5b6-168">标签分析</span><span class="sxs-lookup"><span data-stu-id="ab5b6-168">Label parsing</span></span>

| <span data-ttu-id="ab5b6-169">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-169">Transform</span></span> | <span data-ttu-id="ab5b6-170">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-170">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.LabelConvertTransform> |  <span data-ttu-id="ab5b6-171">转换标签。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-171">Converts labels.</span></span> |
| <xref:Microsoft.ML.Transforms.LabelIndicatorTransform> | <span data-ttu-id="ab5b6-172">将多类标签重新映射为二进制 True、False 标签，主要用于 OVA。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-172">Remaps multiclass labels to binary True, False labels, primarily for use with OVA.</span></span>|

## <a name="missing-values"></a><span data-ttu-id="ab5b6-173">缺失值</span><span class="sxs-lookup"><span data-stu-id="ab5b6-173">Missing values</span></span>

| <span data-ttu-id="ab5b6-174">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-174">Transform</span></span> | <span data-ttu-id="ab5b6-175">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-175">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueDroppingTransformer> | <span data-ttu-id="ab5b6-176">删除列中的缺失值。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-176">Drops missing values from columns.</span></span> |
| <xref:Microsoft.ML.Transforms.MissingValueIndicatorTransform> | <span data-ttu-id="ab5b6-177">创建一个布尔值输出列，其槽数与输入列相同，如果缺少输入列中的值，则输出值为 true。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-177">Creates a boolean output column with the same number of slots as the input column, where the output value is true if the value in the input column is missing.</span></span> |
| <xref:Microsoft.ML.Transforms.MissingValueReplacingTransformer> | <span data-ttu-id="ab5b6-178">通过将缺失值替换为默认值或平均值/最小值/最大值（仅适用于非文本列）来处理缺失值。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-178">Handle missing values by replacing them with either the default value or the mean/min/max value (for non-text columns only).</span></span> |

## <a name="normalization"></a><span data-ttu-id="ab5b6-179">标准化</span><span class="sxs-lookup"><span data-stu-id="ab5b6-179">Normalization</span></span>

| <span data-ttu-id="ab5b6-180">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-180">Transform</span></span> | <span data-ttu-id="ab5b6-181">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-181">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Projections.LpNormalizingTransformer> | <span data-ttu-id="ab5b6-182">Lp-Norm（矢量/行式）标准化转换。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-182">Lp-Norm (vector/row-wise) normalization transform.</span></span> |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarDblAggregator> | <span data-ttu-id="ab5b6-183">计算矢量值列的均值和方差。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-183">Computes the mean and variance for a vector valued column.</span></span> <span data-ttu-id="ab5b6-184">它跟踪当前平均值和 M2（平均值的平方差的总和）、NaNs 的数量和非零元素的数量。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-184">It tracks the current mean and the M2 (sum of squared diffs of the values from the mean), the number of NaNs and the number of non-zero elements.</span></span> |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarSngAggregator> | <span data-ttu-id="ab5b6-185">计算矢量值列的均值和方差。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-185">Computes the mean and variance for a vector valued column.</span></span> <span data-ttu-id="ab5b6-186">它跟踪当前平均值和 M2（平均值的平方差的总和）、NaNs 的数量和非零元素的数量。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-186">It tracks the current mean and the M2 (sum of squared diffs of the values from the mean), the number of NaNs and the number of non-zero elements.</span></span> |
| <xref:Microsoft.ML.Transforms.Normalizers.MinMaxDblAggregator> | <span data-ttu-id="ab5b6-187">跟踪矢量值列的最小值、最大值、非稀疏值 (vCount) 和 ProcessValue() 调用 (trainCount) 的数量。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-187">Tracks min, max, number of non-sparse values (vCount) and number of ProcessValue() calls (trainCount) for a vector valued column.</span></span> |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizeTransform> | <span data-ttu-id="ab5b6-188">标准化特征范围。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-188">Standardizes feature ranges.</span></span> |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizingTransformer> |<span data-ttu-id="ab5b6-189">标准化特征范围。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-189">Standardizes feature ranges.</span></span> |

## <a name="onnx"></a><span data-ttu-id="ab5b6-190">Onnx</span><span class="sxs-lookup"><span data-stu-id="ab5b6-190">Onnx</span></span>

| <span data-ttu-id="ab5b6-191">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-191">Transform</span></span> | <span data-ttu-id="ab5b6-192">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-192">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | <span data-ttu-id="ab5b6-193">对使用 ONNX 标准 v1.2 的预定型 ONNX 模型进行评分</span><span class="sxs-lookup"><span data-stu-id="ab5b6-193">Scores pre-trained ONNX models which use the ONNX standard v1.2</span></span> |

## <a name="preprocessing"></a><span data-ttu-id="ab5b6-194">预处理</span><span class="sxs-lookup"><span data-stu-id="ab5b6-194">Preprocessing</span></span>
| <span data-ttu-id="ab5b6-195">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-195">Transform</span></span> | <span data-ttu-id="ab5b6-196">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-196">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BootstrapSamplingTransformer> | <span data-ttu-id="ab5b6-197">近似使用泊松采样的自助采样。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-197">Approximates bootstrap sampling using Poisson sampling.</span></span> |
| <xref:Microsoft.ML.Transforms.Projections.RandomFourierFeaturizingTransformer> | <span data-ttu-id="ab5b6-198">生成随机傅立叶特征。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-198">Produces random Fourier feature.</span></span> |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | <span data-ttu-id="ab5b6-199">面向字符的 tokenizer，其中文本被视为一系列字符。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-199">Character-oriented tokenizer where text is considered a sequence of characters.</span></span> |
| <xref:Microsoft.ML.Transforms.Projections.VectorWhiteningTransformer> | <span data-ttu-id="ab5b6-200">简化优化以帮助识别权重。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-200">Simplifies optimization to assist with identifying weights.</span></span> |

## <a name="row-filters"></a><span data-ttu-id="ab5b6-201">行筛选器</span><span class="sxs-lookup"><span data-stu-id="ab5b6-201">Row Filters</span></span>

| <span data-ttu-id="ab5b6-202">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-202">Transform</span></span> | <span data-ttu-id="ab5b6-203">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-203">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowShufflingTransformer> | <span data-ttu-id="ab5b6-204">使用给定行数的池混淆试图执行操作的随机游标。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-204">Shuffles a randomized cursor attempt to perform using a pool of a given number of rows.</span></span>  |
| <xref:Microsoft.ML.Transforms.SkipFilter> | <span data-ttu-id="ab5b6-205">允许通过跳过多行来将输入限制为行的子集。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-205">Allows limiting input to a subset of rows by skipping a number of rows.</span></span> |
| <xref:Microsoft.ML.Transforms.SkipTakeFilter> | <span data-ttu-id="ab5b6-206">允许将输入限制为可选偏移的行的子集。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-206">Allows limiting input to a subset of rows at an optional offset.</span></span> <span data-ttu-id="ab5b6-207">可用于实现数据分页。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-207">Can be used to implement data paging.</span></span> <span data-ttu-id="ab5b6-208">使用 SkipTakeFilter.SkipArguments 创建时，表现为 `SkipFilter`。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-208">When created with SkipTakeFilter.SkipArguments behaves as `SkipFilter`.</span></span>
| <xref:Microsoft.ML.Transforms.TakeFilter> | <span data-ttu-id="ab5b6-209">允许通过使用 N 个第一行来将输入限制为行的子集。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-209">Allows limiting input to a subset of rows by taking N first rows.</span></span> |


## <a name="schema"></a><span data-ttu-id="ab5b6-210">架构</span><span class="sxs-lookup"><span data-stu-id="ab5b6-210">Schema</span></span>

| <span data-ttu-id="ab5b6-211">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-211">Transform</span></span> | <span data-ttu-id="ab5b6-212">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-212">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnCopyingTransformer> | <span data-ttu-id="ab5b6-213">复制数据集中的列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-213">Duplicates columns from the dataset.</span></span>|
| <xref:Microsoft.ML.Transforms.ColumnSelectingTransformer> | <span data-ttu-id="ab5b6-214">选择要从给定输入中删除或保留的一组列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-214">Selects a set of columns to drop or keep from a given input.</span></span> |
| <xref:Microsoft.ML.Transforms.FeatureSelection.SlotsDroppingTransformer> | <span data-ttu-id="ab5b6-215">删除列中的槽。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-215">Drops slots from columns.</span></span>|
| <xref:Microsoft.ML.Transforms.OptionalColumnTransform> | <span data-ttu-id="ab5b6-216">使用指定的类型和默认值创建新列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-216">Creates a new column with the specified type and default values.</span></span> |
| <xref:Microsoft.ML.Transforms.RangeFilter> | <span data-ttu-id="ab5b6-217">在 Single、Double 或 Key 类型的列上筛选数据视图（相邻）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-217">Filters a dataview on a column of type Single, Double or Key (contiguous).</span></span> <span data-ttu-id="ab5b6-218">保留指定的最小/最大范围内的值。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-218">Keeps the values that are in the specified min/max range.</span></span> <span data-ttu-id="ab5b6-219">总是筛选出 NaN。如果输入是 Key 类型，则最小值/最大值将被视为值数量的百分比。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-219">NaNs are always filtered out. If the input is a Key type, the min/max are considered percentages of the number of values.</span></span> |

## <a name="tensorflow"></a><span data-ttu-id="ab5b6-220">TensorFlow</span><span class="sxs-lookup"><span data-stu-id="ab5b6-220">TensorFlow</span></span>

| <span data-ttu-id="ab5b6-221">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-221">Transform</span></span> | <span data-ttu-id="ab5b6-222">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-222">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | <span data-ttu-id="ab5b6-223">使用预定型的 TensorFlow 模型进行评分或重新定型 TensorFlow 模型。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-223">Either scores with pretrained TensorFlow model or retrains TensorFlow model.</span></span> |

## <a name="text-processing-and-featurization"></a><span data-ttu-id="ab5b6-224">文本处理和特征化</span><span class="sxs-lookup"><span data-stu-id="ab5b6-224">Text processing and featurization</span></span>

| <span data-ttu-id="ab5b6-225">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-225">Transform</span></span> | <span data-ttu-id="ab5b6-226">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-226">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.TextNormalizingTransformer> | <span data-ttu-id="ab5b6-227">文本规范化转换，可以规范化文本大小写、删除标注字符、标点符号和/或数字。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-227">A text normalization transform that allows normalizing text case, removing diacritical marks, punctuation marks and/or numbers.</span></span> <span data-ttu-id="ab5b6-228">转换对文本输入以及令牌/文本（ReadOnlyMemory 的矢量）的矢量进行的操作。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-228">The transform operates on text input as well as vector of tokens/text (vector of ReadOnlyMemory).</span></span> |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | <span data-ttu-id="ab5b6-229">面向字符的 tokenizer，其中文本被视为一系列字符。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-229">Character-oriented tokenizer where text is considered a sequence of characters.</span></span> |

## <a name="time-series"></a><span data-ttu-id="ab5b6-230">时序</span><span class="sxs-lookup"><span data-stu-id="ab5b6-230">Time series</span></span>

| <span data-ttu-id="ab5b6-231">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-231">Transform</span></span> | <span data-ttu-id="ab5b6-232">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-232">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesProcessing.ExponentialAverageTransform> | <span data-ttu-id="ab5b6-233">采用值的加权平均值：ExpAvg(y_t) = a \* y_t + (1-a) \* ExpAvg(y_(t-1))。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-233">Takes a weighted average of the values: ExpAvg(y_t) = a \* y_t + (1-a) \* ExpAvg(y_(t-1)).</span></span> |
| <xref:Microsoft.ML.TimeSeriesProcessing.IidChangePointDetector> | <span data-ttu-id="ab5b6-234">实现 i.i.d 的更改点检测器转换。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-234">Implements the change point detector transform for an i.i.d.</span></span> <span data-ttu-id="ab5b6-235">基于自适应内核密度估计和鞅的序列（随机样本）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-235">sequence (random sample) based on adaptive kernel density estimation and martingales.</span></span> |
| <xref:Microsoft.ML.TimeSeriesProcessing.IidSpikeDetector> | <span data-ttu-id="ab5b6-236">实现 i.i.d 的峰值检测器转换。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-236">Implements the spike detector transform for an i.i.d.</span></span> <span data-ttu-id="ab5b6-237">基于自适应内核密度估计的序列（随机样本）。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-237">sequence (random sample) based on adaptive kernel density estimation.</span></span> |
| <xref:Microsoft.ML.TimeSeriesProcessing.MovingAverageTransform> | <span data-ttu-id="ab5b6-238">提供滑动窗口值的加权平均值。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-238">Provides a weighted average of the sliding window values.</span></span> |
| <xref:Microsoft.ML.TimeSeriesProcessing.PercentileThresholdTransform> | <span data-ttu-id="ab5b6-239">确定时序当前值是否属于滑动窗口排在前列的几个值的百分比。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-239">Decides whether the time-series current value belongs to the sliding window top values percentile.</span></span> |
| <xref:Microsoft.ML.TimeSeriesProcessing.PValueTransform> | <span data-ttu-id="ab5b6-240">根据滑动窗口中的其他值计算该系列当前值经验 p 值。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-240">Computes the series current value empirical p-value based on the other values in the sliding window.</span></span> |
| <xref:Microsoft.ML.TimeSeriesProcessing.SlidingWindowTransform> | <span data-ttu-id="ab5b6-241">在 Single 类型的时序上输出滑动窗口。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-241">Outputs a sliding window on a time series of type Single.</span></span> |
| <xref:Microsoft.ML.TimeSeriesProcessing.SsaChangePointDetector> | <span data-ttu-id="ab5b6-242">基于时序的奇异谱建模实现更改点检测器转换。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-242">Implements the change point detector transform based on Singular Spectrum modeling of the time-series.</span></span> |
| <xref:Microsoft.ML.TimeSeriesProcessing.SsaSpikeDetector> | <span data-ttu-id="ab5b6-243">基于时序的奇异谱建模实现峰值检测器转换。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-243">Implements the spike detector transform based on Singular Spectrum modeling of the time-series.</span></span> |

## <a name="miscellaneous"></a><span data-ttu-id="ab5b6-244">杂项</span><span class="sxs-lookup"><span data-stu-id="ab5b6-244">Miscellaneous</span></span>

| <span data-ttu-id="ab5b6-245">Transform</span><span class="sxs-lookup"><span data-stu-id="ab5b6-245">Transform</span></span> | <span data-ttu-id="ab5b6-246">定义</span><span class="sxs-lookup"><span data-stu-id="ab5b6-246">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CompositeTransformer> | <span data-ttu-id="ab5b6-247">创建复合 DataTransform。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-247">Creates a Composite DataTransform.</span></span> |
| <xref:Microsoft.ML.Transforms.CustomMappingTransformer%602> | <span data-ttu-id="ab5b6-248">为提供的 `IDataView` 生成其他列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-248">Generates additional columns to the provided `IDataView`.</span></span> <span data-ttu-id="ab5b6-249">它不会更改行数，并且可以看作是将用户的函数应用于输入数据的每一行的结果。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-249">It doesn't change the number of rows and can be seen as a result of application of the user's function to every row of the input data.</span></span>|
| <xref:Microsoft.ML.Transforms.GenerateNumberTransform> | <span data-ttu-id="ab5b6-250">添加具有已生成数字序列的列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-250">Adds a column with a generated number sequence.</span></span> |
| <xref:Microsoft.ML.Transforms.ProduceIdTransform> | <span data-ttu-id="ab5b6-251">生成以游标的 ID 作为列的列。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-251">Produces a column with the cursor's ID as a column.</span></span> |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | <span data-ttu-id="ab5b6-252">生成随机数。</span><span class="sxs-lookup"><span data-stu-id="ab5b6-252">Generates a random number.</span></span> |
