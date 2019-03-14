---
title: 从多个文件加载数据用于机器学习处理 - ML.NET
description: 通过 ML.NET，了解如何从多个文件加载数据用于机器学习模型生成、培训和评分
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: fbf5e4b5ab9a1a686edb933bdec818fc532bbf42
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679016"
---
# <a name="load-data-from-multiple-files-for-machine-learning-processing---mlnet"></a><span data-ttu-id="5b633-103">从多个文件加载数据用于机器学习处理 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="5b633-103">Load data from multiple files for machine learning processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="5b633-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="5b633-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="5b633-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="5b633-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="5b633-106">此操作说明和相关示例目前使用的是 ML.NET 版本 0.10。</span><span class="sxs-lookup"><span data-stu-id="5b633-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="5b633-107">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="5b633-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="5b633-108">使用 `TextLoader`，将一组文件指定到 `Read` 方法。</span><span class="sxs-lookup"><span data-stu-id="5b633-108">Use the `TextLoader`, and specify an array of files to the `Read` method.</span></span> <span data-ttu-id="5b633-109">文件必须具有相同的架构（相同的列数量和类型）：</span><span class="sxs-lookup"><span data-stu-id="5b633-109">The files must have the same schema (same number and type of columns):</span></span>

* [<span data-ttu-id="5b633-110">示例文件1</span><span class="sxs-lookup"><span data-stu-id="5b633-110">Example file1</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.train)
* [<span data-ttu-id="5b633-111">示例文件2</span><span class="sxs-lookup"><span data-stu-id="5b633-111">Example file2</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.test)

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

// Now read the files (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(exampleFile1, exampleFile2);
```