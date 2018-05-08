---
title: Windows 窗体控件开发基础知识
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: b455912468376d2f5de0ac1f30b4fcab5bb93309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-control-development-basics"></a>Windows 窗体控件开发基础知识
Windows 窗体控件是直接或间接派生自的类<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。 以下列表描述用于开发 Windows 窗体控件的常见方案：  
  
-   组合现有控件来创作复合控件。  
  
     复合控件封装为控件可重复使用的用户界面。 复合控件的一个示例是一个文本框和重置按钮组成一个控件。 可视化设计器提供了用于创建复合控件的丰富支持。 若要创作复合控件，派生自<xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>。 基类<xref:System.Windows.Forms.UserControl>提供了键盘路由子控件，并使子控件作为组进行工作。 有关详细信息，请参阅[开发复合 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)。  
  
-   将扩展现有控件自定义项，或将添加到其功能。  
  
     无法更改其颜色的按钮和一个按钮，具有附加属性，用于跟踪多少次单击它是扩展控件的示例。 你可以从其派生和重写或添加属性、 方法和事件以自定义任何 Windows 窗体控件。  
  
-   创作的控件，不会组合或扩展现有的控件。  
  
     在此方案中，从基类派生你的控件<xref:System.Windows.Forms.Control>。 你可以添加，以及重写属性、 方法和事件的基类。 若要开始，请参阅[如何： 开发简单的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)。  
  
 Windows 窗体控件的基类<xref:System.Windows.Forms.Control>，提供所需的客户端基于 Windows 的应用程序中的可视显示管道。 <xref:System.Windows.Forms.Control> 提供的窗口句柄、 处理消息路由，并提供鼠标和键盘事件，以及许多其他用户界面事件。 它提供高级的布局，如具有属性特定于可视显示<xref:System.Windows.Forms.Control.ForeColor%2A>， <xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.Height%2A>， <xref:System.Windows.Forms.Control.Width%2A>，等等。 此外，它提供了安全，线程处理支持和 ActiveX 控件与互操作性。 由于基类提供了大量基础结构，因此使开发自己的 Windows 窗体控件变得相对简单。  
  
## <a name="see-also"></a>请参阅  
 [如何：开发简单的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [开发复合 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [如何：创建显示进度的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)  
 [各种自定义控件](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
