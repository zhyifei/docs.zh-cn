---
title: 从文本文件加载数据以进行机器学习处理 - ML.NET
description: 通过 ML.NET，了解如何从文本文件加载数据用于机器学习模型生成、定型和评分
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 14b1f8c99da6f1b8da436d9afef5b2ac8d36ecae
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2019
ms.locfileid: "57843364"
---
# <a name="load-data-from-a-text-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="ad54d-103">从文本文件加载数据以进行机器学习处理 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="ad54d-103">Load data from a text file for machine learning processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="ad54d-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="ad54d-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="ad54d-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="ad54d-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="ad54d-106">此操作说明和相关示例目前使用的是 ML.NET 版本 0.10。</span><span class="sxs-lookup"><span data-stu-id="ad54d-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="ad54d-107">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="ad54d-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="ad54d-108">`TextLoader` 用于从文本文件加载数据。</span><span class="sxs-lookup"><span data-stu-id="ad54d-108">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="ad54d-109">需要在文本文件中指定数据列、类型及其位置。</span><span class="sxs-lookup"><span data-stu-id="ad54d-109">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="ad54d-110">注意，读取文件的某些列或多次读取同一列是完全可以接受的。</span><span class="sxs-lookup"><span data-stu-id="ad54d-110">Note that it's perfectly acceptable to read some columns of a file, or read the same column multiple times.</span></span>

<span data-ttu-id="ad54d-111">[示例文件](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt)：</span><span class="sxs-lookup"><span data-stu-id="ad54d-111">[Example file](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>

<!-- markdownlint-disable MD010 -->
```console
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse
```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="ad54d-112">从文本文件中加载数据：</span><span class="sxs-lookup"><span data-stu-id="ad54d-112">To load the data from a text file:</span></span>

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
