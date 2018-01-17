---
title: "演练：使用设计器创建带有 ListView 和 TreeView 控件的资源管理器样式的界面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 200c5bbb5a162c1e585fc35f9c8cb3f63eb0368e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>演练：使用设计器创建带有 ListView 和 TreeView 控件的资源管理器样式的界面
Visual Studio 的优点之一是能够在短时间内创建具有专业水准的 Windows 窗体应用程序。 一种常见方案使用创建用户界面 (UI)<xref:System.Windows.Forms.ListView>和<xref:System.Windows.Forms.TreeView>类似于 Windows 操作系统的 Windows 资源管理器功能的控件。 Windows 资源管理器显示的层次结构的文件和文件夹的用户的计算机上。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>若要创建包含 ListView 和 TreeView 控件的窗体  
  
1.  在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。  
  
2.  在**新项目**对话框框中，执行以下操作：  
  
    1.  在类别选择**Visual Basic**或**Visual C#**。  
  
    2.  在模板列表中，选择**Windows 窗体应用程序**。  
  
3.  单击 **“确定”**。 创建新的 Windows 窗体项目。  
  
4.  添加<xref:System.Windows.Forms.SplitContainer>到窗体控件，并设置其<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>。  
  
5.  添加<xref:System.Windows.Forms.ImageList>名为`imageList1`到窗体，然后使用属性窗口添加两个映像： 一个文件夹图像和文档的图像，按此顺序。  
  
6.  添加<xref:System.Windows.Forms.TreeView>控件名为`treeview1`到窗体，并将其放在左侧的<xref:System.Windows.Forms.SplitContainer>控件。 中的属性窗口`treeView1`执行以下操作：  
  
    1.  将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。  
  
    2.  将 <xref:System.Windows.Forms.TreeView.ImageList%2A> 属性设置为 `imagelist1.`  
  
7.  添加<xref:System.Windows.Forms.ListView>控件名为`listView1`到窗体，并将其放在右侧<xref:System.Windows.Forms.SplitContainer>控件。 中的属性窗口`listview1`执行以下操作：  
  
    1.  将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。  
  
    2.  将 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Details>。  
  
    3.  打开 ColumnHeader 集合编辑器中，单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 中<xref:System.Windows.Forms.ListView.Columns%2A>属性**。** 添加三个列，并设置其<xref:System.Windows.Forms.ColumnHeader.Text%2A>属性`Name`， `Type`，和`Last Modified`分别。 单击“确定”关闭对话框。  
  
    4.  将 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 属性设置为 `imageList1.`  
  
8.  实现代码以填充<xref:System.Windows.Forms.TreeView>节点和子节点。 添加此代码与`Form1`类。  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. 由于前面的代码使用 System.IO 命名空间，添加适当的使用或导入窗体顶部的语句。  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. 从窗体的构造函数的上一步调用设置方法或<xref:System.Windows.Forms.Form.Load>事件处理方法。 将此代码添加到窗体构造函数。  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. 处理<xref:System.Windows.Forms.TreeView.NodeMouseClick>事件`treeview1` **，**和实现代码以填充`listview1`时单击节点的节点的内容。 添加此代码与`Form1`类。  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     如果你使用的 C#，请确保你具有<xref:System.Windows.Forms.TreeView.NodeMouseClick>事件与其事件处理方法关联。 将此代码添加到窗体构造函数。  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a>测试应用程序  
 你现在可以测试窗体，以确保其行为与预期相同。  
  
#### <a name="to-test-the-form"></a>若要测试窗体  
  
-   按 F5 运行该应用程序。  
  
     你将看到一个拆分窗体包含<xref:System.Windows.Forms.TreeView>左侧，显示你的项目目录的控件和<xref:System.Windows.Forms.ListView>具有三列右侧的控件。 你可以遍历<xref:System.Windows.Forms.TreeView>通过选择目录节点和<xref:System.Windows.Forms.ListView>填充所选目录的内容。  
  
## <a name="next-steps"></a>后续步骤  
 此应用程序使你可以使用一种方法的示例<xref:System.Windows.Forms.TreeView>和<xref:System.Windows.Forms.ListView>控制在一起。 有关这些控件的详细信息，请参阅以下主题：  
  
-   [如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [如何：向 ListView 控件添加搜索功能](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [如何：将快捷菜单附加到 TreeView 节点](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.TreeView>  
 [ListView 控件](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [如何：使用 Windows 窗体 TreeView 控件添加和删除节点](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [如何：使用 Windows 窗体 ListView 控件添加和删除项](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [如何：向 Windows 窗体 ListView 控件添加列](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
