---
ms.openlocfilehash: 7b5ae84d02b83a10a4b9e002fc2ed4ee0833b84c
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198365"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP：已删除 DefaultHttpContext 扩展性

作为 ASP.NET Core 3.0 性能改进的一部分，已删除 `DefaultHttpContext` 的扩展性。 此类现在为 `sealed`。 有关详细信息，请参阅 [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504)。

如果单元测试使用 `Mock<DefaultHttpContext>`，请改用 `Mock<HttpContext>`。

有关讨论，请参阅 [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534)。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

类可从 `DefaultHttpContext` 派生。

#### <a name="new-behavior"></a>新行为

类不可从 `DefaultHttpContext` 派生。

#### <a name="reason-for-change"></a>更改原因

最初提供扩展性是为了允许 `HttpContext` 合并，但它引入了不必要的复杂性并妨碍了其他优化。

#### <a name="recommended-action"></a>建议的操作

如果在单元测试中使用 `Mock<DefaultHttpContext>`，请改为开始使用 `Mock<HttpContext>`。

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
