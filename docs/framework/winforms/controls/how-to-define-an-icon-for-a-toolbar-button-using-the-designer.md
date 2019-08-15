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
ms.openlocfilehash: 5de7645ecbf2123df849046a152643cd629b4898
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038227"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>如何：使用设计器定义工具栏按钮的图标

> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。

<xref:System.Windows.Forms.ToolBar>按钮能够显示它们中的图标, 用户可以轻松识别。 这是通过向<xref:System.Windows.Forms.ImageList>组件添加图像并将其<xref:System.Windows.Forms.ToolBar>与控件相关联实现的。

下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.ToolBar>包含控件和<xref:System.Windows.Forms.ImageList>组件的窗体。 有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。


### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>在设计时设置工具栏按钮的图标

1. 向<xref:System.Windows.Forms.ImageList>组件添加映像。 有关详细信息，请参阅[如何：在设计器](how-to-add-or-remove-imagelist-images-with-the-designer.md)中添加或删除 ImageList 映像。

2. 选择窗<xref:System.Windows.Forms.ToolBar>体上的控件。

3. 在 "**属性**" 窗口中, <xref:System.Windows.Forms.ToolBar>将控件<xref:System.Windows.Forms.ToolBar.ImageList%2A> <xref:System.Windows.Forms.ImageList>的属性设置为组件。

4. <xref:System.Windows.Forms.ToolBar.Buttons%2A> ![](./media/visual-studio-ellipsis-button.png)单击控件的属性以将其选中, 然后单击省略号 ("Visual Studio" 的属性窗口中的省略号按钮 (...), 以打开 " **ToolBarButton 集合编辑器**"。 <xref:System.Windows.Forms.ToolBar>

5. 使用 "**添加**" 按钮可将按钮添加<xref:System.Windows.Forms.ToolBar>到控件。

6. 在**ToolBarButton 集合编辑器**右侧窗格中显示的 " <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> **属性**" 窗口中, 将每个工具栏按钮的属性设置为列表中的值之一, 此列表中的值从添加到<xref:System.Windows.Forms.ImageList>组件。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolBar>
- [如何：工具栏按钮的触发器菜单事件](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar 控件](toolbar-control-windows-forms.md)
- [ImageList 组件](imagelist-component-windows-forms.md)
