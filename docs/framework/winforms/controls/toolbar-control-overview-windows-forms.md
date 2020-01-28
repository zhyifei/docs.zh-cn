---
title: ToolBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: f364e052258703331496f8103b48953a90aa3a9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735485"
---
# <a name="toolbar-control-overview-windows-forms"></a>工具栏控件概述（Windows 窗体）
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。  
  
 Windows 窗体 <xref:System.Windows.Forms.ToolBar> 控件在窗体上用作可显示下拉菜单的行的控件条以及可激活命令的位图按钮。 因此，单击工具栏按钮相当于选择菜单命令。 可将按钮配置为以普通按钮、下拉菜单或分隔符等形式显示和表现。 通常，工具栏包含对应于应用程序菜单结构中的项的按钮和菜单，提供对应用程序最常用的函数和命令的快速访问。  
  
## <a name="working-with-the-toolbar-control"></a>使用 ToolBar 控件  
 <xref:System.Windows.Forms.ToolBar> 控件通常沿其父窗口的顶部 "停靠"，但也可停靠到窗口的任何一侧。 用户将鼠标指针指向工具栏按钮时，工具栏可以显示工具提示。 工具提示是一个小型弹出式窗口，用以简述按钮或菜单的用途。 若要显示工具提示，<xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> 属性必须设置为 `true`。  
  
> [!NOTE]
> 某些应用程序具有与工具栏非常类似的控件，这些控件可“浮动”在应用程序窗口之上并可重新定位。 Windows 窗体 ToolBar 控件不能执行这些操作。  
  
 <xref:System.Windows.Forms.ToolBar.Appearance%2A> 属性设置为 <xref:System.Windows.Forms.ToolBarAppearance>时，工具栏按钮显示为凸起和三维。 您可以将工具栏的 "<xref:System.Windows.Forms.ToolBar.Appearance%2A>" 属性设置为 "<xref:System.Windows.Forms.ToolBarAppearance>，为工具栏及其按钮设置平面外观。 鼠标指针移动到平面按钮时，该按钮的外观变为三维形状。 可使用分隔符将工具栏按钮划分成多个逻辑组。 分隔符是 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 属性设置为 <xref:System.Windows.Forms.ToolBarButtonStyle>的工具栏按钮。 它在工具栏上显示为空白。 工具栏以平面方式显示时，按钮分隔符在按钮之间显示为直线而不是空白。  
  
 <xref:System.Windows.Forms.ToolBar> 控件允许您通过将 <xref:System.Windows.Forms.Button> 对象添加到 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 集合来创建工具栏。 您可以使用 "集合编辑器" 向 <xref:System.Windows.Forms.ToolBar> 控件添加按钮;尽管可以同时分配文本或图像，但是每个 <xref:System.Windows.Forms.Button> 对象都应分配文本或图像。 图像由关联的 [ImageList](imagelist-component-windows-forms.md) 组件提供。 在运行时，可以使用 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> 和 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> 方法，在 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> 中添加或删除按钮。 若要对 <xref:System.Windows.Forms.ToolBar>的按钮进行编程，请使用 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> 类的 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> 属性将代码添加到 <xref:System.Windows.Forms.ToolBar>的 <xref:System.Windows.Forms.ToolBar.ButtonClick> 事件，以确定单击了哪个按钮。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolBar>
- [ToolBar 控件](toolbar-control-windows-forms.md)
- [如何：向 ToolBar 控件添加按钮](how-to-add-buttons-to-a-toolbar-control.md)
- [如何：定义 ToolBar 控件按钮的图标](how-to-define-an-icon-for-a-toolbar-button.md)
- [如何：触发工具栏按钮的菜单事件](how-to-trigger-menu-events-for-toolbar-buttons.md)
