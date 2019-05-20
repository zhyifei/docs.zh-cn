---
title: 准备数据
description: 了解如何在 ML.NET 中使用转换来操作和准备数据用于进行其他处理或建模。
author: luisquintanilla
ms.author: luquinta
ms.date: 05/03/2019
ms.custom: mvc, how-to
ms.openlocfilehash: 461a00c6ecc1d9a8b9caaca79f9d7905d2bb7528
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063461"
---
# <a name="prepare-data"></a>准备数据

了解如何使用 ML.NET 来准备数据用于进行其他处理或生成模型。

数据通常是不干净的和稀疏的。 此外，ML.NET 机器学习算法期望输入或特征位于单个数字向量中。 因此，数据准备的目标之一是将数据转换为 ML.NET 算法所期望的格式。 

## <a name="filter-data"></a>筛选数据

有时，并非数据集中的所有数据都与分析相关。 删除不相关数据的方法之一是筛选。 [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) 包含一组筛选操作，这些操作接收包含所有数据的 [`IDataView`](xref:Microsoft.ML.IDataView)，并返回仅包含关注数据点的 [IDataView](xref:Microsoft.ML.IDataView)。 值得注意的是，因为筛选操作不像 [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog) 中的操作那样是 [`IEstimator`](xref:Microsoft.ML.IEstimator%601) 或 [`ITransformer`](xref:Microsoft.ML.ITransformer)，所以它们不能作为 [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) 或 [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) 数据准备管道的一部分包含在内。 

使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：

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

若要根据列的值筛选数据，请使用 [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) 方法。

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

上述示例采用数据集中价格介于 200,000 和 1,000,000 之间的行。 应用此筛选器的结果为，将仅返回数据中的最后两行，并排除第一行，因为其价格为 100,000，不在指定范围之间。

## <a name="replace-missing-values"></a>替换缺失值

缺失值在数据集中是常见现象。 处理缺失值的一种方法是使用给定类型的默认值（如有）或其他有意义的值（例如数据中的平均值）替换它们。 

使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：

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

请注意，列表中最后一个元素的 `Price` 缺失值。 若要替换 `Price` 列中的缺失值，请使用 [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) 方法填充该缺失值。

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) 仅适用于数字数据。

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET 支持各种[替换模式](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode)。 上述示例使用 `Mean` 替换模式，该模式将使用该列的平均值填充缺失值。 替换的结果使用 200,000 填充数据中最后一个元素的 `Price` 属性，因为它是 100,000 和 300,000 的平均值。 

## <a name="use-normalizers"></a>使用规范化程序

[规范化](https://en.wikipedia.org/wiki/Feature_scaling)是一种数据预处理技术，用于标准化比例不同的特征，这有助于算法更快地融合。 例如，年龄和收入等值的范围存在明显差异，年龄的范围通常为 0-100，而收入的范围通常为零到数千。 访问[转换页面](../resources/transforms.md)，获取更详细的规范化转换列表和说明。 

### <a name="min-max-normalization"></a>最小-最大规范化

使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：

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

使用 [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) 方法通过最小-最大规范化来规范化数据。

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

原始价格值 `[200000,100000]` 使用 `MinMax` 规范化公式转换为 `[ 1, 0.5 ]`，该公式生成范围在 0-1 之间的输出值。

### <a name="binning"></a>分箱

[分箱](https://en.wikipedia.org/wiki/Data_binning)将连续值转换为输入的离散表示形式。 例如，假设某个特征为年龄。 分箱不使用实际年龄值，而是为该值创建范围。 0-18 可以是一个箱，另一个箱可以是 19-35，依此类推。 

使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：

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

使用 [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) 方法将数据规范化为箱。 `maximumBinCount` 参数使你可以指定对数据进行分类所需的箱数。 在此示例中，数据将放入两个箱中。  

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

分箱的结果为创建 `[0,200000,Infinity]` 的分箱边界。 因此，所得到的箱为 `[0,1,1]`，因为第一个观测在 0-200,000 之间，而其他观测则大于 200,000 但小于无穷大。

## <a name="work-with-categorical-data"></a>使用分类数据

在用于生成机器学习模型之前，需要将非数字分类数据转换为数字。 

使用加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的以下输入数据：

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

分类 `VehicleType` 属性可以使用 [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) 方法转换为数字。 

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

生成的转换将 `VehicleType` 的文本值转换为数字。 应用转换后，`VehicleType` 列中的条目将变为以下内容： 

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a>使用文本数据

在用于生成机器学习模型之前，需要将文本数据转换为数字。 访问[转换页面](../resources/transforms.md)，获取更详细的文本转换列表和说明。

使用类似以下已加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的数据的数据：

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

将文本转换为数字向量表示形式的最简单步骤是使用 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 方法。 通过使用 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 转换，将一系列转换应用于输入文本列，从而生成表示 lp 规范化字词和 n 元语法的数字向量。 

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

生成的转换会将 `Description` 列中的文本值转换为类似以下输出的数字向量：

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

将复杂的文本处理步骤合并到一个 [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) 中以消除干扰，并可能根据需要减少所需的处理资源量。

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator` 包含 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 方法执行的一组操作。 更复杂管道的好处在于对应用于数据的转换的控制和可见性。 

以第一个条目为例，以下是对 `textEstimator` 定义的转换步骤产生的结果的详细说明：

**原始文本：This is a good product**

|Transform | 说明 | 结果
|--|--|--|
|1.NormalizeText | 默认情况下将所有字母转换为小写字母 | this is a good product
|2.TokenizeWords | 将字符串拆分为单独的字词 | ["this","is","a","good","product"]
|3.RemoveDefaultStopWords | 删除 *is* 和 *a* 等非索引字 | ["good","product"]
|4.MapValueToKey | 根据输入数据将值映射到键（类别） |  [1,2]
|5.ProduceNGrams | 将文本转换为连续单词的序列 | [1,1,1,0,0]
|6.NormalizeLpNorm | 按缩放的 lp 规范缩放输入 | [ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]
