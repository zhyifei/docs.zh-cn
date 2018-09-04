---
title: 从数据库获取单一值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 1a0d92c7acad58d3618c3f50b7463022352cf542
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560852"
---
# <a name="obtaining-a-single-value-from-a-database"></a>从数据库获取单一值
您可能需要返回只是单个值的数据库信息，而不需要返回表或数据流形式的数据库信息。 例如，您可能需要返回 COUNT 等聚合函数的结果 (\*)，sum (price) 或 avg （quantity）。 **命令**对象提供了返回单个值使用的功能**ExecuteScalar**方法。 **ExecuteScalar**方法返回时，为标量值，结果集的第一行的第一列的值。  
  
 下面的代码示例使用 <xref:System.Data.SqlClient.SqlCommand> 在数据库中插入一个新值。 使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> 方法可返回已插入记录的标识列值。  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 [命令和参数](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [执行命令](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [DbConnection、DbCommand 和 DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
