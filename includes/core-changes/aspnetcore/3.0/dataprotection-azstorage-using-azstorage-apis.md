---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901836"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a>数据保护：DataProtection.AzureStorage 使用新的 Azure 存储 API

<xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> 取决于 [Azure 存储库](https://github.com/Azure/azure-storage-net)。 这些库已重命名其程序集、包和命名空间。 从 ASP.NET Core 3.0 开始，`Microsoft.AspNetCore.DataProtection.AzureStorage` 使用新的带有 `Microsoft.Azure.Storage.` 前缀的 API 和包。

有关 Azure 存储 API 的问题，请使用 <https://github.com/Azure/azure-storage-net>。 有关此问题的讨论，请参阅 [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472)。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

该包引用了 `WindowsAzure.Storage` NuGet 包。

#### <a name="new-behavior"></a>新行为

该包引用 `Microsoft.Azure.Storage.Blob` NuGet 包。

#### <a name="reason-for-change"></a>更改原因

此更改允许 `Microsoft.AspNetCore.DataProtection.AzureStorage` 迁移到建议的 Azure 存储包。

#### <a name="recommended-action"></a>建议操作

如果仍需要将较旧的 Azure 存储 API 与 ASP.NET Core 3.0 一起使用，请将直接依赖项添加到 [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) 包。 此包可以与新的 `Microsoft.Azure.Storage` API 一起安装。

在许多情况下，升级仅涉及更改 `using` 语句以使用新的命名空间：

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
