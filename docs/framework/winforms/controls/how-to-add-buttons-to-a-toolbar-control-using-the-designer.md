---
title: "如何：使用设计器向 ToolBar 控件添加按钮"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5339d946f771b7ba187813dd67860aaa63a21eb3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>如何：使用设计器向 ToolBar 控件添加按钮
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。  
  
 不可或缺的组成部分<xref:System.Windows.Forms.ToolBar>控件是你向其添加的按钮。 这些可用于提供轻松访问菜单命令，或者，或者，您可以将它们放置在另一个区域中的应用程序以向你的菜单结构中均不提供的用户公开的命令的用户界面。  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.ToolBar>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-buttons-at-design-time"></a>若要在设计时添加按钮  
  
1.  选择 <xref:System.Windows.Forms.ToolBar> 控件。  
  
2.  在**属性**窗口中，单击<xref:System.Windows.Forms.ToolBar.Buttons%2A>属性来选择它，然后单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**工具栏按钮集合编辑器**。  
  
3.  使用**添加**和**删除**按钮来添加和删除按钮从<xref:System.Windows.Forms.ToolBar>控件。  
  
4.  配置的属性中的单个按钮**属性**编辑器右侧的窗格中显示的窗口。 下表显示需要考虑一些重要属性。  
  
    |属性|描述|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|设置要显示在下拉列表工具栏按钮的菜单。 工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>。 此属性采用的实例<xref:System.Windows.Forms.ContextMenu>作为引用的类。|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|设置是否部分推送切换式工具栏按钮。 工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>。|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|设置是否切换式工具栏按钮当前处于按下状态。 工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>或<xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>。|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|设置工具栏按钮的样式。 必须是中的值之一<xref:System.Windows.Forms.ToolBarButtonStyle>枚举。|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|显示了按钮的文本字符串。|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|为按钮的工具提示显示的文本。|  
  
5.  单击**确定**以关闭对话框并创建您指定的面板。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolBar>  
 [如何：定义 ToolBar 控件按钮的图标](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [如何：触发工具栏按钮的菜单事件](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar 控件概述](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [ToolBar 控件](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
