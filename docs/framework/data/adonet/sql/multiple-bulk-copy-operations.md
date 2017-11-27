---
title: "多个批量复制操作"
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
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7db77dcd58e48927e8dac9bee82f7f14cdacf196
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="multiple-bulk-copy-operations"></a>多个批量复制操作
可以使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类的单个实例执行多次批量复制操作。 如果复制 （例如，目标表的名称） 之间更改操作参数，你必须先更新这些对任何的任何后续调用**WriteToServer**方法，如下面的示例中所示。 除非显式更改，否则，所有属性值都将与给定实例的上一次批量复制操作相同。  
  
> [!NOTE]
>  使用 <xref:System.Data.SqlClient.SqlBulkCopy> 的相同实例执行多次批量复制操作通常比每个操作使用独立的实例更加有效。  
  
 如果使用相同的 <xref:System.Data.SqlClient.SqlBulkCopy> 对象执行多次批量复制操作，不会限制每个操作中的源信息或目标信息相同还是不同。 但是，必须确保每次写入服务器时正确设置了列关联信息。  
  
> [!IMPORTANT]
>  除非你已创建了工作表中所述，将不会运行此示例[批量复制示例设置](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)。 提供此代码是为了演示使用的语法**SqlBulkCopy**仅。 如果源表和目标表位于同一个 SQL Server 实例中，则使用 Transact-SQL `INSERT … SELECT` 语句复制数据会更加容易、更加迅速。  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server 中的大容量复制操作](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
