---
title: "如何：更新数据库中的行"
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
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0ba7d6369b534edf5e8c61605b09823a36143a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-update-rows-in-the-database"></a>如何：更新数据库中的行
你可以通过修改与关联的对象的成员值来更新数据库中的行[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Table%601>集合，然后将提交到数据库的更改。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]将转换成相应的 SQL 更改`UPDATE`命令。  
  
> [!NOTE]
>  您可以重写 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]、`Insert` 和 `Update` 数据库操作的 `Delete` 默认方法。 有关详细信息，请参阅[自定义插入、 更新和删除操作](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)。  
>   
>  使用 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 的开发人员可以使用 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 来开发用于实现相同目的的存储过程。  
  
 以下步骤假定您已通过有效的 <xref:System.Data.Linq.DataContext> 连接到 Northwind 数据库。 有关详细信息，请参阅[如何： 连接到数据库](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)。  
  
### <a name="to-update-a-row-in-the-database"></a>更新数据库中的行  
  
1.  查询数据库中要更新的行。  
  
2.  对得到的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对象中的成员值进行所需的更改。  
  
3.  将更改提交到数据库。  
  
## <a name="example"></a>示例  
 下面的示例查询数据库中编号为 11000 的订单，然后更改所得到的 `ShipName` 对象中的 `ShipVia` 和 `Order` 值。 最后，对这些成员值的更改将作为对 `ShipName` 和 `ShipVia` 列的更改提交到数据库。  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a>另请参阅  
 [如何： 管理更改冲突](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [如何： 分配存储的过程以便执行更新、 插入和删除操作 （O/R 设计器）](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [进行和提交数据更改](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
