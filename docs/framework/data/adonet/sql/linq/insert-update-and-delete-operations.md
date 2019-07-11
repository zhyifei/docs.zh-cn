---
title: 插入、更新和删除操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: fa3690ae74869f5dc0fbaa8d824d4aebca8ce724
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743065"
---
# <a name="insert-update-and-delete-operations"></a>插入、更新和删除操作
在 `Insert` 中执行 `Update`、`Delete` 和 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 操作的方法是：向对象模型中添加对象、更改和移除对象模型中的对象。 默认情况下，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将您所做的操作转换成 SQL，然后将这些更改提交至数据库。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 在操作和保持对对象所做更改方面有着最大的灵活性。 实体对象可用（通过查询检索它们或通过重新构造它们）后，就可以像应用程序中的典型对象一样更改实体对象。 也就是说，可以更改它们的值、 可以将其添加到集合中，和可以从集合中删除它们。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会跟踪您所做的更改，并且在您调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时就可以将这些更改传回数据库。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 不支持且无法识别级联删除操作。 如果你想要删除的行有约束的表中，必须设置`ON DELETE CASCADE`中在数据库中，foreign key 约束的规则或使用你自己的代码首先删除阻止删除父对象的子对象。 否则会引发异常。 有关详细信息，请参阅[如何：从数据库中删除行](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)。  
  
 以下摘录会用到 Northwind 示例数据库中的 `Customer` 和 `Order` 类。 为简洁起见，不显示类定义。  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 当您调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会自动生成并执行它为将您所做的更改传回数据库而必须具备的 SQL 命令。  
  
> [!NOTE]
>  您可以使用自己的自定义逻辑来重写此行为，这通常是通过存储过程来实现的。 有关详细信息，请参阅[开发人员在重写默认行为的职责](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)。  
>   
>  使用 Visual Studio 的开发人员可以使用对象关系设计器来开发用于此目的的存储的过程。  
  
## <a name="see-also"></a>请参阅

- [下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [自定义插入、更新和删除操作](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
