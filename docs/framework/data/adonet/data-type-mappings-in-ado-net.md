---
title: ADO.NET 中的数据类型映射
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: ddb3c1c5551336ace66bab53af3beb83b6cd2d34
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950400"
---
# <a name="data-type-mappings-in-adonet"></a>ADO.NET 中的数据类型映射
.NET Framework 基于用于定义如何在运行时声明、使用和管理类型的通用类型系统。 它由值类型和引用类型组成，这两种类型均派生自 <xref:System.Object> 基类型。 使用数据源时，如果未显式指定数据类型，则从数据提供程序推断出它。 例如，<xref:System.Data.DataSet> 对象独立于任何特定的数据源。 `DataSet` 中的数据从数据源中进行检索，而更改则会使用 `DataAdapter` 持久保存回数据源。 这意味着当`DataAdapter` `DataSet`使用数据源中<xref:System.Data.DataTable>的值填充中的时, 中列的`DataTable`结果数据类型为 .NET Framework 类型, 而不是特定于 .NET Framework 数据提供程序的类型,用于连接到数据源。  
  
 同样, 当从`DataReader`数据源返回值时, 生成的值将存储在具有 .NET Framework 类型的局部变量中。 `DataAdapter`对于的`Fill` 操作`Get`和的方法,将从.NETFramework数据提供程序返回的值推断.NETFramework类型。`DataReader`  
  
 当所返回值的特定类型已知时，可以使用 `DataReader` 的类型化访问器方法，而不是依靠推断出的数据类型。 类型化访问器方法通过以特定 .NET Framework 类型返回值来提高性能, 从而无需额外的类型转换。  
  
> [!NOTE]
> .NET Framework 数据提供程序数据类型的 Null 值由`DBNull.Value`表示。  
  
## <a name="in-this-section"></a>本节内容  
 [SQL Server 数据类型映射](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 列出针对 <xref:System.Data.SqlClient> 的推断数据类型映射和数据访问器方法。  
  
 [OLE DB 数据类型映射](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 列出针对 <xref:System.Data.OleDb> 的推断数据类型映射和数据访问器方法。  
  
 [ODBC 数据类型映射](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 列出针对 <xref:System.Data.Odbc> 的推断数据类型映射和数据访问器方法。  
  
 [Oracle 数据类型映射](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 列出针对 <xref:System.Data.OracleClient> 的推断数据类型映射和数据访问器方法。  
  
 [浮点数](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 描述开发人员在使用浮点数时经常遇到的问题。  
  
## <a name="see-also"></a>请参阅

- [SQL Server 数据类型和 ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [配置参数和参数数据类型](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [检索数据库架构信息](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [常规类型系统](../../../standard/base-types/common-type-system.md)
- [转换类型](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
