---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181846"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>不支持 Switch.System.Windows.Forms.DontSupportReentrantFilterMessage 兼容性开关

已在 .NET Framework 4.6.1 中引入 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 兼容性开关，但它在 .NET Core 3.0 上的 Windows 窗体中尚不受支持。

#### <a name="change-description"></a>更改描述

自 .NET Framework 4.6.1 起，`Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 兼容性开关可处理通过自定义 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 实现调用 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 消息时可能引发的 <xref:System.IndexOutOfRangeException> 异常。 有关详细信息，请参阅[缓解：自定义 IMessageFilter.PreFilterMessage 实现](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)。

.NET Core 中尚不支持 `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` 开关。

#### <a name="version-introduced"></a>引入的版本

3.0 预览版 9

#### <a name="recommended-action"></a>建议的操作

删除此开关。 此开关不受支持，且未提供替代功能。

#### <a name="category"></a>类别

Windows 窗体

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
