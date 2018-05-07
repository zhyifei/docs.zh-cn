---
title: Panel 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 1ba766629f923b091459531ce74d28dca4b4ea0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="panel-control-overview-windows-forms"></a>Panel 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.Panel>控件用于提供其他控件可识别分组。 通常，你可以使用面板函数细分窗体。 例如，你可以指定邮件的选项，如使用哪夜间运输工具订购窗体。 分组在面板中的所有选项为用户提供一个逻辑的视觉提示。 在设计时所有可以轻松地移动控件 — 当您移动<xref:System.Windows.Forms.Panel>控制，所有其所含的控件移动，太。 在一个面板中分组控件可以通过其<xref:System.Windows.Forms.Control.Controls%2A>属性。 此属性返回的集合<xref:System.Windows.Forms.Control>实例，因此你通常需要强制转换控件检索到它的特定类型的这种方式。  
  
## <a name="panel-versus-groupbox"></a>与组合框的面板  
 <xref:System.Windows.Forms.Panel>控件是类似于<xref:System.Windows.Forms.GroupBox>控制; 但是，仅<xref:System.Windows.Forms.Panel>控件可以具有滚动条仅和<xref:System.Windows.Forms.GroupBox>控件显示的标题。  
  
## <a name="key-properties"></a>键属性  
 若要显示滚动条，设置<xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A>属性`true`。 此外可以自面板的外观定义通过设置<xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.BackgroundImage%2A>，和<xref:System.Windows.Forms.Panel.BorderStyle%2A>属性。 有关详细信息<xref:System.Windows.Forms.Control.BackColor%2A>和<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性，请参阅[如何： 设置面板的背景](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)。 <xref:System.Windows.Forms.Panel.BorderStyle%2A>属性确定是否为无可视边框概述面板 (<xref:System.Windows.Forms.BorderStyle.None>)，纯行 (<xref:System.Windows.Forms.BorderStyle.FixedSingle>)，或隐藏的行 (<xref:System.Windows.Forms.BorderStyle.Fixed3D>)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Panel>  
 [GroupBox 控件](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)  
 [如何：使用设计器用 Windows 窗体 Panel 控件对控件进行分组](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)  
 [如何：使用设计器设置 Windows 窗体 Panel 控件的背景](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
