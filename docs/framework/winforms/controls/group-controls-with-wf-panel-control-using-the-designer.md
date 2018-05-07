---
title: 如何：使用设计器用 Windows 窗体面板控件对控件进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 1cf4519a9aaaa1c4f0df321ab38c3f543c87b2a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>如何：使用设计器用 Windows 窗体面板控件对控件进行分组
Windows 窗体<xref:System.Windows.Forms.Panel>控制用于其他控件进行分组。 有三个原因与组控件。 有 visual 清除用户接口; 相关的窗体元素的分组另一种是以编程方式分组的单选按钮例如;最后一个是用于在设计时将控件移作为一个单元。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-create-a-group-of-controls"></a>若要创建一组控件  
  
1.  拖动<xref:System.Windows.Forms.Panel>控件从**Windows 窗体**拖到窗体工具箱选项卡中的。  
  
2.  将其他控件添加到面板中，绘制面板内的每个。  
  
     如果你有想要将括在一个面板中的现有控件，可以选择所有控件，将它们剪切到剪贴板，再都选择<xref:System.Windows.Forms.Panel>控制，然后将其粘贴到面板中。 你还可以将其拖到面板。  
  
3.  （可选）如果你想要将边框添加到面板，设置其<xref:System.Windows.Forms.BorderStyle>属性。 有三个选择： <xref:System.Windows.Forms.BorderStyle.Fixed3D>， <xref:System.Windows.Forms.BorderStyle.FixedSingle>，和<xref:System.Windows.Forms.BorderStyle.None>。  
  
## <a name="see-also"></a>请参阅  
 [Panel 控件](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panel 控件概述](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [如何：设置 Panel 控件的背景](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
