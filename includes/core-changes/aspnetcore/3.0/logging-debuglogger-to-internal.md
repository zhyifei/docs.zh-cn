---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394173"
---
### <a name="logging-debuglogger-class-made-internal"></a>日志记录：将 DebugLogger 类设为内部类

在 ASP.NET Core 3.0 之前，`DebugLogger` 的访问修饰符为 `public`。 在 ASP.NET Core 3.0 中，访问修饰符更改为 `internal`。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="reason-for-change"></a>更改原因

正在进行更改以便：

* 强制执行与其他记录器（如 `ConsoleLogger`）实现的一致性。
* 减少 API 图面。

#### <a name="recommended-action"></a>建议的操作

使用 <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` 扩展方法来启用调试日志记录。 如果需要手动注册服务，<xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> 也仍为 `public`。

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
