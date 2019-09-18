---
title: 从文件和其他源加载数据
description: 本操作说明演示如何将数据加载到 ML.NET 中进行处理和训练。 最初存储在文件或其他数据源（例如数据库、JSON、XML 或内存中集合）中的数据。
ms.date: 09/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 4008f38bf4a20113a3f5c865e38222e5b82f2acc
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991365"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="5b60f-104">从文件和其他源加载数据</span><span class="sxs-lookup"><span data-stu-id="5b60f-104">Load data from files and other sources</span></span>

<span data-ttu-id="5b60f-105">本操作说明演示如何将数据加载到 ML.NET 中进行处理和训练。</span><span class="sxs-lookup"><span data-stu-id="5b60f-105">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="5b60f-106">最初存储在文件或其他数据源（例如数据库、JSON、XML 或内存中集合）中的数据。</span><span class="sxs-lookup"><span data-stu-id="5b60f-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="5b60f-107">创建数据模型</span><span class="sxs-lookup"><span data-stu-id="5b60f-107">Create the data model</span></span>

<span data-ttu-id="5b60f-108">ML.NET 允许通过类定义数据模型。</span><span class="sxs-lookup"><span data-stu-id="5b60f-108">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="5b60f-109">例如，给定以下输入数据：</span><span class="sxs-lookup"><span data-stu-id="5b60f-109">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="5b60f-110">创建一个表示以下代码片段的数据模型：</span><span class="sxs-lookup"><span data-stu-id="5b60f-110">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="5b60f-111">使用列特性注释数据模型</span><span class="sxs-lookup"><span data-stu-id="5b60f-111">Annotating the data model with column attributes</span></span>

<span data-ttu-id="5b60f-112">特性为 ML.NET 提供有关数据模型和数据源的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b60f-112">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="5b60f-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) 特性指定属性的列索引。</span><span class="sxs-lookup"><span data-stu-id="5b60f-113">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b60f-114">只有从文件加载数据时才需要 [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)。</span><span class="sxs-lookup"><span data-stu-id="5b60f-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="5b60f-115">将列加载为：</span><span class="sxs-lookup"><span data-stu-id="5b60f-115">Load columns as:</span></span>

- <span data-ttu-id="5b60f-116">单个列，例如 `HousingData` 类中的 `Size` 和 `CurrentPrices`。</span><span class="sxs-lookup"><span data-stu-id="5b60f-116">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="5b60f-117">以向量的形式一次加载多个列，例如 `HousingData` 类中的 `HistoricalPrices`。</span><span class="sxs-lookup"><span data-stu-id="5b60f-117">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="5b60f-118">如果有一个向量属性，请在数据模型中向该属性应用 [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 特性。</span><span class="sxs-lookup"><span data-stu-id="5b60f-118">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="5b60f-119">请务必注意，向量中的所有元素必须为相同的类型。</span><span class="sxs-lookup"><span data-stu-id="5b60f-119">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="5b60f-120">保持列与列之间的分隔状态可以提高特征工程的易用性和灵活性，但是对于非常多的列，在单个列上操作会对训练速度产生影响。</span><span class="sxs-lookup"><span data-stu-id="5b60f-120">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="5b60f-121">ML.NET 通过列名称进行操作。</span><span class="sxs-lookup"><span data-stu-id="5b60f-121">ML.NET Operates through column names.</span></span> <span data-ttu-id="5b60f-122">如果要将某个列的名称更改为该属性名称以外的其他名称，请使用 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 特性。</span><span class="sxs-lookup"><span data-stu-id="5b60f-122">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="5b60f-123">创建内存中对象时，仍然使用该属性名称创建对象。</span><span class="sxs-lookup"><span data-stu-id="5b60f-123">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="5b60f-124">但是，对于数据处理和生成机器学习模型，ML.NET 使用 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 特性中提供的值覆盖并引用该属性。</span><span class="sxs-lookup"><span data-stu-id="5b60f-124">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="5b60f-125">从单个文件加载数据</span><span class="sxs-lookup"><span data-stu-id="5b60f-125">Load data from a single file</span></span>

<span data-ttu-id="5b60f-126">若要从文件加载数据，请使用 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 方法以及要加载的数据的数据模型。</span><span class="sxs-lookup"><span data-stu-id="5b60f-126">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="5b60f-127">由于 `separatorChar` 参数默认为制表符分隔，因此请根据需要为数据文件更改该参数。</span><span class="sxs-lookup"><span data-stu-id="5b60f-127">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="5b60f-128">如果文件有标头，请将 `hasHeader` 参数设置为 `true`，以忽略文件中的第一行并开始从第二行加载数据。</span><span class="sxs-lookup"><span data-stu-id="5b60f-128">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="5b60f-129">从多个文件加载数据</span><span class="sxs-lookup"><span data-stu-id="5b60f-129">Load data from multiple files</span></span>

<span data-ttu-id="5b60f-130">如果数据存储在多个文件中，只要数据架构相同，ML.NET 就允许从同一目录或多个目录中的多个文件加载数据。</span><span class="sxs-lookup"><span data-stu-id="5b60f-130">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="5b60f-131">从单个目录中的文件加载</span><span class="sxs-lookup"><span data-stu-id="5b60f-131">Load from files in a single directory</span></span>

<span data-ttu-id="5b60f-132">当所有数据文件位于同一目录中时，请在 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 方法中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="5b60f-132">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="5b60f-133">从多个目录中的文件加载</span><span class="sxs-lookup"><span data-stu-id="5b60f-133">Load from files in multiple directories</span></span>

<span data-ttu-id="5b60f-134">若要从多个目录加载数据，请使用 [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) 方法创建 [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)。</span><span class="sxs-lookup"><span data-stu-id="5b60f-134">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="5b60f-135">然后，使用 [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) 方法并指定单个文件路径（不能使用通配符）。</span><span class="sxs-lookup"><span data-stu-id="5b60f-135">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a><span data-ttu-id="5b60f-136">从关系数据库加载数据</span><span class="sxs-lookup"><span data-stu-id="5b60f-136">Load data from a relational database</span></span>

> [!NOTE]
> <span data-ttu-id="5b60f-137">DatabaseLoader 当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="5b60f-137">DatabaseLoader is currently in preview.</span></span> <span data-ttu-id="5b60f-138">引用 [Microsoft.ML.Experimental](https://www.nuget.org/packages/Microsoft.ML.Experimental/0.16.0-preview) 和 [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient/4.6.1) NuGet 包，即可使用该预览版。</span><span class="sxs-lookup"><span data-stu-id="5b60f-138">It can be used by referencing the [Microsoft.ML.Experimental](https://www.nuget.org/packages/Microsoft.ML.Experimental/0.16.0-preview) and [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient/4.6.1) NuGet packages.</span></span>

<span data-ttu-id="5b60f-139">ML.NET 支持从各种关系数据库中加载数据（包括 SQL Server、Azure SQL 数据库、Oracle、SQLite、PostgreSQL、Progress、IBM DB2 等），这些关系数据库由 [`System.Data`](xref:System.Data) 提供支持。</span><span class="sxs-lookup"><span data-stu-id="5b60f-139">ML.NET supports loading data from a variety of relational databases supported by [`System.Data`](xref:System.Data) that include SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2, and many more.</span></span>

<span data-ttu-id="5b60f-140">指定具有名为 `House` 的表和以下架构的数据库：</span><span class="sxs-lookup"><span data-stu-id="5b60f-140">Given a database with a table named `House` and the following schema:</span></span>

```SQL
CREATE TABLE [House] (
    [HouseId] int NOT NULL IDENTITY,
    [Size] real NOT NULL,
    [Price] real NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

<span data-ttu-id="5b60f-141">数据可以通过 `HouseData` 等类进行建模。</span><span class="sxs-lookup"><span data-stu-id="5b60f-141">The data can be modeled by a class like `HouseData`.</span></span>

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float Price { get; set; }
}
```

<span data-ttu-id="5b60f-142">然后，在应用程序中创建 `DatabaseLoader`。</span><span class="sxs-lookup"><span data-stu-id="5b60f-142">Then, inside of your application, create a `DatabaseLoader`.</span></span>

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

<span data-ttu-id="5b60f-143">定义连接字符串以及要在数据库上执行的 SQL 命令，并创建 `DatabaseSource` 实例。</span><span class="sxs-lookup"><span data-stu-id="5b60f-143">Define your connection string as well as the SQL command to be executed on the database and create a `DatabaseSource` instance.</span></span> <span data-ttu-id="5b60f-144">此示例使用具有文件路径的 LocalDB SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="5b60f-144">This sample uses a LocalDB SQL Server database with a file path.</span></span> <span data-ttu-id="5b60f-145">但是，DatabaseLoader 支持本地和云中数据库的任何其他有效连接字符串。</span><span class="sxs-lookup"><span data-stu-id="5b60f-145">However, DatabaseLoader supports any other valid connection string for databases on-premises and in the cloud.</span></span>

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size,Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance,connectionString,sqlCommand);
```

<span data-ttu-id="5b60f-146">最后，使用 `Load` 方法将数据加载到 [`IDataView`](xref:Microsoft.ML.IDataView)。</span><span class="sxs-lookup"><span data-stu-id="5b60f-146">Finally, use the `Load` method to load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="5b60f-147">从其他源加载数据</span><span class="sxs-lookup"><span data-stu-id="5b60f-147">Load data from other sources</span></span>

<span data-ttu-id="5b60f-148">除了加载存储在文件中的数据外，ML.NET 还支持从各种源加载数据，这些源包括但不限于：</span><span class="sxs-lookup"><span data-stu-id="5b60f-148">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="5b60f-149">内存中集合</span><span class="sxs-lookup"><span data-stu-id="5b60f-149">In-memory collections</span></span>
- <span data-ttu-id="5b60f-150">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="5b60f-150">JSON/XML</span></span>

<span data-ttu-id="5b60f-151">请注意，在使用流式处理源时，ML.NET 预计输入采用内存中集合的形式。</span><span class="sxs-lookup"><span data-stu-id="5b60f-151">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="5b60f-152">因此，在使用 JSON/XML 等源时，请确保将数据格式化为内存中集合。</span><span class="sxs-lookup"><span data-stu-id="5b60f-152">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="5b60f-153">给定以下内存中集合：</span><span class="sxs-lookup"><span data-stu-id="5b60f-153">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="5b60f-154">使用 [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) 方法将内存中集合加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中：</span><span class="sxs-lookup"><span data-stu-id="5b60f-154">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b60f-155">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) 假定其所加载的 [`IEnumerable`](xref:System.Collections.IEnumerable) 是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="5b60f-155">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
