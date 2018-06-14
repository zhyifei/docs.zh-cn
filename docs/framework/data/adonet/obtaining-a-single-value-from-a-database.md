---
title: 从数据库获取单一值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: b7ad989dce39a8e9a0ed7b6cd988e06304e7b40f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764926"
---
# <a name="obtaining-a-single-value-from-a-database"></a>从数据库获取单一值
您可能需要返回只是单个值的数据库信息，而不需要返回表或数据流形式的数据库信息。 例如，你可能想要返回的结果计数等聚合函数 (\*)，（price） 或 AVG(Quantity)。 **命令**对象提供的功能，以返回单个值使用**ExecuteScalar**方法。 **ExecuteScalar**方法返回时，为标量值，结果集的第一行的第一列的值。  
  
 下面的代码示例使用 <xref:System.Data.SqlClient.SqlCommand> 在数据库中插入一个新值。 使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> 方法可返回已插入记录的标识列值。  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 [命令和参数](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [执行命令](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [DbConnection、DbCommand 和 DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
