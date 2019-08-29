---
title: 用于实体框架的 SqlClient
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: ec67637c416f2560c1f5d0a9fd0e856703820a84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69954969"
---
# <a name="sqlclient-for-the-entity-framework"></a>用于实体框架的 SqlClient
本节介绍用于 SQL Server (SqlClient) 的 .NET Framework 数据提供程序，该提供程序使实体框架能够在 Microsoft SQL Server 上工作。  
  
## <a name="provider-schema-attribute"></a>Provider 架构属性  
 `Provider` 是以存储架构定义语言 (SSDL) 表示的 `Schema` 元素的一个特性。  
  
 若要使用 SqlClient，请将字符串“System.Data.SqlClient”分配给 `Provider` 元素的 `Schema` 属性。  
  
## <a name="providermanifesttoken-schema-attribute"></a>ProviderManifestToken 架构属性  
 `ProviderManifestToken` 是以 SSDL 表示的 `Schema` 元素的一个必需特性。 此标记用于为脱机方案加载提供程序清单。 有关`ProviderManifestToken`特性的详细信息, 请参阅[Schema 元素 (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl)。  
  
 SqlClient 可用作 SQL Server 的不同版本的数据访问接口。 这些版本具有不同的功能。 例如, SQL Server 2000 不支持`varchar(max)`和`nvarchar(max)` SQL Server 2005 引入的类型。  
  
 针对不同版本的 SQL Server，SqlClient 生成和接受以下提供程序清单标记。  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
> 从 Visual Studio 2010 开始, [ADO.NET 实体数据模型工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))不支持 SQL Server 2000。  
  
## <a name="provider-namespace-name"></a>提供程序命名空间名称  
 所有提供程序都必须指定一个命名空间。 实体框架通过此属性获知提供程序为特定构造（如类型和函数）使用哪个前缀。 SqlClient 提供程序清单的命名空间为 `SqlServer`。 有关命名空间的详细信息, 请参阅[命名空间](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)。  
  
## <a name="types"></a>类型  
 实体框架的 SqlClient 提供程序提供概念模型类型与 SQL Server 类型之间的映射信息。 有关详细信息, 请参阅[SqlClient For Entity sqlclient 类型](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)。  
  
## <a name="functions"></a>函数  
 实体框架的 SqlClient 提供程序定义提供程序支持的函数列表。 有关支持的函数的列表, 请参阅[SqlClient for 实体框架函数](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [用于实体框架函数的 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [用于实体框架的 SqlClient 类型](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [SqlClient 中的已知问题（实体框架）](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 语言](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [语言参考](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
- [用于实体框架的 SqlClient 提供程序中的已知问题](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
