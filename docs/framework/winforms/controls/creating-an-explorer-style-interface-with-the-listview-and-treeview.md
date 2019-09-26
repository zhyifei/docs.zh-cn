---
title: 演练：使用设计器创建带有 ListView 和 TreeView 控件的资源管理器样式界面
ms.date: 03/30/2017
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
ms.openlocfilehash: d80f8e3bc729689b274af520bc37fda8417b0407
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "69658574"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>演练：使用设计器创建带有 ListView 和 TreeView 控件的资源管理器样式界面

Visual Studio 的一个优点是，可以在短时间内创建专业外观的 Windows 窗体应用程序。 常见的方案是创建具有<xref:System.Windows.Forms.ListView>和<xref:System.Windows.Forms.TreeView>控件的用户界面（UI），这类似于 windows 操作系统的 windows 资源管理器功能。 Windows 资源管理器显示用户计算机上的文件和文件夹的层次结构。

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>创建包含 ListView 和 TreeView 控件的窗体

1. 在 **“文件”** 菜单上，指向 **“新建”** ，然后单击 **“项目”** 。

2. 在 "**新建项目**" 对话框中, 执行以下操作:

    1. 在 "类别" 中，选择 " **Visual Basic** " 或 "**视觉对象C#** "。

    2. 在模板列表中，选择 " **Windows 窗体应用程序**"。

3. 单击 **“确定”** 。 这将创建一个新的 Windows 窗体项目。

4. 向窗<xref:System.Windows.Forms.SplitContainer>体添加一个控件，并将<xref:System.Windows.Forms.SplitContainer.Dock%2A>其属性<xref:System.Windows.Forms.DockStyle.Fill>设置为。

5. 向窗<xref:System.Windows.Forms.ImageList>体`imageList1`添加一个名为的，并使用属性窗口按顺序添加两个图像：文件夹图像和文档图像。

6. 向窗<xref:System.Windows.Forms.TreeView>体添加`treeview1`一个名为的控件，并将其定位在<xref:System.Windows.Forms.SplitContainer>控件的左侧。 在属性窗口`treeView1`中，执行以下操作：

    1. 将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。

    2. 将 <xref:System.Windows.Forms.TreeView.ImageList%2A> 属性设置为 `imagelist1.`

7. 向窗<xref:System.Windows.Forms.ListView>体添加`listView1`一个名为的控件，并将其定位在<xref:System.Windows.Forms.SplitContainer>控件的右侧。 在属性窗口`listview1`中，执行以下操作：

    1. 将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。

    2. 将 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Details>。

    3. ![通过**单击**](./media/visual-studio-ellipsis-button.png)属性中的 "Visual Studio 属性窗口中的省略号按钮（...）来打开" ColumnHeader 集合编辑器 "。 <xref:System.Windows.Forms.ListView.Columns%2A> 添加三列，并分别<xref:System.Windows.Forms.ColumnHeader.Text%2A>将其`Name`属性`Type`设置为`Last Modified`、和。 单击“确定”关闭对话框。

    4. 将 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 属性设置为 `imageList1.`

8. 实现代码以<xref:System.Windows.Forms.TreeView>用节点和子节点填充。 将此代码添加到`Form1`类。

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. 由于前面的代码使用 System.IO 命名空间，因此请在窗体顶部添加适当的 using 或 import 语句。

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. 在窗体的构造函数或<xref:System.Windows.Forms.Form.Load>事件处理方法中，调用上一步中的设置方法。 将此代码添加到窗体构造函数中。

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. `listview1`处理的<xref:System.Windows.Forms.TreeView.NodeMouseClick> `treeview1`事件 **，** 并在单击节点时实现代码以填充节点的内容。 将此代码添加到`Form1`类。

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     如果使用C#的是，请确保<xref:System.Windows.Forms.TreeView.NodeMouseClick>事件与其事件处理方法关联。 将此代码添加到窗体构造函数中。

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a>测试应用程序

你现在可以对窗体进行测试，以确保它按预期方式运行。

#### <a name="to-test-the-form"></a>测试窗体

- 按 F5 运行该应用程序。

     你将看到一个拆分窗体， <xref:System.Windows.Forms.TreeView>该窗体包含一个控件，该控件在左侧显示你<xref:System.Windows.Forms.ListView>的项目目录，在右侧显示一个具有三列的控件。 您可以<xref:System.Windows.Forms.TreeView>通过选择目录节点遍历， <xref:System.Windows.Forms.ListView>并使用所选目录的内容进行填充。

## <a name="next-steps"></a>后续步骤

此应用程序提供了一种使用<xref:System.Windows.Forms.TreeView>和<xref:System.Windows.Forms.ListView>控制的方式的示例。 有关这些控件的详细信息，请参阅以下主题：

- [如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [如何：向 ListView 控件添加搜索功能](how-to-add-search-capabilities-to-a-listview-control.md)

- [如何：将快捷菜单附加到 TreeView 节点](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [ListView 控件](listview-control-windows-forms.md)
- [如何：在 Windows 窗体 TreeView 控件中添加和删除节点](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [如何：通过 Windows 窗体 ListView 控件添加和移除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [如何：向 Windows 窗体 ListView 控件添加列](how-to-add-columns-to-the-windows-forms-listview-control.md)
