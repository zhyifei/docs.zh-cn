---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394095"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Kestrel：删除并公开传输抽象

作为远离“pubternal”API 的一部分，Kestrel 传输层 API 被公开为 `Microsoft.AspNetCore.Connections.Abstractions` 库中的公共接口。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

- `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` 库中提供传输相关的抽象。
- `ListenOptions.NoDelay` 属性可用。

#### <a name="new-behavior"></a>新行为

- 在 `Microsoft.AspNetCore.Connections.Abstractions` 库中引入 `IConnectionListener` 接口以公开 `...Transport.Abstractions` 库最常用的功能。
- 现在提供传输选项 `NoDelay`（`LibuvTransportOptions` 和 `SocketTransportOptions`）。
- `SchedulingMode` 不再可用。

#### <a name="reason-for-change"></a>更改原因

ASP.NET Core 3.0 已从“pubternal”API 移出。

#### <a name="recommended-action"></a>建议的操作

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

无

<!-- 

### Affected APIs

Not detectable via API analysis

-->
