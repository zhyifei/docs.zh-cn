---
title: "连接到 ADO.NET 中的数据源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 01a7342d6e081bec88aeef2c55461be2d936e4a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="connecting-to-a-data-source-in-adonet"></a>连接到 ADO.NET 中的数据源
在 ADO.NET 中使用**连接**要通过提供必要的身份验证信息来连接字符串连接到特定数据源对象。 **连接**你使用的对象取决于数据源的类型。  
  
 随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbConnection> 对象：适用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbConnection> 对象，适用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlConnection> 对象，适用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcConnection> 对象，适用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleConnection> 对象。  
  
## <a name="in-this-section"></a>本节内容  
 [建立连接](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 介绍如何使用**连接**对象以建立与数据源的连接。  
  
 [连接事件](../../../../docs/framework/data/adonet/connection-events.md)  
 介绍如何使用**InfoMessage**事件从数据源中检索信息性消息。  
  
## <a name="see-also"></a>请参阅  
 [连接字符串](../../../../docs/framework/data/adonet/connection-strings.md)  
 [连接池](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [命令和参数](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapters 和 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [事务和并发性](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
