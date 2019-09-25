---
ms.openlocfilehash: 02dbf5ccca97f5e7d2e1fada39bdf601cf37906f
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119148"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a>`Control.DefaultFont` 更改为 `Segoe UI 9pt` 

#### <a name="change-description"></a>更改描述

在 .NET Framework 中，<xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> 属性设置为 `Microsoft Sans Serif 8pt`。 下图显示了使用默认字体的窗口。

![.NET Framework 中的默认控件字体](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

在 .NET Core 中，从 .NET Core 3.0 开始，该字体设置为 `Segoe UI 9pt`（与 <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType> 字体相同）。 作为此更改的结果，窗体和控件的大小会增长约 27%，以适应新默认字体的更大大小。 例如:

![.NET Core 中的默认控件字体](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

此更改是为了与 [Windows UX 准则](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors)保持一致。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="recommended-action"></a>建议的操作

由于窗体和控件的大小改变，因此请确保应用程序能够正确呈现。

要保留原始字体，请将窗体的默认字体设置为 `Microsoft Sans Serif 8pt`。 例如:

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a>类别

- Windows 窗体

#### <a name="affected-apis"></a>受影响的 API

无。

<!--

### Affected APIs

- Not detectable via API analysis

-->