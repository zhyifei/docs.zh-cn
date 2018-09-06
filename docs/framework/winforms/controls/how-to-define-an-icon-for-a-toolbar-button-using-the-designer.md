---
title: 如何：使用设计器定义工具栏按钮的图标
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: f26e21d824420fc4ff0480de21f260309c5c2e11
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856603"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>如何：使用设计器定义工具栏按钮的图标
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。  
  
 <xref:System.Windows.Forms.ToolBar> 按钮是可以由用户显示其中方便识别的图标。 这通过添加到图像<xref:System.Windows.Forms.ImageList>组件并将其与<xref:System.Windows.Forms.ToolBar>控件。  
  
 下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.ToolBar>控件和一个<xref:System.Windows.Forms.ImageList>组件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)并[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>若要在设计时设置工具栏按钮的图标  
  
1.  将映像添加到<xref:System.Windows.Forms.ImageList>组件。 有关详细信息，请参阅[如何： 添加或删除 ImageList 图像与设计器](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md)。  
  
2.  选择<xref:System.Windows.Forms.ToolBar>窗体上的控件。  
  
3.  在中**属性**窗口中，将<xref:System.Windows.Forms.ToolBar>控件的<xref:System.Windows.Forms.ToolBar.ImageList%2A>属性设置为<xref:System.Windows.Forms.ImageList>组件。  
  
4.  单击<xref:System.Windows.Forms.ToolBar>控件的<xref:System.Windows.Forms.ToolBar.Buttons%2A>属性来选择它，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**工具栏按钮集合编辑器**。  
  
5.  使用**外**按钮以将按钮添加到<xref:System.Windows.Forms.ToolBar>控件。  
  
6.  中**属性**的右侧窗格中显示的窗口**工具栏按钮集合编辑器**，将<xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>到其中一个的值在列表中，每个工具栏按钮的属性的从映像添加到绘制<xref:System.Windows.Forms.ImageList>组件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolBar>  
 [如何：触发工具栏按钮的菜单事件](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar 控件](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [ImageList 组件](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
