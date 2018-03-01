---
title: "如何：在 TableLayoutPanel 控件中编辑行和列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bf54a02a409bead598a4e98315d5709e55677f3b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控件中编辑行和列
你可以使用集合编辑器的<xref:System.Windows.Forms.TableLayoutPanel>控件，调用**列和行样式**对话框中，若要编辑的行和控件的列。  
  
> [!NOTE]
>  如果你想要跨多个行或列的控件，设置`RowSpan`和`ColumnSpan`控件上的属性。 有关详细信息，请参阅 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。  
>   
>  如果你想要在单元格中，控件对齐，或者如果想要在单元格中拉伸控件，使用控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性。 有关详细信息，请参阅 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。  
>   
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-edit-rows-and-columns"></a>若要编辑行和列  
  
1.  拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。  
  
2.  单击<xref:System.Windows.Forms.TableLayoutPanel>控件的智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))，然后选择**编辑行和列**以打开**列和行样式**对话框。 你也可以右键单击<xref:System.Windows.Forms.TableLayoutPanel>控件，然后选择**编辑行和列**从快捷菜单。  
  
3.  若要添加或删除列，选择**列**从**成员类型**下拉列表框。  
  
4.  若要添加或删除行，选择**行**从**成员类型**下拉列表框。  
  
5.  单击**添加**按钮以将行或列添加到末尾**成员**列表。  
  
6.  单击**插入**按钮以在列表中添加行或当前选定项之前的列。  
  
7.  如果在添加行或列，选择**大小类型**新行或列。 有关详细信息，请参阅<xref:System.Windows.Forms.SizeType>。  
  
8.  若要删除的行或列，请单击**删除**按钮以删除中的当前选定的项**成员**列表。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.SizeType>  
 [TableLayoutPanel 控件](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
