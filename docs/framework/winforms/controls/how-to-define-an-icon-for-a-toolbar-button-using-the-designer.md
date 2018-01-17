---
title: "如何：使用设计器定义工具栏按钮的图标"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90e72b2516efab3bc5b5d8cc7cacb66f149f3a66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>如何：使用设计器定义工具栏按钮的图标
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。  
  
 <xref:System.Windows.Forms.ToolBar>按钮就能够自身中显示图标以便于识别用户。 这将通过添加到图像实现<xref:System.Windows.Forms.ImageList>组件并将其与关联<xref:System.Windows.Forms.ToolBar>控件。  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.ToolBar>控件和<xref:System.Windows.Forms.ImageList>组件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>若要在设计时设置工具栏按钮的图标  
  
1.  将映像添加到<xref:System.Windows.Forms.ImageList>组件。 有关详细信息，请参阅[如何： 添加或移除 ImageList 图像与设计器](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md)。  
  
2.  选择<xref:System.Windows.Forms.ToolBar>窗体上的控件。  
  
3.  在**属性**窗口中，设置<xref:System.Windows.Forms.ToolBar>控件的<xref:System.Windows.Forms.ToolBar.ImageList%2A>属性<xref:System.Windows.Forms.ImageList>组件。  
  
4.  单击<xref:System.Windows.Forms.ToolBar>控件的<xref:System.Windows.Forms.ToolBar.Buttons%2A>属性以选中它，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**工具栏按钮集合编辑器**。  
  
5.  使用**添加**按钮以将按钮添加到<xref:System.Windows.Forms.ToolBar>控件。  
  
6.  在**属性**的右侧的窗格中显示的窗口**工具栏按钮集合编辑器**，将其设置<xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>的某个值在列表中，每个工具栏按钮的属性的从添加到映像绘制<xref:System.Windows.Forms.ImageList>组件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolBar>  
 [如何：触发工具栏按钮的菜单事件](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar 控件](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [ImageList 组件](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
