---
title: 如何：查询信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634646"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="7e9ad-102">如何：查询信息</span><span class="sxs-lookup"><span data-stu-id="7e9ad-102">How to: Query for Information</span></span>
<span data-ttu-id="7e9ad-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中的查询使用与 LINQ 中的查询相同的语法。</span><span class="sxs-lookup"><span data-stu-id="7e9ad-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="7e9ad-104">唯一的区别在于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询中引用的对象将映射到数据库中的元素。</span><span class="sxs-lookup"><span data-stu-id="7e9ad-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="7e9ad-105">有关详细信息，请参阅 [LINQ 查询简介 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="7e9ad-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7e9ad-106">将您编写的查询转换成等效的 SQL 查询，然后将它们发送至服务器进行处理。</span><span class="sxs-lookup"><span data-stu-id="7e9ad-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="7e9ad-107">LINQ 查询的某些功能在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序中可能需要特别注意。</span><span class="sxs-lookup"><span data-stu-id="7e9ad-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="7e9ad-108">有关详细信息，请参阅[查询概念](query-concepts.md)。</span><span class="sxs-lookup"><span data-stu-id="7e9ad-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e9ad-109">示例</span><span class="sxs-lookup"><span data-stu-id="7e9ad-109">Example</span></span>  
 <span data-ttu-id="7e9ad-110">下面的查询请求来自伦敦的客户的列表。</span><span class="sxs-lookup"><span data-stu-id="7e9ad-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="7e9ad-111">在此示例中，`Customers` 是 Northwind 示例数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="7e9ad-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7e9ad-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e9ad-112">See also</span></span>

- [<span data-ttu-id="7e9ad-113">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="7e9ad-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="7e9ad-114">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="7e9ad-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="7e9ad-115">查询数据库</span><span class="sxs-lookup"><span data-stu-id="7e9ad-115">Querying the Database</span></span>](querying-the-database.md)
