---
title: "如何：显示弹出帮助"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ec4401bb3465f72e4ef732e7554dc64603d700c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-display-pop-up-help"></a>如何：显示弹出帮助
若要在 Windows 窗体上显示帮助的一种方法是通过**帮助**按钮，位于标题栏，可通过访问右侧<xref:System.Windows.Forms.Form.HelpButton%2A>属性。 此类型的“帮助”显示非常适用于对话框。 使用 <xref:System.Windows.Forms.Form.ShowDialog%2A> 方法适度显示的对话框在获取外部帮助系统时会遇到问题，因为必须先关闭模型对话框后才能切换到另一个窗口。 此外，使用**帮助**按钮要求是否有任何**最小化**按钮或**最大化**标题栏中显示的按钮。 这是一个标准对话框约定，而窗体通常具有**最小化**和**最大化**按钮。  
  
 请注意，你还可以使用 <xref:System.Windows.Forms.HelpProvider> 组件将控件链接到帮助系统中的文件，即使你已实现了弹出帮助。 有关详细信息，请参阅[Windows 应用程序中提供帮助](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-display-pop-up-help"></a>显示弹出帮助  
  
1.  拖动[HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)组件从工具箱拖到窗体中。  
  
     它将显示在 Windows 窗体设计器底部的任务栏中。  
  
2.  在“属性”窗口，将 <xref:System.Windows.Forms.Form.HelpButton%2A> 属性设置为 `true`。 这将在窗体的标题栏右侧显示带问号的按钮。  
  
3.  为了显示 <xref:System.Windows.Forms.Form.HelpButton%2A>，必须将窗体的 <xref:System.Windows.Forms.Form.MinimizeBox%2A> 和 <xref:System.Windows.Forms.Form.MaximizeBox%2A> 属性设置为 `false`，将 <xref:System.Windows.Forms.Form.ControlBox%2A> 属性设置为 `true` 以及将 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 属性设置为下列值之一：<xref:System.Windows.Forms.FormBorderStyle.FixedSingle>、<xref:System.Windows.Forms.FormBorderStyle.Fixed3D>、<xref:System.Windows.Forms.FormBorderStyle.FixedDialog> 或 <xref:System.Windows.Forms.FormBorderStyle.Sizable>。  
  
4.  选择想在你的窗体上显示帮助的控件，然后在“属性”窗口设置“帮助”字符串。 这是将在类似于一个窗口中显示的文本的字符串[工具提示](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)。  
  
5.  按 F5 。  
  
6.  按**帮助**按钮标题栏上，然后单击在其设置的帮助字符串的控件。  
  
## <a name="see-also"></a>请参阅  
 [使用工具提示的控件帮助](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [在 Windows 窗体中集成用户帮助](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows 窗体](../../../../docs/framework/winforms/index.md)
