---
title: 如何：使用标量值用户定义的函数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: ffb24468c81cb4ec9f41645f8888c2c4ba021609
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033574"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="84875-102">如何：使用标量值用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="84875-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="84875-103">您可以通过使用 <xref:System.Data.Linq.Mapping.FunctionAttribute> 属性将类中定义的客户端方法映射到用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="84875-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="84875-104">请注意，方法体会构造一个捕获方法调用意向的表达式，并将该表达式传递给 <xref:System.Data.Linq.DataContext> 进行转换和执行。</span><span class="sxs-lookup"><span data-stu-id="84875-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84875-105">只有在查询外部调用此函数时，才会直接执行。</span><span class="sxs-lookup"><span data-stu-id="84875-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="84875-106">有关详细信息，请参阅[如何：内联调用用户定义的函数](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)。</span><span class="sxs-lookup"><span data-stu-id="84875-106">For more information, see [How to: Call User-Defined Functions Inline](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84875-107">示例</span><span class="sxs-lookup"><span data-stu-id="84875-107">Example</span></span>  
 <span data-ttu-id="84875-108">下面的 SQL 代码展示了一个用户定义的标量值函数 `ReverseCustName()`。</span><span class="sxs-lookup"><span data-stu-id="84875-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="84875-109">您可以为此代码映射一个客户端方法，例如，可以映射下面这个方法：</span><span class="sxs-lookup"><span data-stu-id="84875-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="84875-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="84875-110">See also</span></span>

- [<span data-ttu-id="84875-111">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="84875-111">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
