---
title: "SQL Server 中的批量复制操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 31da2fbc7dca4c0c2c077991ddec39e8979b08b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bulk-copy-operations-in-sql-server"></a>SQL Server 中的批量复制操作
Microsoft SQL Server 包括一个名为的常用命令行实用工具**bcp**为快速批量将大型文件复制到 SQL Server 数据库中表或视图。 使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类可以编写提供类似功能的托管代码解决方案。 还可以通过其他方式将数据加载到 SQL Server 表中（例如 INSERT 语句），但是 <xref:System.Data.SqlClient.SqlBulkCopy> 提供的性能要明显优于这些方式。  
  
 <xref:System.Data.SqlClient.SqlBulkCopy> 类只能用于向 SQL Server 表中写入数据。 但是，数据源不限于 SQL Server；可以使用任何数据源，只要数据可以加载到 <xref:System.Data.DataTable> 实例或使用 <xref:System.Data.IDataReader> 实例读取即可。  
  
 使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类可以执行下列操作：  
  
-   单次批量复制操作  
  
-   多次批量复制操作  
  
-   事务中的批量复制操作  
  
> [!NOTE]
>  使用.NET Framework 1.1 或更早版本时 (后者不支持<xref:System.Data.SqlClient.SqlBulkCopy>类)，你可以执行 SQL Server TRANSACT-SQL**大容量插入**语句使用<xref:System.Data.SqlClient.SqlCommand>对象。  
  
## <a name="in-this-section"></a>本节内容  
 [批量复制示例设置](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 描述批量复制示例中使用的表，并提供用于在 AdventureWorks 数据库中创建表的 SQL 脚本。  
  
 [单次批量复制操作](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 描述如何使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类将数据单次批量复制到 SQL Server 实例中，以及如何使用 Transact-SQL 语句和 <xref:System.Data.SqlClient.SqlCommand> 类执行批量复制操作。  
  
 [多个大容量复制操作](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 描述如何使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类将数据多次批量复制到 SQL Server 实例中。  
  
 [事务和批量复制操作](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 描述如何在事务中执行批量复制操作，包括如何提交或回滚事务。  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server 和 ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
