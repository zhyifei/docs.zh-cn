---
title: 加载数据
description: 将数据文件和流式处理数据加载到 ML.NET 中
ms.date: 05/03/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 6edcc92b610e2e1f5e21c371b9f0aefd0b216d31
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063651"
---
# <a name="load-data-from-file-and-in-memory-sources"></a><span data-ttu-id="b5d7e-103">从文件和内存中源加载数据</span><span class="sxs-lookup"><span data-stu-id="b5d7e-103">Load data from file and in-memory sources</span></span>

<span data-ttu-id="b5d7e-104">本操作说明演示如何将数据加载到 ML.NET 中进行处理和训练。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-104">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="b5d7e-105">数据最初存储在文件或实时/流式处理数据源中。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-105">The data is originally stored in files or real-time / streaming data sources.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="b5d7e-106">创建数据模型</span><span class="sxs-lookup"><span data-stu-id="b5d7e-106">Create the data model</span></span>

<span data-ttu-id="b5d7e-107">ML.NET 允许通过类定义数据模型。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-107">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="b5d7e-108">例如，给定以下输入数据：</span><span class="sxs-lookup"><span data-stu-id="b5d7e-108">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="b5d7e-109">创建一个表示以下代码片段的数据模型：</span><span class="sxs-lookup"><span data-stu-id="b5d7e-109">Create a data model that represents the snippet below:</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }
 
    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="b5d7e-110">使用列特性注释数据模型</span><span class="sxs-lookup"><span data-stu-id="b5d7e-110">Annotating the data model with column attributes</span></span>

<span data-ttu-id="b5d7e-111">特性为 ML.NET 提供有关数据模型和数据源的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-111">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="b5d7e-112">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) 特性指定属性的列索引。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-112">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5d7e-113">只有从文件加载数据时才需要 [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="b5d7e-114">将列加载为：</span><span class="sxs-lookup"><span data-stu-id="b5d7e-114">Load columns as:</span></span> 
- <span data-ttu-id="b5d7e-115">单个列，例如 `HousingData` 类中的 `Size` 和 `CurrentPrices`。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-115">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="b5d7e-116">以向量的形式一次加载多个列，例如 `HousingData` 类中的 `HistoricalPrices`。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-116">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="b5d7e-117">如果有一个向量属性，请在数据模型中向该属性应用 [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 特性。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-117">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="b5d7e-118">请务必注意，向量中的所有元素必须为相同的类型。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-118">It's important to note that all of the elements in the vector need to be the same type.</span></span>

<span data-ttu-id="b5d7e-119">ML.NET 通过列名称进行操作。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-119">ML.NET Operates through column names.</span></span> <span data-ttu-id="b5d7e-120">如果要将某个列的名称更改为该属性名称以外的其他名称，请使用 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 特性。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-120">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="b5d7e-121">创建内存中对象时，仍然使用该属性名称创建对象。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-121">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="b5d7e-122">但是，对于数据处理和生成机器学习模型，ML.NET 使用 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 特性中提供的值覆盖并引用该属性。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-122">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="b5d7e-123">从单个文件加载数据</span><span class="sxs-lookup"><span data-stu-id="b5d7e-123">Load data from a single file</span></span>

<span data-ttu-id="b5d7e-124">若要从文件加载数据，请使用 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 方法以及要加载的数据的数据模型。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-124">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="b5d7e-125">由于 `separatorChar` 参数默认为制表符分隔，因此请根据需要为数据文件更改该参数。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-125">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="b5d7e-126">如果文件有标头，请将 `hasHeader` 参数设置为 `true`，以忽略文件中的第一行并开始从第二行加载数据。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-126">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="b5d7e-127">从多个文件加载数据</span><span class="sxs-lookup"><span data-stu-id="b5d7e-127">Load data from multiple files</span></span>

<span data-ttu-id="b5d7e-128">如果数据存储在多个文件中，只要数据架构相同，ML.NET 就允许从同一目录或多个目录中的多个文件加载数据。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-128">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="b5d7e-129">从单个目录中的文件加载</span><span class="sxs-lookup"><span data-stu-id="b5d7e-129">Load from files in a single directory</span></span>

<span data-ttu-id="b5d7e-130">当所有数据文件位于同一目录中时，请在 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 方法中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-130">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="b5d7e-131">从多个目录中的文件加载</span><span class="sxs-lookup"><span data-stu-id="b5d7e-131">Load from files in multiple directories</span></span>

<span data-ttu-id="b5d7e-132">若要从多个目录加载数据，请使用 [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) 方法创建 [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-132">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="b5d7e-133">然后，使用 [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) 方法并指定单个文件路径（不能使用通配符）。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-133">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-streaming-source"></a><span data-ttu-id="b5d7e-134">从流式处理源加载数据</span><span class="sxs-lookup"><span data-stu-id="b5d7e-134">Load data from a streaming source</span></span>

<span data-ttu-id="b5d7e-135">除了加载存储在磁盘上的数据外，ML.NET 还支持从各种流式处理源加载数据，这些源包括但不限于：</span><span class="sxs-lookup"><span data-stu-id="b5d7e-135">In addition to loading data stored on disk, ML.NET supports loading data from various streaming sources that include but are not limited to:</span></span>

- <span data-ttu-id="b5d7e-136">内存中集合</span><span class="sxs-lookup"><span data-stu-id="b5d7e-136">In-memory collections</span></span>
- <span data-ttu-id="b5d7e-137">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="b5d7e-137">JSON/XML</span></span>
- <span data-ttu-id="b5d7e-138">数据库</span><span class="sxs-lookup"><span data-stu-id="b5d7e-138">Databases</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5d7e-139">请注意，在使用流式处理源时，ML.NET 预计输入采用内存中集合的形式。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-139">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="b5d7e-140">因此，在使用 JSON/XML 等源时，请确保将数据格式化为内存中集合。</span><span class="sxs-lookup"><span data-stu-id="b5d7e-140">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="b5d7e-141">给定以下内存中集合：</span><span class="sxs-lookup"><span data-stu-id="b5d7e-141">Given the following in-memory collection:</span></span>

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

<span data-ttu-id="b5d7e-142">使用 [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) 方法将内存中集合加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中：</span><span class="sxs-lookup"><span data-stu-id="b5d7e-142">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
