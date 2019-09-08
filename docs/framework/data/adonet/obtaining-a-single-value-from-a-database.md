---
title: 从数据库获取单一值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: fb43d21546a0e98e87aab23db9213309b62320b9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794746"
---
# <a name="obtaining-a-single-value-from-a-database"></a>从数据库获取单一值
您可能需要返回只是单个值的数据库信息，而不需要返回表或数据流形式的数据库信息。 例如，您可能希望返回聚合函数的结果，如 COUNT （\*）、SUM （Price）或 AVG （数量）。 **Command**对象提供使用**ExecuteScalar**方法返回单个值的功能。 **ExecuteScalar**方法以标量值的形式返回结果集第一行的第一列的值。  
  
 下面的代码示例使用 <xref:System.Data.SqlClient.SqlCommand> 在数据库中插入一个新值。 使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> 方法可返回已插入记录的标识列值。  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>请参阅

- [命令和参数](commands-and-parameters.md)
- [执行命令](executing-a-command.md)
- [DbConnection、DbCommand 和 DbException](dbconnection-dbcommand-and-dbexception.md)
- [ADO.NET 概述](ado-net-overview.md)
