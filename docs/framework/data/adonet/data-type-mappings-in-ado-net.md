---
title: ADO.NET 中的数据类型映射
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 4e85db4732da664848cee2ef48f9a880a86fef18
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583759"
---
# <a name="data-type-mappings-in-adonet"></a>ADO.NET 中的数据类型映射
.NET Framework 基于用于定义如何在运行时声明、使用和管理类型的通用类型系统。 它由值类型和引用类型组成，这两种类型均派生自 <xref:System.Object> 基类型。 使用数据源时，如果未显式指定数据类型，则从数据提供程序推断出它。 例如，<xref:System.Data.DataSet> 对象独立于任何特定的数据源。 `DataSet` 中的数据从数据源中进行检索，而更改则会使用 `DataAdapter` 持久保存回数据源。 这意味着，当`DataAdapter`填充<xref:System.Data.DataTable>中`DataSet`来自数据源中的列的结果数据类型的值与`DataTable`是.NET Framework 类型，而不是特定于.NET Framework 数据提供程序类型，用于连接到数据源。  
  
 同样，当`DataReader`返回数据源，生成的值中的值存储在具有.NET Framework 类型的本地变量中。 两个`Fill`的操作`DataAdapter`并`Get`方法的`DataReader`，.NET Framework 类型从.NET Framework 数据提供程序返回的值来推断。  
  
 当所返回值的特定类型已知时，可以使用 `DataReader` 的类型化访问器方法，而不是依靠推断出的数据类型。 类型化取值函数方法，通过为特定的.NET Framework 类型，而不需要将其他类型转换为返回值更好的性能。  
  
> [!NOTE]
>  对于.NET Framework 数据提供程序的数据类型的 null 值由`DBNull.Value`。  
  
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
- [常规类型系统](../../../../docs/standard/base-types/common-type-system.md)
- [转换类型](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
