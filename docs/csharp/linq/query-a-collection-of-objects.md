---
title: "查询对象的集合"
description: "如何查询集合。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e08f2e5877ffe24f5a238ab19abb9760cb442f2
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="66284-104">查询对象的集合</span><span class="sxs-lookup"><span data-stu-id="66284-104">Query a collection of objects</span></span>
<span data-ttu-id="66284-105">此示例演示如何对一系列 `Student` 对象执行简单查询。</span><span class="sxs-lookup"><span data-stu-id="66284-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="66284-106">每个 `Student` 对象均包含一些关于学生的基本信息和表示学生在四门考试中的分数的列表。</span><span class="sxs-lookup"><span data-stu-id="66284-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="66284-107">该应用程序充当本部分中使用相同 `students` 数据源的许多其他示例的框架。</span><span class="sxs-lookup"><span data-stu-id="66284-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66284-108">示例</span><span class="sxs-lookup"><span data-stu-id="66284-108">Example</span></span>  
 <span data-ttu-id="66284-109">以下查询将返回在第一堂考试中得分为 90 或更高的学生。</span><span class="sxs-lookup"><span data-stu-id="66284-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 <span data-ttu-id="66284-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="66284-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span></span>  
  
 <span data-ttu-id="66284-111">该查询有意简单，以使你可以进行实验。</span><span class="sxs-lookup"><span data-stu-id="66284-111">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="66284-112">例如，你可以在 `where` 子句中尝试其他条件或使用 `orderby` 子句对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="66284-112">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="66284-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="66284-113">See also</span></span>  
 [<span data-ttu-id="66284-114">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="66284-114">LINQ Query Expressions</span></span>](index.md)

