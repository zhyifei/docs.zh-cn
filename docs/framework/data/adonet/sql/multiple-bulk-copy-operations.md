---
title: 多个批量复制操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 838f56311f165c99c71cc734576bbdb53a946b7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792064"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="91439-102">多个批量复制操作</span><span class="sxs-lookup"><span data-stu-id="91439-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="91439-103">可以使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类的单个实例执行多次批量复制操作。</span><span class="sxs-lookup"><span data-stu-id="91439-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="91439-104">如果在两个副本之间发生操作参数更改（例如，目标表的名称），则必须在对任何**WriteToServer**方法的后续调用之前更新这些参数，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="91439-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="91439-105">除非显式更改，否则，所有属性值都将与给定实例的上一次批量复制操作相同。</span><span class="sxs-lookup"><span data-stu-id="91439-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91439-106">使用 <xref:System.Data.SqlClient.SqlBulkCopy> 的相同实例执行多次批量复制操作通常比每个操作使用独立的实例更加有效。</span><span class="sxs-lookup"><span data-stu-id="91439-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="91439-107">如果使用相同的 <xref:System.Data.SqlClient.SqlBulkCopy> 对象执行多次批量复制操作，不会限制每个操作中的源信息或目标信息相同还是不同。</span><span class="sxs-lookup"><span data-stu-id="91439-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="91439-108">但是，必须确保每次写入服务器时正确设置了列关联信息。</span><span class="sxs-lookup"><span data-stu-id="91439-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="91439-109">除非已按照[大容量复制示例设置](bulk-copy-example-setup.md)中所述创建了工作表，否则此示例将不会运行。</span><span class="sxs-lookup"><span data-stu-id="91439-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](bulk-copy-example-setup.md).</span></span> <span data-ttu-id="91439-110">提供此代码是为了演示仅使用**SqlBulkCopy**的语法。</span><span class="sxs-lookup"><span data-stu-id="91439-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="91439-111">如果源表和目标表位于同一个 SQL Server 实例中，则使用 Transact-SQL `INSERT … SELECT` 语句复制数据会更加容易、更加迅速。</span><span class="sxs-lookup"><span data-stu-id="91439-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="91439-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="91439-112">See also</span></span>

- [<span data-ttu-id="91439-113">SQL Server 中的大容量复制操作</span><span class="sxs-lookup"><span data-stu-id="91439-113">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="91439-114">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="91439-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
