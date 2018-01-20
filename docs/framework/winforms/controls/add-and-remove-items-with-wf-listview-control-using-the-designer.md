---
title: "如何：使用设计器用 Windows 窗体 ListView 控件添加和移除项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89665e5b4076c8746fbca939fd3f5491b03afd28
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器用 Windows 窗体 ListView 控件添加和移除项
将项添加到 Windows 窗体的过程<xref:System.Windows.Forms.ListView>控件包含主要的指定项并将属性分配给它。 可以在任何时候完成添加或删除列表项。  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.ListView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-or-remove-items-using-the-designer"></a>若要添加或删除项使用设计器  
  
1.  选择 <xref:System.Windows.Forms.ListView> 控件。  
  
2.  在**属性**窗口中，单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边按钮<xref:System.Windows.Forms.ListView.Items%2A>属性。  
  
     **列表视图项集合编辑器**显示。  
  
3.  若要添加项，请单击**添加**按钮。 然后可以设置属性的新项，如<xref:System.Windows.Forms.ListView.Text%2A>和<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>属性。  
  
4.  若要移除一个项，请选择它，然后单击**删除**按钮。  
  
## <a name="see-also"></a>请参阅  
 [ListView 控件概述](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [如何：向 Windows 窗体 ListView 控件添加列](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [如何：使用 Windows 窗体 ListView 控件在列中显示子项](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [如何：显示 Windows 窗体 ListView 控件的图标](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [如何：在 Windows 窗体 ListView 控件中对项进行分组](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)
