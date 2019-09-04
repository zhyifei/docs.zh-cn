---
title: 将某一类型转换为泛型 IEnumerable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c92f65c22fe4b4128a171c757bb9e9c0ccbc3fee
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247729"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="e110d-102">将某一类型转换为泛型 IEnumerable</span><span class="sxs-lookup"><span data-stu-id="e110d-102">Convert a Type to a Generic IEnumerable</span></span>
<span data-ttu-id="e110d-103">使用 <xref:System.Linq.Enumerable.AsEnumerable%2A> 可返回类型化为泛型 `IEnumerable` 的参数。</span><span class="sxs-lookup"><span data-stu-id="e110d-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e110d-104">示例</span><span class="sxs-lookup"><span data-stu-id="e110d-104">Example</span></span>  
 <span data-ttu-id="e110d-105">在此示例中，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]（使用默认泛型 `Query`）会尝试将查询转换为 SQL 并在服务器上执行。</span><span class="sxs-lookup"><span data-stu-id="e110d-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="e110d-106">但 `where` 子句引用用户定义的客户端方法 (`isValidProduct`)，此方法无法转换为 SQL。</span><span class="sxs-lookup"><span data-stu-id="e110d-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="e110d-107">解决方法是指定 <xref:System.Collections.Generic.IEnumerable%601> 的客户端泛型 `where` 实现以替换泛型 <xref:System.Linq.IQueryable%601>。</span><span class="sxs-lookup"><span data-stu-id="e110d-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="e110d-108">可通过调用 <xref:System.Linq.Enumerable.AsEnumerable%2A> 运算符来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e110d-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="e110d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e110d-109">See also</span></span>

- [<span data-ttu-id="e110d-110">查询示例</span><span class="sxs-lookup"><span data-stu-id="e110d-110">Query Examples</span></span>](query-examples.md)
