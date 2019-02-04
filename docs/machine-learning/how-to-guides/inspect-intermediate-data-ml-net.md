---
title: 在 ML.NET 管道处理期间检查中间数据值
description: 了解如何在 ML.NET 机器学习管道处理期间检查实际的中间数据值
ms.date: 01/30/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b3a554bf7cd88219a66f91a18b9d983bb91c0f0e
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675005"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a>在 ML.NET 管道处理期间检查中间数据值

在实验过程中，可能需要观察和验证给定时间点的数据处理结果。 由于 ML.NET 操作具有延迟性，生成的对象都是“预示”的数据，这并非易事。

可使用 `GetColumn<T>` 扩展方法检查中间数据。 它以 `IEnumerable` 的形式返回数据列的内容。

以下示例演示如何使用 `GetColumn<T>` 扩展方法：

[示例文件](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt)：
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```

类定义如下：

```csharp
public class InspectedRow
{
    [LoadColumn(0)]
    public bool IsOver50K { get; set; }
    [LoadColumn(1)]
    public string WorkClass { get; set; }
    [LoadColumn(2)]
    public string Education { get; set; }
    [LoadColumn(3)]
    public string MaritalStatus { get; set; }
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Read the data into a data view.
var data = mlContext.Data.ReadFromTextFile<InspectedRow>(dataPath, hasHeader: true);

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "WorkClass", "Education", "MaritalStatus");

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns =
    transformedData
        .GetColumn<string[]>(mlContext, "AllFeatures")
        .Take(20)
        .ToArray();
```
