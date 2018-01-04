---
title: "如何：使用设计器用 Windows 窗体创建多窗格用户界面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6cfd9f258aa7c43f4c98e475c40af7fe7d9c286b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>如何：使用设计器用 Windows 窗体创建多窗格用户界面
在下面的过程中，将创建多窗格用户界面类似于在 Microsoft Outlook 中与使用**文件夹**列表中，**消息**窗格中，和一个**预览**窗格。 这种安排主要通过停靠处理该窗体控件。  
  
 当你将控件停靠时，你确定控件固定的父容器的边缘。 因此，如果你设置<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Right>，将其父控件的右边缘停靠的控件的右边缘。 此外，该控件的停靠的边缘是调整大小，以匹配它的容器控件。 有关详细信息，如何<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性会发生作用，请参阅[如何： 在 Windows 窗体上停靠控件](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)。  
  
 此过程侧重于排列<xref:System.Windows.Forms.SplitContainer>和其他控件在窗体上，而不添加使模拟 Microsoft Outlook 应用程序的功能。  
  
 若要创建此用户界面，你将中的所有控件<xref:System.Windows.Forms.SplitContainer>控件，它包含<xref:System.Windows.Forms.TreeView>左侧面板中的控件。 右侧面板<xref:System.Windows.Forms.SplitContainer>控件包含第二个<xref:System.Windows.Forms.SplitContainer>控件替换为<xref:System.Windows.Forms.ListView>控件上述<xref:System.Windows.Forms.RichTextBox>控件。 这些<xref:System.Windows.Forms.SplitContainer>控件启用独立调整窗体上的其他控件的大小。 你可以调整此过程制作出的你自己的自定义用户界面中的方法。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>若要在设计时创建的 Outlook 样式的用户界面  
  
1.  创建新的 Windows 应用程序项目。 有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。  
  
2.  拖动<xref:System.Windows.Forms.SplitContainer>控件从**工具箱**到窗体。 在**属性**窗口中，设置<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>。  
  
3.  拖动<xref:System.Windows.Forms.TreeView>控件从**工具箱**到左侧的面板<xref:System.Windows.Forms.SplitContainer>控件。 在**属性**窗口中，设置<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Left>通过单击左侧面板中单击向下箭头时显示的值编辑器。  
  
4.  将另一个<xref:System.Windows.Forms.SplitContainer>控件从**工具箱**; 将其放在右侧面板中的<xref:System.Windows.Forms.SplitContainer>向窗体添加的控件。 在**属性**窗口中，设置<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>和<xref:System.Windows.Forms.SplitContainer.Orientation%2A>属性<xref:System.Windows.Forms.Orientation.Horizontal>。  
  
5.  拖动<xref:System.Windows.Forms.ListView>控件从**工具箱**到第二个面板右上<xref:System.Windows.Forms.SplitContainer>向窗体添加的控件。 将 <xref:System.Windows.Forms.ListView> 控件的 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。  
  
6.  拖动<xref:System.Windows.Forms.RichTextBox>控件从**工具箱**到第二个下方面板<xref:System.Windows.Forms.SplitContainer>控件。 将 <xref:System.Windows.Forms.RichTextBox> 控件的 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。  
  
     此时，如果按 F5 运行该应用程序时，窗体将显示由三部分用户界面，类似于 Microsoft Outlook。  
  
    > [!NOTE]
    >  当将鼠标指针放在拆分条中在任一<xref:System.Windows.Forms.SplitContainer>控件，你可以调整内部维度的大小。  
  
     此时在应用程序开发中，具有制作复杂的用户界面。 下一步的步骤再继续进行的编程的应用程序本身，可能是通过连接<xref:System.Windows.Forms.TreeView>控件和<xref:System.Windows.Forms.ListView>某种类型的数据源的控件。 有关连接到数据的控件的详细信息，请参阅[数据绑定和 Windows 窗体](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer 控件](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
