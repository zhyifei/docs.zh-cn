---
title: "如何：从 Control 类继承"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75b9c56d2d9df80745cec2b811c39f5e438d07c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-the-control-class"></a>如何：从 Control 类继承
如果你想要创建使用 Windows 窗体上的完全自定义控件，应从继承<xref:System.Windows.Forms.Control>类。 时从继承<xref:System.Windows.Forms.Control>类要求你执行详细的规划和实现，它还提供的选项的最大范围。 从继承时<xref:System.Windows.Forms.Control>，继承使控件能够运行的最基本功能。 中的固有功能<xref:System.Windows.Forms.Control>类处理通过键盘和鼠标的用户输入，定义的边界和控件大小，提供 windows 句柄，并提供消息处理和安全性。 它没有纳入任何绘图功能（这里指的是控件的图形界面的实际呈现），也没有纳入任何特定的用户交互功能。 必须通过自定义代码提供所有的这些功能。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-create-a-custom-control"></a>创建自定义控件  
  
1.  创建一个新的 **Windows 应用程序**或 **Windows 控件库**项目。  
  
2.  从“项目”菜单中，选择“添加类”。  
  
3.  在“添加新项”对话框中，单击“自定义控件”。  
  
     一个新的自定义控件将被添加到项目中。  
  
4.  按 F7 打开自定义控件的“代码编辑器”。  
  
5.  找到<xref:System.Windows.Forms.Control.OnPaint%2A>方法，将为空除外调用<xref:System.Windows.Forms.Control.OnPaint%2A>基本类的方法。  
  
6.  修改代码以纳入控件所需的任何自定义绘图。  
  
     有关编写代码来呈现控件的图形的信息，请参阅[自定义控件的绘制和呈现](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)。  
  
7.  实现控件将纳入的任何自定义方法、属性或事件。  
  
8.  保存并测试控件。  
  
## <a name="see-also"></a>另请参阅  
 [各种自定义控件](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [如何：从 UserControl 类继承](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [如何：从现有 Windows 窗体控件继承](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [如何：创作 Windows 窗体的控件](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Visual Basic 中继承的事件处理程序疑难解答](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [设计时开发 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
