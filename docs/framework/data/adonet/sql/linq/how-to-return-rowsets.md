---
title: "如何：返回行集"
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
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c5f88ce69239c0ca601344362dc420205291cb74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="f1c77-102">如何：返回行集</span><span class="sxs-lookup"><span data-stu-id="f1c77-102">How to: Return Rowsets</span></span>
<span data-ttu-id="f1c77-103">此示例从数据库中返回行集合，并包含用于筛选结果的输入参数。</span><span class="sxs-lookup"><span data-stu-id="f1c77-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="f1c77-104">执行返回行集的存储的过程时，你使用*结果*存储从存储过程中的返回的类。</span><span class="sxs-lookup"><span data-stu-id="f1c77-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="f1c77-105">有关详细信息，请参阅[分析 LINQ to SQL 源代码](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md)。</span><span class="sxs-lookup"><span data-stu-id="f1c77-105">For more information, see [Analyzing LINQ to SQL Source Code](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1c77-106">示例</span><span class="sxs-lookup"><span data-stu-id="f1c77-106">Example</span></span>  
 <span data-ttu-id="f1c77-107">下面的示例表示一个存储过程，该存储过程返回客户行并使用输入参数来仅返回将“London”列为客户城市的那些行。</span><span class="sxs-lookup"><span data-stu-id="f1c77-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="f1c77-108">该示例假定有一个可枚举的 `CustomersByCityResult` 类。</span><span class="sxs-lookup"><span data-stu-id="f1c77-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1c77-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1c77-109">See Also</span></span>  
 [<span data-ttu-id="f1c77-110">存储过程</span><span class="sxs-lookup"><span data-stu-id="f1c77-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="f1c77-111">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="f1c77-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
