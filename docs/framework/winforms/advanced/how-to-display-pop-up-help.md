---
title: 如何：显示弹出帮助
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: bf3bcbff0cd6f3bbf71e96e748cb170d5ce68dfc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211403"
---
# <a name="how-to-display-pop-up-help"></a>如何：显示弹出帮助

若要在 Windows 窗体上显示帮助的一种方法是通过**帮助**按钮，位于标题栏，可通过访问右侧<xref:System.Windows.Forms.Form.HelpButton%2A>属性。 此类型的“帮助”显示非常适用于对话框。 使用 <xref:System.Windows.Forms.Form.ShowDialog%2A> 方法适度显示的对话框在获取外部帮助系统时会遇到问题，因为必须先关闭模型对话框后才能切换到另一个窗口。 此外，使用**帮助**按钮，则需要无**最小化**按钮或**最大化**按钮的标题栏中所示。 这是一个标准对话框约定，而窗体通常具有**最小化**并**最大化**按钮。

此外可以使用<xref:System.Windows.Forms.HelpProvider>组件将控件链接到的文件在帮助系统中，即使已实现弹出帮助。 有关详细信息，请参阅[Windows 应用程序中提供帮助](how-to-provide-help-in-a-windows-application.md)。

## <a name="display-pop-up-help"></a>显示弹出帮助

1. 在 Visual Studio 中，拖动[HelpProvider](../controls/helpprovider-component-windows-forms.md)组件从工具箱拖到窗体。

   它将显示在 Windows 窗体设计器底部的任务栏中。

2. 在“属性”窗口，将 <xref:System.Windows.Forms.Form.HelpButton%2A> 属性设置为 `true`。 这将在窗体的标题栏右侧显示带问号的按钮。

3. 为了显示 <xref:System.Windows.Forms.Form.HelpButton%2A>，必须将窗体的 <xref:System.Windows.Forms.Form.MinimizeBox%2A> 和 <xref:System.Windows.Forms.Form.MaximizeBox%2A> 属性设置为 `false`，将 <xref:System.Windows.Forms.Form.ControlBox%2A> 属性设置为 `true` 以及将 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 属性设置为下列值之一：<xref:System.Windows.Forms.FormBorderStyle.FixedSingle>、<xref:System.Windows.Forms.FormBorderStyle.Fixed3D>、<xref:System.Windows.Forms.FormBorderStyle.FixedDialog> 或 <xref:System.Windows.Forms.FormBorderStyle.Sizable>。

4. 选择想在你的窗体上显示帮助的控件，然后在“属性”窗口设置“帮助”字符串。 这是将类似于窗口中显示的文本的字符串[工具提示](../controls/tooltip-component-windows-forms.md)。

5. 按 F5 。

6. 按**帮助**按钮的标题栏上，单击设置帮助字符串的控件。

## <a name="see-also"></a>请参阅

- [使用工具提示的控件帮助](control-help-using-tooltips.md)
- [在 Windows 窗体中集成用户帮助](integrating-user-help-in-windows-forms.md)
- [Windows 窗体](../index.md)
