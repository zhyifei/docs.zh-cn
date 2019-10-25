---
ms.openlocfilehash: 32c7f4e9e4736145f9275b74f34c04404e7c770a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394201"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a>缓存：Microsoft.Extensions.Caching.SqlServer 使用新 SqlClient 包

`Microsoft.Extensions.Caching.SqlServer` 包将使用新的 `Microsoft.Data.SqlClient` 包，而不是 `System.Data.SqlClient` 包。 此更改可能会导致轻微的行为中断性变更。 有关详细信息，请参阅[引入新的 Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/)。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

`Microsoft.Extensions.Caching.SqlServer` 包已使用过 `System.Data.SqlClient` 包。

#### <a name="new-behavior"></a>新行为

`Microsoft.Extensions.Caching.SqlServer` 现在使用 `Microsoft.Data.SqlClient` 包。

#### <a name="reason-for-change"></a>更改原因

`Microsoft.Data.SqlClient` 是从 `System.Data.SqlClient` 生成的新包。 从现在开始，所有新功能的工作都在该包中进行。

#### <a name="recommended-action"></a>建议的操作

客户无需担心此中断性变更，除非他们使用 `Microsoft.Extensions.Caching.SqlServer` 包返回的类型，并将它们强制转换为 `System.Data.SqlClient` 类型。 例如，如果有人将 `DbConnection` 强制转换为[旧的 SqlConnection 类型](xref:System.Data.SqlClient.SqlConnection)，则需要将转换更改为新的 `Microsoft.Data.SqlClient.SqlConnection` 类型。 

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

无

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
