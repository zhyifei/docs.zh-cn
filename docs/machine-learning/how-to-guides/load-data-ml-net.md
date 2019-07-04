---
title: 从文件和其他源加载数据
description: 本操作说明演示如何将数据加载到 ML.NET 中进行处理和训练。 最初存储在文件或其他数据源（例如数据库、JSON、XML 或内存中集合）中的数据。
ms.date: 06/25/2019
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: fafbe3fed9e3f0b509eda4f9d8967965bde19767
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397746"
---
# <a name="load-data-from-files-and-other-sources"></a>从文件和其他源加载数据

本操作说明演示如何将数据加载到 ML.NET 中进行处理和训练。 最初存储在文件或其他数据源（例如数据库、JSON、XML 或内存中集合）中的数据。

## <a name="create-the-data-model"></a>创建数据模型

ML.NET 允许通过类定义数据模型。 例如，给定以下输入数据：

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

创建一个表示以下代码片段的数据模型：

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

### <a name="annotating-the-data-model-with-column-attributes"></a>使用列特性注释数据模型

特性为 ML.NET 提供有关数据模型和数据源的详细信息。

[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) 特性指定属性的列索引。

> [!IMPORTANT]
> 只有从文件加载数据时才需要 [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)。

将列加载为： 
- 单个列，例如 `HousingData` 类中的 `Size` 和 `CurrentPrices`。
- 以向量的形式一次加载多个列，例如 `HousingData` 类中的 `HistoricalPrices`。

如果有一个向量属性，请在数据模型中向该属性应用 [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 特性。 请务必注意，向量中的所有元素必须为相同的类型。

ML.NET 通过列名称进行操作。 如果要将某个列的名称更改为该属性名称以外的其他名称，请使用 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 特性。 创建内存中对象时，仍然使用该属性名称创建对象。 但是，对于数据处理和生成机器学习模型，ML.NET 使用 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 特性中提供的值覆盖并引用该属性。

## <a name="load-data-from-a-single-file"></a>从单个文件加载数据

若要从文件加载数据，请使用 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 方法以及要加载的数据的数据模型。 由于 `separatorChar` 参数默认为制表符分隔，因此请根据需要为数据文件更改该参数。 如果文件有标头，请将 `hasHeader` 参数设置为 `true`，以忽略文件中的第一行并开始从第二行加载数据。

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a>从多个文件加载数据

如果数据存储在多个文件中，只要数据架构相同，ML.NET 就允许从同一目录或多个目录中的多个文件加载数据。

### <a name="load-from-files-in-a-single-directory"></a>从单个目录中的文件加载

当所有数据文件位于同一目录中时，请在 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 方法中使用通配符。

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a>从多个目录中的文件加载

若要从多个目录加载数据，请使用 [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) 方法创建 [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)。 然后，使用 [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) 方法并指定单个文件路径（不能使用通配符）。

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-other-sources"></a>从其他源加载数据

除了加载存储在文件中的数据外，ML.NET 还支持从各种源加载数据，这些源包括但不限于：

- 内存中集合
- JSON/XML
- 数据库

请注意，在使用流式处理源时，ML.NET 预计输入采用内存中集合的形式。 因此，在使用 JSON/XML 等源时，请确保将数据格式化为内存中集合。

给定以下内存中集合：

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

使用 [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) 方法将内存中集合加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中：

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
