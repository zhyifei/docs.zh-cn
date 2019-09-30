---
ms.openlocfilehash: e6bb1d53cbe1883b8faef75bd22942bd4f65a5e6
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181800"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a>不支持 Switch.System.Windows.Forms.EnableVisualStyleValidation 兼容性开关

.NET Core 3.0 上的 Windows 窗体不支持 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 兼容性开关。

#### <a name="change-description"></a>更改描述

在 .NET Framework 中，`Switch.System.Windows.Forms.EnableVisualStyleValidation` 兼容性开关使得应用程序可选择不验证以数值格式提供的视觉样式。 

.NET Core 中尚不支持 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 开关。

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
