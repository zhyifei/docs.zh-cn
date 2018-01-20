---
title: "ListView 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b79fecb0a537f4c568b4a57e9ce2bfab8d8e1005
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="listview-control-overview-windows-forms"></a>ListView 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ListView> 控件显示带图标的项列表。 你可以使用列表视图创建类似 Windows 资源管理器右窗格的用户界面。 在控件有四种视图模式： 视图、 SmallIcon、 列表和详细信息。  
  
## <a name="what-you-can-do-with-the-listview-control"></a>如何使用 ListView 控件  
  
> [!NOTE]
>  其他视图模式中，磁贴，才在 Windows XP 和 Windows Server 2003 操作系统上可用。 有关详细信息，请参阅[如何： 在 Windows 窗体 ListView 控件中启用平铺视图](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md)。  
  
 视图模式显示大图标旁边的项文本;如果控件是足够大，这些项将显示在多个列。 SmallIcon 模式均相同，只不过它将显示小图标。 列表视图模式显示小图标，但始终在单个列。 详细信息模式显示多个列中的项。 有关详细信息，请参阅[如何： 向 Windows 窗体 ListView 控件添加列](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)。 视图模式由<xref:System.Windows.Forms.ListView.View%2A>属性。 所有视图模式可以显示来自图像列表的图像。 有关详细信息，请参阅[如何： 为 Windows 窗体 ListView 控件显示图标](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)。  
  
 下表列出了一些的<xref:System.Windows.Forms.ListView>成员以及它们是在中有效的视图。  
  
|ListView 成员|视图|  
|---------------------|----------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A> 属性|<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A> 属性|<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A> 方法|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.Columns%2A> 属性|<xref:System.Windows.Forms.View.Details> 或 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem>事件|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A> 方法|<xref:System.Windows.Forms.View.Details>、<xref:System.Windows.Forms.View.List> 或 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A> 方法|<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A> 方法|<xref:System.Windows.Forms.View.Details> 或 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.Groups%2A> 属性|除之外的所有视图<xref:System.Windows.Forms.View.List>|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A> 属性|<xref:System.Windows.Forms.View.Details>。|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A> 属性|<xref:System.Windows.Forms.View.LargeIcon>、<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.Tile>|  
  
 键属性的<xref:System.Windows.Forms.ListView>控件是<xref:System.Windows.Forms.ListView.Items%2A>，其中包含由控件显示的项。 <xref:System.Windows.Forms.ListView.SelectedItems%2A>属性包含控件中当前选定的项的集合。 用户可以选择多个项，例如，拖放到另一个控件，一次的多个项，如果<xref:System.Windows.Forms.ListView.MultiSelect%2A>属性设置为`true`。 <xref:System.Windows.Forms.ListView>控件可以显示项旁的复选框，如果<xref:System.Windows.Forms.ListView.CheckBoxes%2A>属性设置为`true`。  
  
 <xref:System.Windows.Forms.ListView.Activation%2A>属性确定用户要激活列表中的某个项而必须执行的操作类型： 的选项为<xref:System.Windows.Forms.ItemActivation.Standard>， <xref:System.Windows.Forms.ItemActivation.OneClick>，和<xref:System.Windows.Forms.ItemActivation.TwoClick>。 <xref:System.Windows.Forms.ItemActivation.OneClick>激活要求通过单击来激活选项。 <xref:System.Windows.Forms.ItemActivation.TwoClick>激活时，要求用户通过双击来激活项;单击一次更改的项文本的颜色。 <xref:System.Windows.Forms.ItemActivation.Standard>激活要求用户双击以激活某个项但该项不会更改外观。  
  
 <xref:System.Windows.Forms.ListView>控件还支持视觉样式和提供的其他功能在 Windows XP 平台上，包括分组、 磁贴视图，以及插入标记。 有关详细信息，请参阅[Windows XP 功能和 Windows 窗体控件](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ListView>  
 [ListView 控件](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [如何：使用 Windows 窗体 ListView 控件添加和删除项](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [如何：向 Windows 窗体 ListView 控件添加列](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [如何：显示 Windows 窗体 ListView 控件的图标](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [如何：使用 Windows 窗体 ListView 控件在列中显示子项](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [如何：选择 Windows 窗体 ListView 控件中的项](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 [如何：在 Windows 窗体 ListView 控件中对项进行分组](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)  
 [如何：在 Windows 窗体 ListView 控件中显示插入标记](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 [如何：向 ListView 控件添加搜索功能](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
 [如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [如何：使用 Windows 窗体创建多窗格用户界面](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)
