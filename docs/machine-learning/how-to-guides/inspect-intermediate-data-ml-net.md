---
title: 在 ML.NET 处理期间检查中间数据值
description: 了解如何在 ML.NET 机器学习管道处理期间检查实际的中间数据值
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 06c4a473841db62a10dfc24025f842df7ae2c583
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063519"
---
# <a name="inspect-intermediate-data-values-during-processing"></a><span data-ttu-id="c10f9-103">在处理期间检查中间数据值</span><span class="sxs-lookup"><span data-stu-id="c10f9-103">Inspect intermediate data values during processing</span></span>

<span data-ttu-id="c10f9-104">了解如何在 ML.NET 的加载、处理和训练步骤中检查值。</span><span class="sxs-lookup"><span data-stu-id="c10f9-104">Learn how to inspect values during loading, processing and training steps in ML.NET.</span></span>

<span data-ttu-id="c10f9-105">可以在 ML.NET 中以各种方式检查加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中的如下所示的数据。</span><span class="sxs-lookup"><span data-stu-id="c10f9-105">Data like the one represented below which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView) can be inspected in various ways in ML.NET.</span></span>
 
```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

## <a name="convert-idataview-to-ienumerable"></a><span data-ttu-id="c10f9-106">将 IDataView 转换为 IEnumerable</span><span class="sxs-lookup"><span data-stu-id="c10f9-106">Convert IDataView to IEnumerable</span></span>

<span data-ttu-id="c10f9-107">检查 [`IDataView`](xref:Microsoft.ML.IDataView) 的值的最快方法之一是将其转换为 [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)。</span><span class="sxs-lookup"><span data-stu-id="c10f9-107">One of the quickest ways to inspect the values of an [`IDataView`](xref:Microsoft.ML.IDataView) is to convert it to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span> <span data-ttu-id="c10f9-108">若要将 [`IDataView`](xref:Microsoft.ML.IDataView) 转换为 [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)，请使用 [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) 方法。</span><span class="sxs-lookup"><span data-stu-id="c10f9-108">To convert an [`IDataView`](xref:Microsoft.ML.IDataView) to [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) use the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span> 

<span data-ttu-id="c10f9-109">若要优化性能，请将 `reuseRowObject` 的值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="c10f9-109">To optimize performance, set the value of `reuseRowObject` to `true`.</span></span> <span data-ttu-id="c10f9-110">如果这样做，将在评估当前行的数据时延迟填充相同的对象，而不是为数据集中的每一行创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="c10f9-110">Doing so will lazily populate the same object with the data of the current row as it's being evaluated as opposed to creating a new object for each row in the dataset.</span></span>

```csharp
// Create an IEnumerable of HousingData objects from IDataView
IEnumerable<HousingData> housingDataEnumerable =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: true);

// Iterate over each row
foreach (HousingData row in housingDataEnumerable)
{
    // Do something (print out Size property) with current Housing Data object being evaluated
    Console.WriteLine(row.Size);
}
```

<span data-ttu-id="c10f9-111">如果只需要访问部分数据或特定索引，请使用 [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) 并将 `reuseRowObject` 参数值设置为 `false`，以便为数据集中每个请求的行创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="c10f9-111">If you only need access to a portion of the data or specific indices, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) and set the `reuseRowObject` parameter value to `false` so a new object is created for each of the requested rows in the dataset.</span></span> <span data-ttu-id="c10f9-112">然后，将 [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) 转换为数组或列表。</span><span class="sxs-lookup"><span data-stu-id="c10f9-112">Then, convert the [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) to an array or list.</span></span>

> [!WARNING]
> <span data-ttu-id="c10f9-113">将 [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) 的结果转换为数组或列表会将所有请求的 [`IDataView`](xref:Microsoft.ML.IDataView) 行加载到内存中，这可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="c10f9-113">Converting the result of [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) to an array or list will load all the requested [`IDataView`](xref:Microsoft.ML.IDataView) rows into memory which may affect performance.</span></span>

<span data-ttu-id="c10f9-114">创建集合后，可以对数据执行操作。</span><span class="sxs-lookup"><span data-stu-id="c10f9-114">Once the collection has been created, you can perform operations on the data.</span></span> <span data-ttu-id="c10f9-115">下面的代码片段获取数据集中的前三行并计算当前的平均价格。</span><span class="sxs-lookup"><span data-stu-id="c10f9-115">The code snippet below takes the first three rows in the dataset and calculates the average current price.</span></span>

```csharp
// Create an Array of HousingData objects from IDataView
HousingData[] housingDataArray =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: false)
        .Take(3)
        .ToArray();

// Calculate Average CurrentPrice of First Three Elements
HousingData firstRow = housingDataArray[0];
HousingData secondRow = housingDataArray[1];
HousingData thirdRow = housingDataArray[2];
float averageCurrentPrice = (firstRow.CurrentPrice + secondRow.CurrentPrice + thirdRow.CurrentPrice) / 3;
``` 

## <a name="inspect-values-in-a-single-column"></a><span data-ttu-id="c10f9-116">检查单个列中的值</span><span class="sxs-lookup"><span data-stu-id="c10f9-116">Inspect values in a single column</span></span>

<span data-ttu-id="c10f9-117">在模型生成过程中的任何时候，都可以使用 [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) 方法访问 [`IDataView`](xref:Microsoft.ML.IDataView) 的单个列中的值。</span><span class="sxs-lookup"><span data-stu-id="c10f9-117">At any point in the model building process, values in a single column of an [`IDataView`](xref:Microsoft.ML.IDataView) can be accessed using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span> <span data-ttu-id="c10f9-118">[`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) 方法将单个列中的所有值都返回为 [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)。</span><span class="sxs-lookup"><span data-stu-id="c10f9-118">The [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method returns all of the values in a single column as an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span>

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a><span data-ttu-id="c10f9-119">一次检查一行 IDataView 值</span><span class="sxs-lookup"><span data-stu-id="c10f9-119">Inspect IDataView values one row at a time</span></span>

<span data-ttu-id="c10f9-120">[`IDataView`](xref:Microsoft.ML.IDataView) 延迟求值。</span><span class="sxs-lookup"><span data-stu-id="c10f9-120">[`IDataView`](xref:Microsoft.ML.IDataView) is lazily evaluated.</span></span> <span data-ttu-id="c10f9-121">若要循环访问 [`IDataView`](xref:Microsoft.ML.IDataView) 的各行，而不按本文档前面部分所示转换为 [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)，请通过使用 [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) 方法并传入 [`IDataView`](xref:Microsoft.ML.IDataView) 的 [DataViewSchema](xref:Microsoft.ML.DataViewSchema) 作为参数来创建 [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor)。</span><span class="sxs-lookup"><span data-stu-id="c10f9-121">To iterate over the rows of an [`IDataView`](xref:Microsoft.ML.IDataView) without converting to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) as demonstrated in previous sections of this document, create a [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) by using the [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) method and passing in the [DataViewSchema](xref:Microsoft.ML.DataViewSchema) of your [`IDataView`](xref:Microsoft.ML.IDataView) as a parameter.</span></span> <span data-ttu-id="c10f9-122">然后，若要循环访问各行，请使用 [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) 游标方法以及 [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) 委托从每个列中提取相应的值。</span><span class="sxs-lookup"><span data-stu-id="c10f9-122">Then, to iterate over rows, use the [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) cursor method along with [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) delegates to extract the respective values from each of the columns.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c10f9-123">出于性能考虑，ML.NET 中的向量使用 [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) 而不是本机集合类型（即 `Vector`,`float[]`）。</span><span class="sxs-lookup"><span data-stu-id="c10f9-123">For performance purposes, vectors in ML.NET use [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) instead of native collection types (that is, `Vector`,`float[]`).</span></span> 

```csharp
// Get DataViewSchema of IDataView
DataViewSchema columns = data.Schema;

// Create DataViewCursor
using (DataViewRowCursor cursor = data.GetRowCursor(columns))
{
    // Define variables where extracted values will be stored to
    float size = default;
    VBuffer<float> historicalPrices = default;
    float currentPrice = default;

    // Define delegates for extracting values from columns
    ValueGetter<float> sizeDelegate = cursor.GetGetter<float>(columns[0]);
    ValueGetter<VBuffer<float>> historicalPriceDelegate = cursor.GetGetter<VBuffer<float>>(columns[1]);
    ValueGetter<float> currentPriceDelegate = cursor.GetGetter<float>(columns[2]);
    
    // Iterate over each row
    while (cursor.MoveNext())
    {
        //Get values from respective columns
        sizeDelegate.Invoke(ref size);
        historicalPriceDelegate.Invoke(ref historicalPrices);
        currentPriceDelegate.Invoke(ref currentPrice);
    }
}
```

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a><span data-ttu-id="c10f9-124">预览数据子集的预处理或训练结果</span><span class="sxs-lookup"><span data-stu-id="c10f9-124">Preview result of pre-processing or training on a subset of the data</span></span>

> [!WARNING]
> <span data-ttu-id="c10f9-125">请勿在生产代码中使用 `Preview`，因为它专用于调试，可能会降低性能。</span><span class="sxs-lookup"><span data-stu-id="c10f9-125">Do not use `Preview` in production code because it is intended for debugging and may reduce performance.</span></span>

<span data-ttu-id="c10f9-126">模型生成过程是实验性的和迭代的。</span><span class="sxs-lookup"><span data-stu-id="c10f9-126">The model building process is experimental and iterative.</span></span> <span data-ttu-id="c10f9-127">若要预览对数据子集预处理或训练机器学习模型后的数据，请使用可返回 [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview) 的 [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) 方法。</span><span class="sxs-lookup"><span data-stu-id="c10f9-127">To preview what data would look like after pre-processing or training a machine learning model on a subset of the data, use the [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) method which returns a [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span></span> <span data-ttu-id="c10f9-128">其结果为一个具有 `ColumnView` 和 `RowView` 属性的对象，这两个属性都是 [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) 并包含特定列或行中的值。</span><span class="sxs-lookup"><span data-stu-id="c10f9-128">The result is an object with `ColumnView` and `RowView` properties which are both an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) and contain the values in a particular column or row.</span></span> <span data-ttu-id="c10f9-129">使用 `maxRows` 参数指定要应用转换的行数。</span><span class="sxs-lookup"><span data-stu-id="c10f9-129">Specify the number of rows to apply the transformation to with the `maxRows` parameter.</span></span>

![数据调试器预览对象](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

<span data-ttu-id="c10f9-131">检查 [`IDataView`](xref:Microsoft.ML.IDataView) 的结果将与下面类似：</span><span class="sxs-lookup"><span data-stu-id="c10f9-131">The result of inspecting an [`IDataView`](xref:Microsoft.ML.IDataView) would look similar to the following:</span></span>

![数据调试器预览行视图](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
