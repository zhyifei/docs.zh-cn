---
title: Oracle 和 ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: a8668ee115a3babbdf1ef549a418187d2c5e26b8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583419"
---
# <a name="oracle-and-adonet"></a>Oracle 和 ADO.NET
> [!NOTE]
>  <xref:System.Data.OracleClient> 中的类型已过时。 当前版本的 .NET Framework 仍支持这些类型，但以后的版本会将这些类型删除。 Microsoft 建议您使用第三方 Oracle 提供程序。  
  
 本部分介绍功能和特定于 Oracle.NET Framework 数据提供程序的行为。  
  
 适用于 Oracle 的.NET Framework 数据提供程序提供了对使用 Oracle 调用接口 (OCI) 提供的 Oracle 客户端软件的 Oracle 数据库的访问。 数据提供程序的功能被设计为类似于 SQL Server、 OLE DB 和 ODBC 的.NET Framework 数据提供程序。  
  
 若要使用用于 Oracle 的.NET Framework 数据提供程序，应用程序必须引用<xref:System.Data.OracleClient>命名空间，如下所示：  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 在编译代码时还必须包括对该 DLL 的引用。 例如，如果编译的是 C# 程序，命令行中应包括：  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>本节内容  
 [系统要求](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 介绍了对于 Oracle，使用.NET Framework 数据提供程序的要求以及要使用它时应注意的问题数。  
  
 [Oracle BFILEs](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 描述用于使用 Oracle BFILE 数据类型的 <xref:System.Data.OracleClient.OracleBFile> 类。  
  
 [Oracle LOBs](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 描述用于使用 Oracle LOB 数据类型的 <xref:System.Data.OracleClient.OracleLob> 类。  
  
 [Oracle REF CURSORs](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 描述对 Oracle REF CURSOR 数据类型的支持。  
  
 [OracleTypes](../../../../docs/framework/data/adonet/oracletypes.md)  
 描述可以用于使用 Oracle 数据类型的结构，包括 <xref:System.Data.OracleClient.OracleNumber> 和 <xref:System.Data.OracleClient.OracleString>。  
  
 [Oracle 序列](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 说明对检索服务器生成的 Oracle 键序列值的支持。  
  
 [Oracle 数据类型映射](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 列出 Oracle 数据类型及其与 <xref:System.Data.OracleClient.OracleDataReader> 的映射。  
  
 [Oracle 分布式事务](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 描述 <xref:System.Data.OracleClient.OracleConnection> 对象如何自动在现有分布式事务中登记（如果确定某个事务是活动的）。  
  
## <a name="related-sections"></a>相关章节  
 [保证 ADO.NET 应用程序的安全](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 说明使用 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 时的安全编码做法。  
  
 [数据集、数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 说明如何创建和使用 `DataSets`、类型化 `DataSets`、`DataTables` 和 `DataViews`。  
  
 [在 ADO.NET 中检索和修改数据](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 说明如何使用 ADO.NET 中的数据。  
  
 [SQL Server 和 ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 描述如何使用 SQL Server 特定的功能。  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 说明允许在 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 中编写独立于提供程序的代码的泛型类。  
  
## <a name="see-also"></a>请参阅

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
