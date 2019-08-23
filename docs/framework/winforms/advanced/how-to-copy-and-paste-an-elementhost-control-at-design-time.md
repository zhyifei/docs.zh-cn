---
title: 如何：在设计时复制并粘贴 ElementHost 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dfe5244e0c5b61fdf6d940dd16d8c280f013b12c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666183"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>如何：复制并粘贴 ElementHost 控件

此过程演示如何在 Visual Studio 中的 Windows 窗体上复制 Windows Presentation Foundation (WPF) 控件。

1. 在 Visual Studio 中, 将一个新<xref:System.Windows.Controls.UserControl>的 WPF 添加到 Windows 窗体项目。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参见[演练：在设计时](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)在 Windows 窗体上创建新的 WPF 内容。

2. 在 "**属性**" 窗口中<xref:System.Windows.FrameworkElement.Width%2A> , 将的和<xref:System.Windows.FrameworkElement.Height%2A>属性`UserControl1`的值设置为**200**。

3. 将<xref:System.Windows.Controls.Control.Background%2A>属性的值设置为**蓝色**。

4. 生成项目。

5. 在 Windows 窗体设计器中打开 `Form1`。

6. 从 "**工具箱**" 中, 将的`UserControl1`实例拖到窗体上。

   `UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

7. 选中此选项后, 按**Ctrl**+C 将其复制到剪贴板。 `elementHost1`

8. 按**Ctrl**+**V**将复制的控件粘贴到窗体上。

   在窗<xref:System.Windows.Forms.Integration.ElementHost>体上`elementHost2`创建一个名为的新控件。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [迁移和互操作性](../../wpf/advanced/migration-and-interoperability.md)
- [使用 WPF 控件](using-wpf-controls.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)
