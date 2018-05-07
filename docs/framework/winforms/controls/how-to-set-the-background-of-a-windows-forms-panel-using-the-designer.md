---
title: 如何：使用设计器设置 Windows 窗体面板的背景
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 896aa61f3f0900760dffd09bcab6a08bbc01628d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>如何：使用设计器设置 Windows 窗体面板的背景
Windows 窗体<xref:System.Windows.Forms.Panel>控件可以显示背景色和背景图像。 <xref:System.Windows.Forms.Control.BackColor%2A>属性设置为包含在面板中，例如标签和单选按钮的控件的背景色。 如果<xref:System.Windows.Forms.Control.BackgroundImage%2A>未设置属性，<xref:System.Windows.Forms.Control.BackColor%2A>选择将填充整个面板。 如果<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性设置，则将在面板中包含的控件后面显示的图像。  
  
 下面的过程需要**Windows 应用程序**具有一个包含窗体项目<xref:System.Windows.Forms.Panel>控件。 有关如何设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>在 Windows 窗体设计器中设置背景  
  
1.  选择 <xref:System.Windows.Forms.Panel> 控件。  
  
2.  在**属性**窗口中，单击箭头按钮旁边<xref:System.Windows.Forms.Control.BackColor%2A>属性来显示一个窗口，其中包含三个选项卡。  
  
3.  选择**自定义**选项卡以显示颜色的调色板。  
  
4.  选择**Web**或**系统**选项卡上显示的预定义颜色的名称，列表，然后选择一种颜色。  
  
5.  在**属性**窗口中，单击箭头按钮旁边<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性。  
  
6.  在**打开**对话框框中，选择你想要显示的文件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Panel 控件](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panel 控件概述](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [如何：使用设计器用 Windows 窗体 Panel 控件对控件进行分组](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
