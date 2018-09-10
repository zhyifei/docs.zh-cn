---
title: 查询对象集合（C# 中的 LINQ）
description: 了解如何使用 C# 中的 LINQ 查询集合。
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 7bc59e7009f9ae8d8f66c24e9519d9100404c9c4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511379"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="3d12c-103">查询对象的集合</span><span class="sxs-lookup"><span data-stu-id="3d12c-103">Query a collection of objects</span></span>

<span data-ttu-id="3d12c-104">此示例演示如何对一系列 `Student` 对象执行简单查询。</span><span class="sxs-lookup"><span data-stu-id="3d12c-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="3d12c-105">每个 `Student` 对象均包含一些关于学生的基本信息和表示学生在四门考试中的分数的列表。</span><span class="sxs-lookup"><span data-stu-id="3d12c-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
<span data-ttu-id="3d12c-106">该应用程序充当本部分中使用相同 `students` 数据源的许多其他示例的框架。</span><span class="sxs-lookup"><span data-stu-id="3d12c-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d12c-107">示例</span><span class="sxs-lookup"><span data-stu-id="3d12c-107">Example</span></span>

<span data-ttu-id="3d12c-108">以下查询将返回在第一堂考试中得分为 90 或更高的学生。</span><span class="sxs-lookup"><span data-stu-id="3d12c-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
<span data-ttu-id="3d12c-109">该查询有意简单，以使你可以进行实验。</span><span class="sxs-lookup"><span data-stu-id="3d12c-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="3d12c-110">例如，你可以在 `where` 子句中尝试其他条件或使用 `orderby` 子句对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="3d12c-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d12c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d12c-111">See also</span></span>

- [<span data-ttu-id="3d12c-112">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="3d12c-112">Language Integrated Query (LINQ)</span></span>](index.md)  
- [<span data-ttu-id="3d12c-113">字符串内插</span><span class="sxs-lookup"><span data-stu-id="3d12c-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)