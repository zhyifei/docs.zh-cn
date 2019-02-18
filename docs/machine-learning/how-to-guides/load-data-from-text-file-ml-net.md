---
title: 从文本文件加载数据以进行机器学习处理 - ML.NET
description: 通过 ML.NET，了解如何从文本文件加载数据用于机器学习模型生成、定型和评分
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 70c7ccdeaa27b78a412c2bc82f524d4bf42a740a
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091703"
---
# <a name="load-data-from-a-text-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="a388f-103">从文本文件加载数据以进行机器学习处理 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="a388f-103">Load data from a text file for machine learning processing - ML.NET</span></span>

<span data-ttu-id="a388f-104">`TextLoader` 用于从文本文件加载数据。</span><span class="sxs-lookup"><span data-stu-id="a388f-104">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="a388f-105">需要在文本文件中指定数据列、类型及其位置。</span><span class="sxs-lookup"><span data-stu-id="a388f-105">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="a388f-106">注意，读取文件的某些列或多次读取同一列是完全可以接受的。</span><span class="sxs-lookup"><span data-stu-id="a388f-106">Note that it's perfectly acceptable to read some columns of a file, or read the same column multiple times.</span></span>

<span data-ttu-id="a388f-107">[示例文件](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt)：</span><span class="sxs-lookup"><span data-stu-id="a388f-107">[Example file](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>

```console
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse
```

<span data-ttu-id="a388f-108">从文本文件中加载数据：</span><span class="sxs-lookup"><span data-stu-id="a388f-108">To load the data from a text file:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // A boolean column depicting the 'target label'.
        new TextLoader.Column("IsOver50k",DataKind.BL,0),
        // Three text columns.
        new TextLoader.Column("WorkClass",DataKind.TX,1),
        new TextLoader.Column("Education",DataKind.TX,2),
        new TextLoader.Column("MaritalStatus",DataKind.TX,3)
    },
    hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(dataPath);
```