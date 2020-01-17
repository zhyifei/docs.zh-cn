---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902055"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP：已删除 DefaultHttpContext 扩展性

作为 ASP.NET Core 3.0 性能改进的一部分，已删除 `DefaultHttpContext` 的扩展性。 此类现在为 `sealed`。 有关详细信息，请参阅 [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504)。

如果单元测试使用 `Mock<DefaultHttpContext>`，请改用 `Mock<HttpContext>`。

有关讨论，请参阅 [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534)。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

类可从 `DefaultHttpContext` 派生。

#### <a name="new-behavior"></a>新行为

类不可从 `DefaultHttpContext` 派生。

#### <a name="reason-for-change"></a>更改原因

最初提供扩展性是为了允许 `HttpContext` 合并，但它引入了不必要的复杂性并妨碍了其他优化。

#### <a name="recommended-action"></a>建议操作

如果在单元测试中使用 `Mock<DefaultHttpContext>`，请改为开始使用 `Mock<HttpContext>`。

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
