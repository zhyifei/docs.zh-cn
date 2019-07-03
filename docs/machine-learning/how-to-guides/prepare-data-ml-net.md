---
title: 准备数据
description: 了解如何在 ML.NET 中使用转换来操作和准备数据用于进行其他处理或建模。
author: luisquintanilla
ms.author: luquinta
ms.date: 05/03/2019
ms.custom: mvc, how-to
ms.openlocfilehash: abf43260a438c9b1febffc77cf39e7328e0377ee
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268247"
---
# <a name="prepare-data"></a><span data-ttu-id="69061-103">准备数据</span><span class="sxs-lookup"><span data-stu-id="69061-103">Prepare Data</span></span>

<span data-ttu-id="69061-104">了解如何使用 ML.NET 来准备数据用于进行其他处理或生成模型。</span><span class="sxs-lookup"><span data-stu-id="69061-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="69061-105">数据通常是不干净的和稀疏的。</span><span class="sxs-lookup"><span data-stu-id="69061-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="69061-106">此外，ML.NET 机器学习算法期望输入或特征位于单个数字向量中。</span><span class="sxs-lookup"><span data-stu-id="69061-106">Additionally, ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="69061-107">因此，数据准备的目标之一是将数据转换为 ML.NET 算法所期望的格式。</span><span class="sxs-lookup"><span data-stu-id="69061-107">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span> 

## <a name="filter-data"></a><span data-ttu-id="69061-108">筛选数据</span><span class="sxs-lookup"><span data-stu-id="69061-108">Filter data</span></span>

<span data-ttu-id="69061-109">有时，并非数据集中的所有数据都与分析相关。</span><span class="sxs-lookup"><span data-stu-id="69061-109">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="69061-110">删除不相关数据的方法之一是筛选。</span><span class="sxs-lookup"><span data-stu-id="69061-110">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="69061-111">[`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) 包含一组筛选操作，这些操作接收包含所有数据的 [`IDataView`](xref:Microsoft.ML.IDataView)，并返回仅包含关注数据点的 [IDataView](xref:Microsoft.ML.IDataView)。</span><span class="sxs-lookup"><span data-stu-id="69061-111">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="69061-112">值得注意的是，因为筛选操作不像 [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog) 中的操作那样是 [`IEstimator`](xref:Microsoft.ML.IEstimator%601) 或 [`ITransformer`](xref:Microsoft.ML.ITransformer)，所以它们不能作为 [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) 或 [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) 数据准备管道的一部分包含在内。</span><span class="sxs-lookup"><span data-stu-id="69061-112">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span> 

<span data-ttu-id="69061-113">使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：</span><span class="sxs-lookup"><span data-stu-id="69061-113">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

<span data-ttu-id="69061-114">若要根据列的值筛选数据，请使用 [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) 方法。</span><span class="sxs-lookup"><span data-stu-id="69061-114">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="69061-115">上述示例采用数据集中价格介于 200,000 和 1,000,000 之间的行。</span><span class="sxs-lookup"><span data-stu-id="69061-115">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="69061-116">应用此筛选器的结果为，将仅返回数据中的最后两行，并排除第一行，因为其价格为 100,000，不在指定范围之间。</span><span class="sxs-lookup"><span data-stu-id="69061-116">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="69061-117">替换缺失值</span><span class="sxs-lookup"><span data-stu-id="69061-117">Replace missing values</span></span>

<span data-ttu-id="69061-118">缺失值在数据集中是常见现象。</span><span class="sxs-lookup"><span data-stu-id="69061-118">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="69061-119">处理缺失值的一种方法是使用给定类型的默认值（如有）或其他有意义的值（例如数据中的平均值）替换它们。</span><span class="sxs-lookup"><span data-stu-id="69061-119">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span> 

<span data-ttu-id="69061-120">使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：</span><span class="sxs-lookup"><span data-stu-id="69061-120">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=float.NaN
    }
};
```

<span data-ttu-id="69061-121">请注意，列表中最后一个元素的 `Price` 缺失值。</span><span class="sxs-lookup"><span data-stu-id="69061-121">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="69061-122">若要替换 `Price` 列中的缺失值，请使用 [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) 方法填充该缺失值。</span><span class="sxs-lookup"><span data-stu-id="69061-122">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69061-123">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) 仅适用于数字数据。</span><span class="sxs-lookup"><span data-stu-id="69061-123">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="69061-124">ML.NET 支持各种[替换模式](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode)。</span><span class="sxs-lookup"><span data-stu-id="69061-124">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="69061-125">上述示例使用 `Mean` 替换模式，该模式将使用该列的平均值填充缺失值。</span><span class="sxs-lookup"><span data-stu-id="69061-125">The sample above uses the `Mean` replacement mode which will fill in the missing value with that column's average value.</span></span> <span data-ttu-id="69061-126">替换的结果使用 200,000 填充数据中最后一个元素的 `Price` 属性，因为它是 100,000 和 300,000 的平均值。</span><span class="sxs-lookup"><span data-stu-id="69061-126">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span> 

## <a name="use-normalizers"></a><span data-ttu-id="69061-127">使用规范化程序</span><span class="sxs-lookup"><span data-stu-id="69061-127">Use normalizers</span></span>

<span data-ttu-id="69061-128">[规范化](https://en.wikipedia.org/wiki/Feature_scaling)是一种数据预处理技术，用于标准化比例不同的特征，这有助于算法更快地融合。</span><span class="sxs-lookup"><span data-stu-id="69061-128">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to standardize features that are not on the same scale which helps algorithms converge faster.</span></span> <span data-ttu-id="69061-129">例如，年龄和收入等值的范围存在明显差异，年龄的范围通常为 0-100，而收入的范围通常为零到数千。</span><span class="sxs-lookup"><span data-stu-id="69061-129">For example, the ranges for values like age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="69061-130">访问[转换页面](../resources/transforms.md)，获取更详细的规范化转换列表和说明。</span><span class="sxs-lookup"><span data-stu-id="69061-130">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span> 

### <a name="min-max-normalization"></a><span data-ttu-id="69061-131">最小-最大规范化</span><span class="sxs-lookup"><span data-stu-id="69061-131">Min-Max normalization</span></span>

<span data-ttu-id="69061-132">使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：</span><span class="sxs-lookup"><span data-stu-id="69061-132">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms = 2f,
        Price = 200000f
    },
    new HomeData
    {
        NumberOfBedrooms = 1f,
        Price = 100000f
    }
};
```

<span data-ttu-id="69061-133">可以向包含单个数值及矢量的列应用规范化。</span><span class="sxs-lookup"><span data-stu-id="69061-133">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="69061-134">使用 [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) 方法通过最小-最大规范化来规范化 `Price` 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="69061-134">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="69061-135">原始价格值 `[200000,100000]` 使用 `MinMax` 规范化公式转换为 `[ 1, 0.5 ]`，该公式生成范围在 0-1 之间的输出值。</span><span class="sxs-lookup"><span data-stu-id="69061-135">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula which generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="69061-136">分箱</span><span class="sxs-lookup"><span data-stu-id="69061-136">Binning</span></span>

<span data-ttu-id="69061-137">[分箱](https://en.wikipedia.org/wiki/Data_binning)将连续值转换为输入的离散表示形式。</span><span class="sxs-lookup"><span data-stu-id="69061-137">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="69061-138">例如，假设某个特征为年龄。</span><span class="sxs-lookup"><span data-stu-id="69061-138">For example, suppose one of your features is age.</span></span> <span data-ttu-id="69061-139">分箱不使用实际年龄值，而是为该值创建范围。</span><span class="sxs-lookup"><span data-stu-id="69061-139">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="69061-140">0-18 可以是一个箱，另一个箱可以是 19-35，依此类推。</span><span class="sxs-lookup"><span data-stu-id="69061-140">0-18 could be one bin, another could be 19-35 and so on.</span></span> 

<span data-ttu-id="69061-141">使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：</span><span class="sxs-lookup"><span data-stu-id="69061-141">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

<span data-ttu-id="69061-142">使用 [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) 方法将数据规范化为箱。</span><span class="sxs-lookup"><span data-stu-id="69061-142">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) method.</span></span> <span data-ttu-id="69061-143">`maximumBinCount` 参数使你可以指定对数据进行分类所需的箱数。</span><span class="sxs-lookup"><span data-stu-id="69061-143">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="69061-144">在此示例中，数据将放入两个箱中。</span><span class="sxs-lookup"><span data-stu-id="69061-144">In this example, data will be put into two bins.</span></span>  

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="69061-145">分箱的结果为创建 `[0,200000,Infinity]` 的分箱边界。</span><span class="sxs-lookup"><span data-stu-id="69061-145">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="69061-146">因此，所得到的箱为 `[0,1,1]`，因为第一个观测在 0-200,000 之间，而其他观测则大于 200,000 但小于无穷大。</span><span class="sxs-lookup"><span data-stu-id="69061-146">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="69061-147">使用分类数据</span><span class="sxs-lookup"><span data-stu-id="69061-147">Work with categorical data</span></span>

<span data-ttu-id="69061-148">在用于生成机器学习模型之前，需要将非数字分类数据转换为数字。</span><span class="sxs-lookup"><span data-stu-id="69061-148">Non-numeric categorical data needs to be converted to a number before being used to build a machine learning model.</span></span> 

<span data-ttu-id="69061-149">使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：</span><span class="sxs-lookup"><span data-stu-id="69061-149">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
CarData[] cars = new CarData[] 
{
    new CarData
    {
        Color="Red",
        VehicleType="SUV"
    },
    new CarData
    {
        Color="Blue",
        VehicleType="Sedan"
    },
    new CarData
    {
        Color="Black",
        VehicleType="SUV"
    }
};
```

<span data-ttu-id="69061-150">分类 `VehicleType` 属性可以使用 [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) 方法转换为数字。</span><span class="sxs-lookup"><span data-stu-id="69061-150">The categorical `VehicleType` property can be converted into a number using the [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) method.</span></span> 

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

<span data-ttu-id="69061-151">生成的转换将 `VehicleType` 的文本值转换为数字。</span><span class="sxs-lookup"><span data-stu-id="69061-151">The resulting transform converts the text value of `VehicleType` to a number.</span></span> <span data-ttu-id="69061-152">应用转换后，`VehicleType` 列中的条目将变为以下内容：</span><span class="sxs-lookup"><span data-stu-id="69061-152">The entries in the `VehicleType` column become the following when the transform is applied:</span></span> 

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a><span data-ttu-id="69061-153">使用文本数据</span><span class="sxs-lookup"><span data-stu-id="69061-153">Work with text data</span></span>

<span data-ttu-id="69061-154">在用于生成机器学习模型之前，需要将文本数据转换为数字。</span><span class="sxs-lookup"><span data-stu-id="69061-154">Text data needs to be transformed into numbers before using it to build a machine learning model.</span></span> <span data-ttu-id="69061-155">访问[转换页面](../resources/transforms.md)，获取更详细的文本转换列表和说明。</span><span class="sxs-lookup"><span data-stu-id="69061-155">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="69061-156">使用类似以下已加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的数据的数据：</span><span class="sxs-lookup"><span data-stu-id="69061-156">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
ReviewData[] reviews = new ReviewData[]
{
    new ReviewData
    {
        Description="This is a good product",
        Rating=4.7f
    },
    new ReviewData
    {
        Description="This is a bad product",
        Rating=2.3f
    }
};
```

<span data-ttu-id="69061-157">将文本转换为数字向量表示形式的最简单步骤是使用 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 方法。</span><span class="sxs-lookup"><span data-stu-id="69061-157">The minimum step to convert text to a numerical vector representation is to use the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="69061-158">通过使用 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 转换，将一系列转换应用于输入文本列，从而生成表示 lp 规范化字词和 n 元语法的数字向量。</span><span class="sxs-lookup"><span data-stu-id="69061-158">By using the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) transform, a series of transformations is applied to the input text column resulting in a numerical vector representing the lp-normalized word and character ngrams.</span></span> 

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="69061-159">生成的转换会将 `Description` 列中的文本值转换为类似以下输出的数字向量：</span><span class="sxs-lookup"><span data-stu-id="69061-159">The resulting transform would convert the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="69061-160">将复杂的文本处理步骤合并到一个 [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) 中以消除干扰，并可能根据需要减少所需的处理资源量。</span><span class="sxs-lookup"><span data-stu-id="69061-160">Combine complex text processing steps into an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) to remove noise and potentially reduce the amount of required processing resources as needed.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="69061-161">`textEstimator` 包含 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 方法执行的一组操作。</span><span class="sxs-lookup"><span data-stu-id="69061-161">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="69061-162">更复杂管道的好处在于对应用于数据的转换的控制和可见性。</span><span class="sxs-lookup"><span data-stu-id="69061-162">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span> 

<span data-ttu-id="69061-163">以第一个条目为例，以下是对 `textEstimator` 定义的转换步骤产生的结果的详细说明：</span><span class="sxs-lookup"><span data-stu-id="69061-163">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="69061-164">**原始文本：This is a good product**</span><span class="sxs-lookup"><span data-stu-id="69061-164">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="69061-165">Transform</span><span class="sxs-lookup"><span data-stu-id="69061-165">Transform</span></span> | <span data-ttu-id="69061-166">说明</span><span class="sxs-lookup"><span data-stu-id="69061-166">Description</span></span> | <span data-ttu-id="69061-167">结果</span><span class="sxs-lookup"><span data-stu-id="69061-167">Result</span></span>
|--|--|--|
|<span data-ttu-id="69061-168">1.NormalizeText</span><span class="sxs-lookup"><span data-stu-id="69061-168">1. NormalizeText</span></span> | <span data-ttu-id="69061-169">默认情况下将所有字母转换为小写字母</span><span class="sxs-lookup"><span data-stu-id="69061-169">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="69061-170">this is a good product</span><span class="sxs-lookup"><span data-stu-id="69061-170">this is a good product</span></span>
|<span data-ttu-id="69061-171">2.TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="69061-171">2. TokenizeWords</span></span> | <span data-ttu-id="69061-172">将字符串拆分为单独的字词</span><span class="sxs-lookup"><span data-stu-id="69061-172">Splits string into individual words</span></span> | <span data-ttu-id="69061-173">["this","is","a","good","product"]</span><span class="sxs-lookup"><span data-stu-id="69061-173">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="69061-174">3.RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="69061-174">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="69061-175">删除 *is* 和 *a* 等非索引字</span><span class="sxs-lookup"><span data-stu-id="69061-175">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="69061-176">["good","product"]</span><span class="sxs-lookup"><span data-stu-id="69061-176">["good","product"]</span></span>
|<span data-ttu-id="69061-177">4.MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="69061-177">4. MapValueToKey</span></span> | <span data-ttu-id="69061-178">根据输入数据将值映射到键（类别）</span><span class="sxs-lookup"><span data-stu-id="69061-178">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="69061-179">[1,2]</span><span class="sxs-lookup"><span data-stu-id="69061-179">[1,2]</span></span>
|<span data-ttu-id="69061-180">5.ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="69061-180">5. ProduceNGrams</span></span> | <span data-ttu-id="69061-181">将文本转换为连续单词的序列</span><span class="sxs-lookup"><span data-stu-id="69061-181">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="69061-182">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="69061-182">[1,1,1,0,0]</span></span>
|<span data-ttu-id="69061-183">6.NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="69061-183">6. NormalizeLpNorm</span></span> | <span data-ttu-id="69061-184">按缩放的 lp 规范缩放输入</span><span class="sxs-lookup"><span data-stu-id="69061-184">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="69061-185">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="69061-185">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
