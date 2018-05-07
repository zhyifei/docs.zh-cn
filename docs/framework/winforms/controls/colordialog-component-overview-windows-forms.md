---
title: ColorDialog 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 9b4fb545a2ed35a9c7bad5e28c28d3ec42870860
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="colordialog-component-overview-windows-forms"></a>ColorDialog 组件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.ColorDialog>组件是预配置的对话框，它允许用户选择一种颜色的调色板并向此调色板添加自定义颜色。 此对话框与在其他基于 Windows 的应用程序中看到的用于选择颜色的对话框相同。 在基于 Windows 的应用程序中，使用它作为一种替代配置自己对话框的简单解决方案。  
  
 在中返回在对话框中选定的颜色<xref:System.Windows.Forms.ColorDialog.Color%2A>属性。 如果<xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>属性设置为`false`、"自定义颜色"按钮处于禁用状态和用户仅限于调色板中的预定义颜色。 如果<xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>属性设置为`true`，用户无法选择抖色的颜色。 若要显示对话框中，必须调用其<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog 组件](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [对话框控件和组件](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 [如何：更改 Windows 窗体 ColorDialog 组件的外观](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
