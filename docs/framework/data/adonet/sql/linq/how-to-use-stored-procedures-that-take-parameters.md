---
title: "如何：使用采用参数的存储过程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 28f389d7128283501291bc3220cfde3815cc0713
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="b8d85-102">如何：使用采用参数的存储过程</span><span class="sxs-lookup"><span data-stu-id="b8d85-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="b8d85-103"> 将输出参数映射到引用参数，并且对于值类型，它将参数声明为可以为 null。</span><span class="sxs-lookup"><span data-stu-id="b8d85-103"> maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="b8d85-104">有关如何在返回行集的查询中使用输入的参数的示例，请参阅[如何： 返回行集](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)。</span><span class="sxs-lookup"><span data-stu-id="b8d85-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8d85-105">示例</span><span class="sxs-lookup"><span data-stu-id="b8d85-105">Example</span></span>  
 <span data-ttu-id="b8d85-106">下面的示例带有单个输入参数（客户 ID）并返回一个输出参数（该客户的总销售额）。</span><span class="sxs-lookup"><span data-stu-id="b8d85-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="b8d85-107">示例</span><span class="sxs-lookup"><span data-stu-id="b8d85-107">Example</span></span>  
 <span data-ttu-id="b8d85-108">您将按如下方式调用此存储过程：</span><span class="sxs-lookup"><span data-stu-id="b8d85-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b8d85-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8d85-109">See Also</span></span>  
 [<span data-ttu-id="b8d85-110">存储过程</span><span class="sxs-lookup"><span data-stu-id="b8d85-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="b8d85-111">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="b8d85-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="b8d85-112">使用可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="b8d85-112">Using Nullable Types</span></span>](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [<span data-ttu-id="b8d85-113">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="b8d85-113">Nullable Value Types</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
