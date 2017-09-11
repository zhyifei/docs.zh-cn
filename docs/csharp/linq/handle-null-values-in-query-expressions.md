---
title: "在查询表达式中处理 null 值"
description: "如何：在查询表达式中处理 null 值。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f4f189504c57c9c01268b10bc96ad3c9af49ddbd
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="22caf-104">在查询表达式中处理 null 值</span><span class="sxs-lookup"><span data-stu-id="22caf-104">Handle null values in query expressions</span></span>

<span data-ttu-id="22caf-105">此示例显示如何在源集合中处理可能的 null 值。</span><span class="sxs-lookup"><span data-stu-id="22caf-105">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="22caf-106"><xref:System.Collections.Generic.IEnumerable%601> 等对象集合可包含值为 [null](../language-reference/keywords/null.md) 的元素。</span><span class="sxs-lookup"><span data-stu-id="22caf-106">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="22caf-107">如果源集合为 null 或包含值为 null 的元素，并且查询不处理 null 值，则在执行查询时将引发 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="22caf-107">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22caf-108">示例</span><span class="sxs-lookup"><span data-stu-id="22caf-108">Example</span></span>

 <span data-ttu-id="22caf-109">可采用防御方式进行编码，以避免空引用异常，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="22caf-109">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>  
  
 <span data-ttu-id="22caf-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="22caf-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span></span>  
  
 <span data-ttu-id="22caf-111">在前面的示例中，`where` 子句筛选出类别序列中的所有 null 元素。</span><span class="sxs-lookup"><span data-stu-id="22caf-111">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="22caf-112">此方法独立于 join 子句中的 null 检查。</span><span class="sxs-lookup"><span data-stu-id="22caf-112">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="22caf-113">在此示例中，带有 null 的条件表达式有效，因为 `Products.CategoryID` 的类型为 `int?`，这是 `Nullable<int>` 的速记形式。</span><span class="sxs-lookup"><span data-stu-id="22caf-113">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22caf-114">示例</span><span class="sxs-lookup"><span data-stu-id="22caf-114">Example</span></span>

 <span data-ttu-id="22caf-115">在 join 子句中，如果只有一个比较键是可以为 null 的类型，则可以在查询表达式中将另一个比较键转换为可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="22caf-115">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="22caf-116">在以下示例中，假定 `EmployeeID` 是包含 `int?` 类型的值列：</span><span class="sxs-lookup"><span data-stu-id="22caf-116">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>  
  
 <span data-ttu-id="22caf-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="22caf-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22caf-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22caf-118">See also</span></span>  
 <span data-ttu-id="22caf-119"><xref:System.Nullable%601></span><span class="sxs-lookup"><span data-stu-id="22caf-119"><xref:System.Nullable%601></span></span>   
 <span data-ttu-id="22caf-120">[LINQ 查询表达式](index.md) </span><span class="sxs-lookup"><span data-stu-id="22caf-120">[LINQ query expressions](index.md) </span></span>  
 [<span data-ttu-id="22caf-121">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="22caf-121">Nullable types</span></span>](../programming-guide/nullable-types/index.md)

