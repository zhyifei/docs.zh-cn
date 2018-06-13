---
title: 如何：将快捷菜单附加到 TreeView 节点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: 737e74184b0763ed84b4e585f2508d69944d0e77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528215"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>如何：将快捷菜单附加到 TreeView 节点
Windows 窗体<xref:System.Windows.Forms.TreeView>控件显示节点，类似于文件和文件夹在 Windows 资源管理器的左窗格中显示的层次结构。 通过设置<xref:System.Windows.Forms.Control.ContextMenuStrip%2A>属性，你可以提供区分上下文的操作向用户时用户右击<xref:System.Windows.Forms.TreeView>控件。 通过将相关联<xref:System.Windows.Forms.ContextMenuStrip>组件与单个<xref:System.Windows.Forms.TreeNode>项，可以添加到快捷菜单功能的自定义的级别你<xref:System.Windows.Forms.TreeView>控件。  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>要以编程方式与树节点关联的快捷菜单  
  
1.  实例化<xref:System.Windows.Forms.TreeView>控件替换为相应的属性设置，创建一个根<xref:System.Windows.Forms.TreeNode>，并将子节点。  
  
2.  实例化<xref:System.Windows.Forms.ContextMenuStrip>组件，然后添加<xref:System.Windows.Forms.ToolStripMenuItem>为你想要在运行时提供每个操作。  
  
3.  设置<xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A>与相应的属性<xref:System.Windows.Forms.TreeNode>到你创建的快捷菜单。  
  
4.  当设置此属性时，右键单击节点时，将显示的快捷菜单。  
  
 下面的代码示例创建一个基本<xref:System.Windows.Forms.TreeView>和<xref:System.Windows.Forms.ContextMenuStrip>与的根关联<xref:System.Windows.Forms.TreeNode>的<xref:System.Windows.Forms.TreeView>。 你将需要自定义为适合的菜单选项<xref:System.Windows.Forms.TreeView>你正在开发。 此外，你将想要编写代码来处理<xref:System.Windows.Forms.ToolStripItem.Click>这些菜单项的事件。  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [TreeView 控件](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
