---
ms.openlocfilehash: 07527c247e6ccd53d2a77793946ffc796c3e1cbb
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181773"
---
### <a name="switchsystemwindowsformsuselegacyimages-compatibility-switch-not-supported"></a>不支持 Switch.System.Windows.Forms.UseLegacyImages 兼容性开关

已在 .NET Framework 4.8 中引入 `Switch.System.Windows.Forms.UseLegacyImages` 兼容性开关，但它在 .NET Core 3.0 上的 Windows 窗体中尚不受支持。

#### <a name="change-description"></a>更改描述

自 .NET Framework 4.8 起，`Switch.System.Windows.Forms.UseLegacyImages` 兼容性开关会处理高 DPI 环境中 ClickOnce 方案内可能出现的图像缩放问题。 如果设置为 `true`，则用户可通过此开关在缩放比例设置为大于 100% 的高 DPI 显示器上还原旧的图像缩放行为。 有关详细信息，请参阅 GitHub 上的 [.NET Framework 4.8 发行说明](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce)。

.NET Core 中尚不支持 `Switch.System.Windows.Forms.UseLegacyImages` 开关。

#### <a name="version-introduced"></a>引入的版本

3.0 预览版 9

#### <a name="recommended-action"></a>建议的操作

删除此开关。 此开关不受支持，且未提供替代功能。

#### <a name="category"></a>类别

Windows 窗体

#### <a name="affected-apis"></a>受影响的 API

- 无

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
