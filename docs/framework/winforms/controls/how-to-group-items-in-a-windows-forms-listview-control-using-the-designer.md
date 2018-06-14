---
title: 如何：使用设计器对 Windows 窗体 ListView 控件中的项进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: c532cadc5b42c26f1598c4e7586309cf690456bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539332"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器对 Windows 窗体 ListView 控件中的项进行分组
分组功能<xref:System.Windows.Forms.ListView>控制，你可以在组中显示的项的相关的集。 在屏幕上分隔这些组由包含组标题的水平组标题。 你可以使用<xref:System.Windows.Forms.ListView>组以使大型列表对项进行分组按字母顺序，按日期，或任何其他逻辑分组的导航。 下图显示一些分组的项。  
  
 ![ListView 组](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.ListView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
 若要启用分组，你必须首先创建一个或多个<xref:System.Windows.Forms.ListViewGroup>对象在设计器中或以编程方式。 一旦定义了一个组，你可以将项分配给它。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> 组是仅适用于[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]在你的应用程序调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>方法。 在早期的操作系统上与组相关的任何代码有影响，并且组将不会出现。 有关详细信息，请参阅<xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>。  
>   
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a>若要添加或移除在设计器中的组  
  
1.  在**属性**窗口中，单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边按钮<xref:System.Windows.Forms.ListView.Groups%2A>属性。  
  
     **ListViewGroup 集合编辑器**显示。  
  
2.  若要添加组，请单击**添加**按钮。 然后可以设置属性的新组中，如<xref:System.Windows.Forms.ListViewGroup.Header%2A>和<xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>属性。 若要删除某个组，选择它，然后单击**删除**按钮。  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a>若要将项分配给设计器中的组  
  
1.  在**属性**窗口中，单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边按钮<xref:System.Windows.Forms.ListView.Items%2A>属性。  
  
     **列表视图项集合编辑器**显示。  
  
2.  若要添加新项，请单击**添加**按钮。 然后可以设置属性的新项，如<xref:System.Windows.Forms.ListViewItem.Text%2A>和<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>属性。  
  
3.  选择<xref:System.Windows.Forms.ListViewItem.Group%2A>属性，从下拉列表中选择一个组。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [ListView 控件](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [ListView 控件概述](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Windows XP 功能和 Windows 窗体控件](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [如何：使用 Windows 窗体 ListView 控件添加和删除项](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
