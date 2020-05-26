---
ms.openlocfilehash: 97e38685777c7c418c0ccd91f4c433501ecf3aaa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721081"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>不支持 EnableVisualStyleValidation 兼容性开关

.NET Core 3.0 上的 Windows 窗体不支持 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 兼容性开关。

#### <a name="change-description"></a>更改描述

在 .NET Framework 中，`Switch.System.Windows.Forms.EnableVisualStyleValidation` 兼容性开关使得应用程序可选择不验证以数值格式提供的视觉样式。

.NET Core 中尚不支持 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 开关。

#### <a name="version-introduced"></a>引入的版本

3.0 预览版 9

#### <a name="recommended-action"></a>建议操作

删除此开关。 此开关不受支持，且未提供替代功能。

#### <a name="category"></a>类别

Windows 窗体

#### <a name="affected-apis"></a>受影响的 API

- 无

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
