---
title: "插入、更新和删除操作"
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
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bc279fa541ed14244ea093dcd3ea52c37a4698f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="insert-update-and-delete-operations"></a><span data-ttu-id="e9ab0-102">插入、更新和删除操作</span><span class="sxs-lookup"><span data-stu-id="e9ab0-102">Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="e9ab0-103">在 `Insert` 中执行 `Update`、`Delete` 和 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 操作的方法是：向对象模型中添加对象、更改和移除对象模型中的对象。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-103">You perform `Insert`, `Update`, and `Delete` operations in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] by adding, changing, and removing objects in your object model.</span></span> <span data-ttu-id="e9ab0-104">默认情况下，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将您所做的操作转换成 SQL，然后将这些更改提交至数据库。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your actions to SQL and submits the changes to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e9ab0-105"> 在操作和保持对对象所做更改方面有着最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-105"> offers maximum flexibility in manipulating and persisting changes that you made to your objects.</span></span> <span data-ttu-id="e9ab0-106">实体对象可用（通过查询检索它们或通过重新构造它们）后，就可以像应用程序中的典型对象一样更改实体对象。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-106">As soon as entity objects are available (either by retrieving them through a query or by constructing them anew), you can change them as typical objects in your application.</span></span> <span data-ttu-id="e9ab0-107">也就是说，你可以更改其值、 可以将它们添加到集合中，和从集合中移除它们。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-107">That is, you can change their values, you can add them to your collections, and you can remove them from your collections.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e9ab0-108"> 会跟踪您所做的更改，并且在您调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时就可以将这些更改传回数据库。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-108"> tracks your changes and is ready to transmit them back to the database when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e9ab0-109"> 不支持且无法识别级联删除操作。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-109"> does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="e9ab0-110">如果你想要删除的行有约束的表中，你必须设置`ON DELETE CASCADE`规则在数据库中的外键约束中或使用你自己的代码先删除阻止删除父对象的子对象。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-110">If you want to delete a row in a table that has constraints against it, you must either set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database, or use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span> <span data-ttu-id="e9ab0-111">否则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-111">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="e9ab0-112">有关详细信息，请参阅[如何： 删除数据库中的行](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-112">For more information, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="e9ab0-113">以下摘录会用到 Northwind 示例数据库中的 `Customer` 和 `Order` 类。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-113">The following excerpts use the `Customer` and `Order` classes from the Northwind sample database.</span></span> <span data-ttu-id="e9ab0-114">为简洁起见，不显示类定义。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-114">Class definitions are not shown for brevity.</span></span>  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 <span data-ttu-id="e9ab0-115">当您调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会自动生成并执行它为将您所做的更改传回数据库而必须具备的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-115">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatically generates and executes the SQL commands that it must have to transmit your changes back to the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9ab0-116">您可以使用自己的自定义逻辑来重写此行为，这通常是通过存储过程来实现的。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-116">You can override this behavior by using your own custom logic, typically by way of a stored procedure.</span></span> <span data-ttu-id="e9ab0-117">有关详细信息，请参阅[开发人员在重写默认行为中的责任](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-117">For more information, see [Responsibilities of the Developer In Overriding Default Behavior](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span></span>  
>   
>  <span data-ttu-id="e9ab0-118">使用 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 的开发人员可以使用 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 来开发用于实现此目的的存储过程。</span><span class="sxs-lookup"><span data-stu-id="e9ab0-118">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for this purpose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ab0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9ab0-119">See Also</span></span>  
 [<span data-ttu-id="e9ab0-120">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="e9ab0-120">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="e9ab0-121">自定义插入、更新和删除操作</span><span class="sxs-lookup"><span data-stu-id="e9ab0-121">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
