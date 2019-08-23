---
title: 如何：使用采用参数的存储过程
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 17ae74a430df4d4a4670c2390ce7b2ee25b67c7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938703"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="7bf56-102">如何：使用采用参数的存储过程</span><span class="sxs-lookup"><span data-stu-id="7bf56-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7bf56-103">将输出参数映射到引用参数，并且对于值类型，它将参数声明为可以为 null。</span><span class="sxs-lookup"><span data-stu-id="7bf56-103">maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="7bf56-104">有关如何在返回行集的查询中使用输入参数的示例, 请参阅[如何:返回行](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)集。</span><span class="sxs-lookup"><span data-stu-id="7bf56-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bf56-105">示例</span><span class="sxs-lookup"><span data-stu-id="7bf56-105">Example</span></span>  
 <span data-ttu-id="7bf56-106">下面的示例带有单个输入参数（客户 ID）并返回一个输出参数（该客户的总销售额）。</span><span class="sxs-lookup"><span data-stu-id="7bf56-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="7bf56-107">示例</span><span class="sxs-lookup"><span data-stu-id="7bf56-107">Example</span></span>  
 <span data-ttu-id="7bf56-108">您将按如下方式调用此存储过程：</span><span class="sxs-lookup"><span data-stu-id="7bf56-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7bf56-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="7bf56-109">See also</span></span>

- [<span data-ttu-id="7bf56-110">存储过程</span><span class="sxs-lookup"><span data-stu-id="7bf56-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [<span data-ttu-id="7bf56-111">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="7bf56-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="7bf56-112">使用可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="7bf56-112">Using Nullable Types</span></span>](../../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="7bf56-113">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="7bf56-113">Nullable Value Types</span></span>](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
