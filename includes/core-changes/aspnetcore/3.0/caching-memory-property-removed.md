---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394273"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>缓存：已删除 CompactOnMemoryPressure 属性

ASP.NET Core 3.0 版本已删除[过时的 MemoryCacheOptions API](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18)。

#### <a name="change-description"></a>更改描述

此更改是对 [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221) 的后续补充。 有关讨论，请参阅 [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062)。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

`MemoryCacheOptions.CompactOnMemoryPressure` 属性可用。

#### <a name="new-behavior"></a>新行为

`MemoryCacheOptions.CompactOnMemoryPressure` 属性已被删除。

#### <a name="reason-for-change"></a>更改原因

自动压缩缓存会引起问题。 若要避免意外行为，只应在需要时压缩缓存。

#### <a name="recommended-action"></a>建议的操作

若要压缩缓存，请向下转换到 `MemoryCache` 并在需要时调用 `Compact`。

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
