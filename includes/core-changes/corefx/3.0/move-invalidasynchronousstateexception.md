---
ms.openlocfilehash: 19359422f79f8240676b0057c7391f6b06f961ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147544"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>InvalidAsynchronousStateException 已移到另一程序集

<xref:System.ComponentModel.InvalidAsynchronousStateException> 类已移动。

#### <a name="change-description"></a>更改描述

在 .NET Core 2.2 及更低版本中，<xref:System.ComponentModel.InvalidAsynchronousStateException> 位于 System.ComponentModel.TypeConverter 程序集中  。

而自 .NET Core 3.0 起，它位于 System.ComponentModel.Primitives 程序集中  。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="recommended-action"></a>建议操作

此更改仅影响这样的应用程序，它们通过调用 <xref:System.ComponentModel.InvalidAsynchronousStateException> 等方法或调用假设类型位于特定程序集中的 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 的重载，使用反射过程来加载 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>。 若是如此，应更新程序集在方法调用反射的程序集，以反射出类型的新程序集位置。

#### <a name="category"></a>类别

CoreFx

#### <a name="affected-apis"></a>受影响的 API

无。

<!--

### Affected APIs

- Not detectable via API analysis

-->
