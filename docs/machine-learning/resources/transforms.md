---
title: 数据转换
description: 了解在 ML.NET 中受支持的不同数据转换。
ms.date: 08/08/2018
author: jralexander
ms.author: johalex
ms.openlocfilehash: 3c483f4a263052eb15435775a47f514893eee049
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43397138"
---
# <a name="data-transforms"></a><span data-ttu-id="16a31-103">数据转换</span><span class="sxs-lookup"><span data-stu-id="16a31-103">Data transforms</span></span>

<span data-ttu-id="16a31-104">下表包含有关 ML.NET 中受支持的所有数据转换的信息（选择数据转换类型以导航到相应的表）：</span><span class="sxs-lookup"><span data-stu-id="16a31-104">The following tables contain information about all of the data transforms supported in ML.NET (select the data transform type to navigate to the corresponding table):</span></span>

* [<span data-ttu-id="16a31-105">分类</span><span class="sxs-lookup"><span data-stu-id="16a31-105">Categorical</span></span>](#categorical)
* [<span data-ttu-id="16a31-106">合并器和分离器</span><span class="sxs-lookup"><span data-stu-id="16a31-106">Combiners and segregators</span></span>](#combiners-and-segregators)
* [<span data-ttu-id="16a31-107">功能选择</span><span class="sxs-lookup"><span data-stu-id="16a31-107">Feature selection</span></span>](#feature-selection)
* [<span data-ttu-id="16a31-108">Featurizers</span><span class="sxs-lookup"><span data-stu-id="16a31-108">Featurizers</span></span>](#featurizers)
* [<span data-ttu-id="16a31-109">标签分析</span><span class="sxs-lookup"><span data-stu-id="16a31-109">Label parsing</span></span>](#label-parsing)
* [<span data-ttu-id="16a31-110">缺失值</span><span class="sxs-lookup"><span data-stu-id="16a31-110">Missing Values</span></span>](#missing-values)
* [<span data-ttu-id="16a31-111">标准化</span><span class="sxs-lookup"><span data-stu-id="16a31-111">Normalization</span></span>](#normalization)
* [<span data-ttu-id="16a31-112">行筛选器</span><span class="sxs-lookup"><span data-stu-id="16a31-112">Row filters</span></span>](#row-filters)
* [<span data-ttu-id="16a31-113">架构</span><span class="sxs-lookup"><span data-stu-id="16a31-113">Schema</span></span>](#schema)
* [<span data-ttu-id="16a31-114">文本处理和特征化</span><span class="sxs-lookup"><span data-stu-id="16a31-114">Text processing and featurization</span></span>](#text-processing-and-featurization)
* [<span data-ttu-id="16a31-115">杂项</span><span class="sxs-lookup"><span data-stu-id="16a31-115">Miscellaneous</span></span>](#miscellaneous)

> [!NOTE]
> <span data-ttu-id="16a31-116">ML.NET 当前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="16a31-116">ML.NET is currently in Preview.</span></span> <span data-ttu-id="16a31-117">当前并不支持所有数据转换。</span><span class="sxs-lookup"><span data-stu-id="16a31-117">Not all data transforms are currently supported.</span></span> <span data-ttu-id="16a31-118">要提交某项转换请求，请在 [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues) GitHub 存储库中发起一个问题。</span><span class="sxs-lookup"><span data-stu-id="16a31-118">To submit a request for a certain transform, open an issue in the [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues) GitHub repository.</span></span>

## <a name="categorical"></a><span data-ttu-id="16a31-119">分类</span><span class="sxs-lookup"><span data-stu-id="16a31-119">Categorical</span></span>

| <span data-ttu-id="16a31-120">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-120">Transform</span></span> | <span data-ttu-id="16a31-121">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-121">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CategoricalHashOneHotVectorizer> | <span data-ttu-id="16a31-122">使用基于哈希的编码对分类变量进行编码。</span><span class="sxs-lookup"><span data-stu-id="16a31-122">Encodes the categorical variable with hash-based encoding.</span></span> |
| <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer> | <span data-ttu-id="16a31-123">使用基于术语字典的独热编码对分类变量进行编码。</span><span class="sxs-lookup"><span data-stu-id="16a31-123">Encodes the categorical variable with one-hot encoding based on a term dictionary.</span></span> |

## <a name="combiners-and-segregators"></a><span data-ttu-id="16a31-124">合并器和分离器</span><span class="sxs-lookup"><span data-stu-id="16a31-124">Combiners and segregators</span></span>

| <span data-ttu-id="16a31-125">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-125">Transform</span></span> | <span data-ttu-id="16a31-126">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-126">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CombinerByContiguousGroupId> | <span data-ttu-id="16a31-127">根据相邻的组 ID，将标量列的值汇集到矢量中。</span><span class="sxs-lookup"><span data-stu-id="16a31-127">Groups values of a scalar column into a vector based on a contiguous group ID.</span></span> |
| <xref:Microsoft.ML.Transforms.FeatureCombiner> | <span data-ttu-id="16a31-128">将所有功能合并到一个功能列中。</span><span class="sxs-lookup"><span data-stu-id="16a31-128">Combines all the features into one feature column.</span></span> |
| <xref:Microsoft.ML.Transforms.ManyHeterogeneousModelCombiner> | <span data-ttu-id="16a31-129">将一系列 TransformModel 和一个 PredictorModel 合并到一个 PredictorModel 中。</span><span class="sxs-lookup"><span data-stu-id="16a31-129">Combines a sequence of TransformModels and a PredictorModel into a single PredictorModel.</span></span> |
| <xref:Microsoft.ML.Transforms.ModelCombiner> | <span data-ttu-id="16a31-130">将一系列 TransformModel 合并到一个模型中。</span><span class="sxs-lookup"><span data-stu-id="16a31-130">Combines a sequence of TransformModels into a single model.</span></span> |
| <xref:Microsoft.ML.Transforms.Segregator> | <span data-ttu-id="16a31-131">将矢量列取消组合为一系列行；组转换的逆向。</span><span class="sxs-lookup"><span data-stu-id="16a31-131">Ungroups vector columns into sequences of rows; the inverse of Group transform.</span></span> |
| <xref:Microsoft.ML.Transforms.TwoHeterogeneousModelCombiner> | <span data-ttu-id="16a31-132">将一个 TransformModel 和一个 PredictorModel 合并到一个 PredictorModel 中。</span><span class="sxs-lookup"><span data-stu-id="16a31-132">Combines a TransformModel and a PredictorModel into a single PredictorModel.</span></span> |

## <a name="feature-selection"></a><span data-ttu-id="16a31-133">功能选择</span><span class="sxs-lookup"><span data-stu-id="16a31-133">Feature selection</span></span>

| <span data-ttu-id="16a31-134">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-134">Transform</span></span> | <span data-ttu-id="16a31-135">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-135">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.FeatureSelectorByCount> | <span data-ttu-id="16a31-136">选择非默认值计数大于或等于阈值的槽。</span><span class="sxs-lookup"><span data-stu-id="16a31-136">Selects the slots for which the count of non-default values is greater than or equal to a threshold.</span></span> |
| <xref:Microsoft.ML.Transforms.FeatureSelectorByMutualInformation> | <span data-ttu-id="16a31-137">选择所有指定列中的前 k 个槽，这些列按其与标签列的相互信息排序。</span><span class="sxs-lookup"><span data-stu-id="16a31-137">Selects the top k slots across all specified columns ordered by their mutual information with the label column.</span></span> |

## <a name="featurizers"></a><span data-ttu-id="16a31-138">Featurizers</span><span class="sxs-lookup"><span data-stu-id="16a31-138">Featurizers</span></span>

| <span data-ttu-id="16a31-139">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-139">Transform</span></span> | <span data-ttu-id="16a31-140">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-140">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.HashConverter> | <span data-ttu-id="16a31-141">将列值转换为哈希。</span><span class="sxs-lookup"><span data-stu-id="16a31-141">Converts column values into hashes.</span></span> <span data-ttu-id="16a31-142">此转换接受数字和文本输入，包括单值和矢量值列。</span><span class="sxs-lookup"><span data-stu-id="16a31-142">This transform accepts both numeric and text inputs, both single and vector-valued columns.</span></span> |
| <xref:Microsoft.ML.Transforms.TreeLeafFeaturizer> | <span data-ttu-id="16a31-143">训练树形集成，或从文件加载它，然后将数字功能矢量映射到三个输出：1。</span><span class="sxs-lookup"><span data-stu-id="16a31-143">Trains a tree ensemble, or loads it from a file, then maps a numeric feature vector to three outputs: 1.</span></span> <span data-ttu-id="16a31-144">包含树形集成的各个树输出的矢量。</span><span class="sxs-lookup"><span data-stu-id="16a31-144">A vector containing the individual tree outputs of the tree ensemble.</span></span> <span data-ttu-id="16a31-145">2.</span><span class="sxs-lookup"><span data-stu-id="16a31-145">2.</span></span> <span data-ttu-id="16a31-146">指示功能矢量落在树形集成上的叶子的矢量。</span><span class="sxs-lookup"><span data-stu-id="16a31-146">A vector indicating the leaves that the feature vector falls on in the tree ensemble.</span></span> <span data-ttu-id="16a31-147">3.</span><span class="sxs-lookup"><span data-stu-id="16a31-147">3.</span></span> <span data-ttu-id="16a31-148">指示功能矢量落在树形集成上的路径的矢量。</span><span class="sxs-lookup"><span data-stu-id="16a31-148">A vector indicating the paths that the feature vector falls on in the tree ensemble.</span></span> <span data-ttu-id="16a31-149">如果同时指定了模型文件和训练器，则矢量将使用模型文件。</span><span class="sxs-lookup"><span data-stu-id="16a31-149">If both a model file and a trainer are specified, the vector will use the model file.</span></span> <span data-ttu-id="16a31-150">如果两者都未指定，则矢量将训练默认的 FastTree 模型。</span><span class="sxs-lookup"><span data-stu-id="16a31-150">If neither are specified, the vector will train a default FastTree model.</span></span> <span data-ttu-id="16a31-151">这可以处理键标签，方法是针对其可选的置换索引训练回归模型。</span><span class="sxs-lookup"><span data-stu-id="16a31-151">This can handle key labels by training a regression model towards their optionally permuted indices.</span></span> |

## <a name="label-parsing"></a><span data-ttu-id="16a31-152">标签分析</span><span class="sxs-lookup"><span data-stu-id="16a31-152">Label parsing</span></span>

| <span data-ttu-id="16a31-153">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-153">Transform</span></span> | <span data-ttu-id="16a31-154">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-154">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Dictionarizer> | <span data-ttu-id="16a31-155">将输入值（单词、数字等）转换为字典中的索引。</span><span class="sxs-lookup"><span data-stu-id="16a31-155">Converts input values (words, numbers, etc.) to index in a dictionary.</span></span> |
| <xref:Microsoft.ML.Transforms.LabelColumnKeyBooleanConverter> | <span data-ttu-id="16a31-156">将标签转换为键或布尔值（如果需要），使其适用于分类。</span><span class="sxs-lookup"><span data-stu-id="16a31-156">Transforms the label to either key or bool (if needed) to make it suitable for classification.</span></span> |
| <xref:Microsoft.ML.Transforms.LabelIndicator> | <span data-ttu-id="16a31-157">OVA 使用的标签重映射器。</span><span class="sxs-lookup"><span data-stu-id="16a31-157">Label remapper used by OVA.</span></span> |
| <xref:Microsoft.ML.Transforms.LabelToFloatConverter> | <span data-ttu-id="16a31-158">将标签转换为浮点，使其适用于回归。</span><span class="sxs-lookup"><span data-stu-id="16a31-158">Transforms the label to float to make it suitable for regression.</span></span> |
| <xref:Microsoft.ML.Transforms.PredictedLabelColumnOriginalValueConverter> | <span data-ttu-id="16a31-159">将预测标签列转换为其原始值，除非它是布尔值类型。</span><span class="sxs-lookup"><span data-stu-id="16a31-159">Transforms a predicted label column to its original values, unless it is of type bool.</span></span> |

## <a name="missing-values"></a><span data-ttu-id="16a31-160">缺失值</span><span class="sxs-lookup"><span data-stu-id="16a31-160">Missing Values</span></span>

| <span data-ttu-id="16a31-161">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-161">Transform</span></span> | <span data-ttu-id="16a31-162">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-162">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueHandler> | <span data-ttu-id="16a31-163">通过将缺失值替换为默认值或平均值/最小值/最大值（仅适用于非文本列）来处理缺失值。</span><span class="sxs-lookup"><span data-stu-id="16a31-163">Handle missing values by replacing them with either the default value or the mean/min/max value (for non-text columns only).</span></span> <span data-ttu-id="16a31-164">如果输入列类型为数值，则可以选择连接指示符列。</span><span class="sxs-lookup"><span data-stu-id="16a31-164">An indicator column can optionally be concatenated, if the input column type is numeric.</span></span> |
| <xref:Microsoft.ML.Transforms.MissingValueIndicator> | <span data-ttu-id="16a31-165">创建一个布尔值输出列，其槽数与输入列相同，如果缺少输入列中的值，则输出值为 true。</span><span class="sxs-lookup"><span data-stu-id="16a31-165">Create a boolean output column with the same number of slots as the input column, where the output value is true if the value in the input column is missing.</span></span> |
| <xref:Microsoft.ML.Transforms.MissingValuesDropper> | <span data-ttu-id="16a31-166">从矢量列中删除 NA。</span><span class="sxs-lookup"><span data-stu-id="16a31-166">Removes NAs from vector columns.</span></span> |
| <xref:Microsoft.ML.Transforms.MissingValuesRowDropper> | <span data-ttu-id="16a31-167">筛选出包含缺失值的行。</span><span class="sxs-lookup"><span data-stu-id="16a31-167">Filters out rows that contain missing values.</span></span> |
| <xref:Microsoft.ML.Transforms.MissingValueSubstitutor> | <span data-ttu-id="16a31-168">创建与输入列的类型和大小相同的输出列，其中缺失值将替换为默认值或平均值/最小值/最大值（仅适用于非文本列）。</span><span class="sxs-lookup"><span data-stu-id="16a31-168">Create an output column of the same type and size of the input column, where missing values are replaced with either the default value or the mean/min/max value (for non-text columns only).</span></span> |

## <a name="normalization"></a><span data-ttu-id="16a31-169">标准化</span><span class="sxs-lookup"><span data-stu-id="16a31-169">Normalization</span></span>

| <span data-ttu-id="16a31-170">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-170">Transform</span></span> | <span data-ttu-id="16a31-171">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-171">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BinNormalizer> | <span data-ttu-id="16a31-172">将值分配到等密度箱中，并将值映射到其 bin_number / number_of_bins。</span><span class="sxs-lookup"><span data-stu-id="16a31-172">The values are assigned into equidensity bins and a value is mapped to its bin_number / number_of_bins.</span></span> |
| <xref:Microsoft.ML.Transforms.ConditionalNormalizer> | <span data-ttu-id="16a31-173">仅在需要时，对列进行标准化。</span><span class="sxs-lookup"><span data-stu-id="16a31-173">Normalize the columns only if needed.</span></span> |
| <xref:Microsoft.ML.Transforms.GlobalContrastNormalizer> | <span data-ttu-id="16a31-174">对输入值执行全局对比度标准化：Y = (s \* X - M) / D，其中 s 是范围，M 是平均值，D 是 L2 范数或标准差。</span><span class="sxs-lookup"><span data-stu-id="16a31-174">Performs a global contrast normalization on input values: Y = (s \* X - M) / D, where s is a scale, M is mean and D is either L2 norm or standard deviation.</span></span> | 
| <xref:Microsoft.ML.Transforms.LogMeanVarianceNormalizer> | <span data-ttu-id="16a31-175">根据计算平均数和数据对数方差对数据进行标准化。</span><span class="sxs-lookup"><span data-stu-id="16a31-175">Normalizes the data based on the computed mean and variance of the logarithm of the data.</span></span> |
| <xref:Microsoft.ML.Transforms.LpNormalizer> | <span data-ttu-id="16a31-176">通过将矢量（行）重新调整为单位范数（L2、L1 或 LInf）来单独标准化矢量。</span><span class="sxs-lookup"><span data-stu-id="16a31-176">Normalize vectors (rows) individually by rescaling them to the unit norm (L2, L1 or LInf).</span></span> <span data-ttu-id="16a31-177">对矢量 X 执行以下操作：Y = (X - M) / D，其中 M 是平均值，D 是 L2 范数、L1 范数或 LInf 范数。</span><span class="sxs-lookup"><span data-stu-id="16a31-177">Performs the following operation on a vector X: Y = (X - M) / D, where M is mean and D is either the L2 norm, the L1 norm, or the LInf norm.</span></span> |
| <xref:Microsoft.ML.Transforms.MeanVarianceNormalizer> | <span data-ttu-id="16a31-178">根据计算平均数和数据方差对数据进行标准化。</span><span class="sxs-lookup"><span data-stu-id="16a31-178">Normalizes the data based on the computed mean and variance of the data.</span></span> |
| <xref:Microsoft.ML.Transforms.MinMaxNormalizer> | <span data-ttu-id="16a31-179">根据观察到的数据的最小值和最大值对数据进行标准化。</span><span class="sxs-lookup"><span data-stu-id="16a31-179">Normalizes the data based on the observed minimum and maximum values of the data.</span></span> |
| <xref:Microsoft.ML.Transforms.SupervisedBinNormalizer> | <span data-ttu-id="16a31-180">与 <xref:Microsoft.ML.Transforms.BinNormalizer> 类似，但根据与标签列的关联计算箱数，而不是等密度。</span><span class="sxs-lookup"><span data-stu-id="16a31-180">Similar to <xref:Microsoft.ML.Transforms.BinNormalizer>, but calculates bins based on correlation with the label column, not equidensity.</span></span> <span data-ttu-id="16a31-181">新值是 bin_number / number_of_bins。</span><span class="sxs-lookup"><span data-stu-id="16a31-181">The new value is bin_number / number_of_bins.</span></span> |

## <a name="row-filters"></a><span data-ttu-id="16a31-182">行筛选器</span><span class="sxs-lookup"><span data-stu-id="16a31-182">Row Filters</span></span>

| <span data-ttu-id="16a31-183">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-183">Transform</span></span> | <span data-ttu-id="16a31-184">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-184">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowRangeFilter> | <span data-ttu-id="16a31-185">在 Single、Double 或 Key 类型的列上筛选数据视图（相邻）。</span><span class="sxs-lookup"><span data-stu-id="16a31-185">Filters a dataview on a column of type Single, Double or Key (contiguous).</span></span> <span data-ttu-id="16a31-186">保留指定的最小/最大范围内的值。</span><span class="sxs-lookup"><span data-stu-id="16a31-186">Keeps the values that are in the specified min/max range.</span></span> <span data-ttu-id="16a31-187">总是筛选出 NaN。如果输入是 Key 类型，则最小值/最大值将被视为值数量的百分比。</span><span class="sxs-lookup"><span data-stu-id="16a31-187">NaNs are always filtered out. If the input is a Key type, the min/max are considered percentages of the number of values.</span></span> |
| <xref:Microsoft.ML.Transforms.RowSkipAndTakeFilter> | <span data-ttu-id="16a31-188">允许将输入限制为可选偏移的行的子集。</span><span class="sxs-lookup"><span data-stu-id="16a31-188">Allows limiting input to a subset of rows at an optional offset.</span></span> <span data-ttu-id="16a31-189">可用于实现数据分页。</span><span class="sxs-lookup"><span data-stu-id="16a31-189">Can be used to implement data paging.</span></span> |
| <xref:Microsoft.ML.Transforms.RowSkipFilter> | <span data-ttu-id="16a31-190">允许通过跳过多行来将输入限制为行的子集。</span><span class="sxs-lookup"><span data-stu-id="16a31-190">Allows limiting input to a subset of rows by skipping a number of rows.</span></span> |
| <xref:Microsoft.ML.Transforms.RowTakeFilter> | <span data-ttu-id="16a31-191">允许通过使用 N 个第一行来将输入限制为行的子集。</span><span class="sxs-lookup"><span data-stu-id="16a31-191">Allows limiting input to a subset of rows by taking N first rows.</span></span> |

## <a name="schema"></a><span data-ttu-id="16a31-192">架构</span><span class="sxs-lookup"><span data-stu-id="16a31-192">Schema</span></span>

| <span data-ttu-id="16a31-193">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-193">Transform</span></span> | <span data-ttu-id="16a31-194">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-194">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnConcatenator> | <span data-ttu-id="16a31-195">连接同一项目类型的两列。</span><span class="sxs-lookup"><span data-stu-id="16a31-195">Concatenates two columns of the same item type.</span></span> |
| <xref:Microsoft.ML.Transforms.ColumnCopier> | <span data-ttu-id="16a31-196">复制数据集中的列。</span><span class="sxs-lookup"><span data-stu-id="16a31-196">Duplicates columns from the dataset.</span></span>|
| <xref:Microsoft.ML.Transforms.ColumnDropper> | <span data-ttu-id="16a31-197">从数据集中删除列。</span><span class="sxs-lookup"><span data-stu-id="16a31-197">Drops columns from the dataset.</span></span> |
| <xref:Microsoft.ML.Transforms.ColumnSelector> | <span data-ttu-id="16a31-198">选择一组列，删除所有其他列。</span><span class="sxs-lookup"><span data-stu-id="16a31-198">Selects a set of columns, dropping all others.</span></span> |
| <xref:Microsoft.ML.Transforms.ColumnTypeConverter> | <span data-ttu-id="16a31-199">使用标准转换将列转换为其他类型。</span><span class="sxs-lookup"><span data-stu-id="16a31-199">Converts a column to a different type, using standard conversions.</span></span> |
| <xref:Microsoft.ML.Transforms.KeyToTextConverter> | <span data-ttu-id="16a31-200">KeyToValueTransform 利用 KeyValues 元数据将键索引映射到 KeyValues 元数据中的相应值。</span><span class="sxs-lookup"><span data-stu-id="16a31-200">KeyToValueTransform utilizes KeyValues metadata to map key indices to the corresponding values in the KeyValues metadata.</span></span> |
| <xref:Microsoft.ML.Transforms.NGramTranslator> | <span data-ttu-id="16a31-201">在给定的键矢量中生成一组 ngrams 计数（长度为 1-n 的连续值的序列）。</span><span class="sxs-lookup"><span data-stu-id="16a31-201">Produces a bag of counts of ngrams (sequences of consecutive values of length 1-n) in a given vector of keys.</span></span> <span data-ttu-id="16a31-202">它通过生成 ngram 字典并使用字典中的 ID 作为包中的索引来实现。</span><span class="sxs-lookup"><span data-stu-id="16a31-202">It does so by building a dictionary of ngrams and using the id in the dictionary as the index in the bag.</span></span> | 
| <xref:Microsoft.ML.Transforms.OptionalColumnCreator> | <span data-ttu-id="16a31-203">如果反序列化后源列不存在，请创建具有正确类型和默认值的列。</span><span class="sxs-lookup"><span data-stu-id="16a31-203">If the source column does not exist after deserialization, create a column with the right type and default values.</span></span> |

## <a name="text-processing-and-featurization"></a><span data-ttu-id="16a31-204">文本处理和特征化</span><span class="sxs-lookup"><span data-stu-id="16a31-204">Text processing and featurization</span></span>

| <span data-ttu-id="16a31-205">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-205">Transform</span></span> | <span data-ttu-id="16a31-206">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-206">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CharacterTokenizer> | <span data-ttu-id="16a31-207">面向字符的 tokenizer，其中文本被视为一系列字符。</span><span class="sxs-lookup"><span data-stu-id="16a31-207">Character-oriented tokenizer where text is considered a sequence of characters.</span></span> |
| <xref:Microsoft.ML.Transforms.TextFeaturizer> | <span data-ttu-id="16a31-208">将文本文档集合转换为数值功能矢量的转换。</span><span class="sxs-lookup"><span data-stu-id="16a31-208">A transform that turns a collection of text documents into numerical feature vectors.</span></span> <span data-ttu-id="16a31-209">功能矢量是给定已标记文本中的（单词和/或字符）ngrams 的标准化计数。</span><span class="sxs-lookup"><span data-stu-id="16a31-209">The feature vectors are normalized counts of (word and/or character) ngrams in a given tokenized text.</span></span> |
| <xref:Microsoft.ML.Transforms.TextToKeyConverter> | <span data-ttu-id="16a31-210">将输入值（单词、数字等）转换为字典中的索引。</span><span class="sxs-lookup"><span data-stu-id="16a31-210">Converts input values (words, numbers, etc.) to index in a dictionary.</span></span> |
| <xref:Microsoft.ML.Transforms.WordEmbeddings> | <span data-ttu-id="16a31-211">一种转换，它使用预先训练模型将文本令牌的矢量转换为数值矢量。</span><span class="sxs-lookup"><span data-stu-id="16a31-211">A transform that converts vectors of text tokens into numeric vectors using a pre-trained model.</span></span> <span data-ttu-id="16a31-212">有关该技术的详细信息，请参阅 [Word 嵌入](https://en.wikipedia.org/wiki/Word_embedding) Wikipedia 页。</span><span class="sxs-lookup"><span data-stu-id="16a31-212">For more information about the technique, see the [Word embedding](https://en.wikipedia.org/wiki/Word_embedding) Wikipedia page.</span></span> |
| <xref:Microsoft.ML.Transforms.WordTokenizer> | <span data-ttu-id="16a31-213">此转换的输入是文本，输出是包含原始文本中单词（令牌）的文本矢量。</span><span class="sxs-lookup"><span data-stu-id="16a31-213">The input to this transform is text, and the output is a vector of text containing the words (tokens) in the original text.</span></span> <span data-ttu-id="16a31-214">该分隔符是空格，但可指定任何其他字符（或多个字符）。</span><span class="sxs-lookup"><span data-stu-id="16a31-214">The separator is space, but any other character (or multiple characters) can be specified.</span></span> |

## <a name="miscellaneous"></a><span data-ttu-id="16a31-215">杂项</span><span class="sxs-lookup"><span data-stu-id="16a31-215">Miscellaneous</span></span>

| <span data-ttu-id="16a31-216">Transform</span><span class="sxs-lookup"><span data-stu-id="16a31-216">Transform</span></span> | <span data-ttu-id="16a31-217">定义</span><span class="sxs-lookup"><span data-stu-id="16a31-217">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ApproximateBootstrapSampler> | <span data-ttu-id="16a31-218">近似启动采样。</span><span class="sxs-lookup"><span data-stu-id="16a31-218">Approximate bootstrap sampling.</span></span> |
| <xref:Microsoft.ML.Transforms.BinaryPredictionScoreColumnsRenamer> | <span data-ttu-id="16a31-219">对于二进制预测，重命名 PredictedLabel 和 Score 列以包含正类的名称。</span><span class="sxs-lookup"><span data-stu-id="16a31-219">For binary prediction, renames the PredictedLabel and Score columns to include the name of the positive class.</span></span>|
| <xref:Microsoft.ML.Transforms.DataCache> | <span data-ttu-id="16a31-220">使用指定缓存选项缓存。</span><span class="sxs-lookup"><span data-stu-id="16a31-220">Caches using the specified cache option.</span></span> |
| <xref:Microsoft.ML.Transforms.DatasetScorer> | <span data-ttu-id="16a31-221">使用预测模型对数据集进行评分。</span><span class="sxs-lookup"><span data-stu-id="16a31-221">Scores a dataset with a predictor model.</span></span> |
| <xref:Microsoft.ML.Transforms.DatasetTransformScorer> | <span data-ttu-id="16a31-222">使用转换模型对数据集进行评分。</span><span class="sxs-lookup"><span data-stu-id="16a31-222">Scores a dataset with a transform model.</span></span> |
| <xref:Microsoft.ML.Transforms.NoOperation> | <span data-ttu-id="16a31-223">不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="16a31-223">Does nothing.</span></span> |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | <span data-ttu-id="16a31-224">添加具有已生成数字序列的列。</span><span class="sxs-lookup"><span data-stu-id="16a31-224">Adds a column with a generated number sequence.</span></span> |
| <xref:Microsoft.ML.Transforms.ScoreColumnSelector> | <span data-ttu-id="16a31-225">仅选择最后评分列和参数中指定的其他列。</span><span class="sxs-lookup"><span data-stu-id="16a31-225">Selects only the last score columns and the extra columns specified in the arguments.</span></span> |
| <xref:Microsoft.ML.Transforms.Scorer> | <span data-ttu-id="16a31-226">将预测模型转换为转换模型。</span><span class="sxs-lookup"><span data-stu-id="16a31-226">Turns the predictor model into a transform model.</span></span> |
| <xref:Microsoft.ML.Transforms.SentimentAnalyzer> | <span data-ttu-id="16a31-227">使用预先训练的情绪模型对输入字符串进行评分。</span><span class="sxs-lookup"><span data-stu-id="16a31-227">Uses a pretrained sentiment model to score input strings.</span></span> |
| <xref:Microsoft.ML.Transforms.TrainTestDatasetSplitter> | <span data-ttu-id="16a31-228">将数据集拆分为训练集和测试集。</span><span class="sxs-lookup"><span data-stu-id="16a31-228">Splits the dataset into train and test sets.</span></span> |
