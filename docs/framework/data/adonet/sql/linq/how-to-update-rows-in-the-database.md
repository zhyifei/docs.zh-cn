---
title: 如何：更新数据库中的行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: 84ef85b1e53d97ff468c3360af5e394a0e4ad776
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091187"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="2f421-102">如何：更新数据库中的行</span><span class="sxs-lookup"><span data-stu-id="2f421-102">How to: Update Rows in the Database</span></span>
<span data-ttu-id="2f421-103">可以通过修改与关联的对象的成员值来更新数据库中的行[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Table%601>集合，然后将更改提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="2f421-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="2f421-104">将转换成相应的 SQL 所做的更改`UPDATE`命令。</span><span class="sxs-lookup"><span data-stu-id="2f421-104">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f421-105">您可以重写 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]、`Insert` 和 `Update` 数据库操作的 `Delete` 默认方法。</span><span class="sxs-lookup"><span data-stu-id="2f421-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="2f421-106">有关详细信息，请参阅[自定义插入、 更新和删除操作](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="2f421-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="2f421-107">使用 Visual Studio 的开发人员可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来开发用于同一目的的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="2f421-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="2f421-108">以下步骤假定您已通过有效的 <xref:System.Data.Linq.DataContext> 连接到 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="2f421-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="2f421-109">有关详细信息，请参阅[如何：连接到数据库](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)。</span><span class="sxs-lookup"><span data-stu-id="2f421-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="2f421-110">更新数据库中的行</span><span class="sxs-lookup"><span data-stu-id="2f421-110">To update a row in the database</span></span>  
  
1.  <span data-ttu-id="2f421-111">查询数据库中要更新的行。</span><span class="sxs-lookup"><span data-stu-id="2f421-111">Query the database for the row to be updated.</span></span>  
  
2.  <span data-ttu-id="2f421-112">对得到的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对象中的成员值进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="2f421-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>  
  
3.  <span data-ttu-id="2f421-113">将更改提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="2f421-113">Submit the changes to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f421-114">示例</span><span class="sxs-lookup"><span data-stu-id="2f421-114">Example</span></span>  
 <span data-ttu-id="2f421-115">下面的示例查询数据库中编号为 11000 的订单，然后更改所得到的 `ShipName` 对象中的 `ShipVia` 和 `Order` 值。</span><span class="sxs-lookup"><span data-stu-id="2f421-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="2f421-116">最后，对这些成员值的更改将作为对 `ShipName` 和 `ShipVia` 列的更改提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="2f421-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2f421-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f421-117">See also</span></span>

- [<span data-ttu-id="2f421-118">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="2f421-118">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="2f421-119">如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="2f421-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="2f421-120">进行和提交数据更改</span><span class="sxs-lookup"><span data-stu-id="2f421-120">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
