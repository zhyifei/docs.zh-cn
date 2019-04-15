---
ms.openlocfilehash: 33ad1c044001e0a8d09708cc7a1f06e05cb307de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235084"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>ObjectContext.CreateDatabase 和 DbProviderServices.CreateDatabase 方法处理异常的方式不同

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，如果数据库创建失败，<code>CreateDatabase</code> 方法将尝试删除空数据库。 如果该操作成功，将传播原始 <xref:System.Data.SqlClient.SqlException?displayProperty=name>（而非始终在 .NET Framework 4.0 中引发的 <xref:System.InvalidOperationException?displayProperty=name>）|
|建议|在执行 <xref:System.Data.Objects.ObjectContext.CreateDatabase> 或 <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> 时如果捕获到 <xref:System.InvalidOperationException?displayProperty=name>，现在也应会捕获到 SQLExceptions。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
