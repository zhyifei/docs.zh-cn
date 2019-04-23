---
ms.openlocfilehash: fcaee245e98dfe71beb4042a2664a14b64cf2398
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803339"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection 可以不再连接到 SQL Server 1997 或使用 VIA 适配器的数据库

|   |   |
|---|---|
|详细信息|不再支持使用[虚拟接口适配器 (VIA) 协议](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229%28v=sql.105%29)连接到 SQL Server 数据库。 连接字符串中可以见到用于连接到 SQL Server 数据库的协议。 VIA 连接将包含 via:&lt;servername&gt;。 如果此应用通过协议而不是 VIA （例如 tcp: 或 np:）连接到 SQL，则不会遇到中断的更改。此外，也不再支持连接到 SQL Server 7 (1997)。|
|建议|VIA 协议已弃用，因此，应使用备用协议连接到 SQL 数据库。 使用的最常见的协议是 TCP/IP。 若要详细了解如何通过 TCP/IP 进行连接，请参阅[对数据库实例启用 TCP/IP 协议](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90))。 如果只能从 Intranet 访问数据库，在网络速度慢时，共享的管道协议可能会提供更好的性能。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|
