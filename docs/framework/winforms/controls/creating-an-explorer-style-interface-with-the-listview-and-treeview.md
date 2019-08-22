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
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658574"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="f8822-102">演练：使用设计器创建带有 ListView 和 TreeView 控件的资源管理器样式界面</span><span class="sxs-lookup"><span data-stu-id="f8822-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="f8822-103">Visual Studio 的一个优点是, 可以在短时间内创建专业外观的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="f8822-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="f8822-104">常见的方案是创建具有<xref:System.Windows.Forms.ListView>和<xref:System.Windows.Forms.TreeView>控件的用户界面 (UI), 这类似于 windows 操作系统的 windows 资源管理器功能。</span><span class="sxs-lookup"><span data-stu-id="f8822-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="f8822-105">Windows 资源管理器显示用户计算机上的文件和文件夹的层次结构。</span><span class="sxs-lookup"><span data-stu-id="f8822-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="f8822-106">创建包含 ListView 和 TreeView 控件的窗体</span><span class="sxs-lookup"><span data-stu-id="f8822-106">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="f8822-107">在 **“文件”** 菜单上，指向 **“新建”** ，然后单击 **“项目”** 。</span><span class="sxs-lookup"><span data-stu-id="f8822-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="f8822-108">在 "**新建项目**" 对话框中, 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f8822-108">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="f8822-109">在 "类别" 中, 选择 " **Visual Basic** " 或 "**视觉对象C#** "。</span><span class="sxs-lookup"><span data-stu-id="f8822-109">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="f8822-110">在模板列表中, 选择 " **Windows 窗体应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="f8822-110">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="f8822-111">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="f8822-111">Click **OK**.</span></span> <span data-ttu-id="f8822-112">这将创建一个新的 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="f8822-112">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="f8822-113">向窗<xref:System.Windows.Forms.SplitContainer>体添加一个控件, 并将<xref:System.Windows.Forms.SplitContainer.Dock%2A>其属性<xref:System.Windows.Forms.DockStyle.Fill>设置为。</span><span class="sxs-lookup"><span data-stu-id="f8822-113">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="f8822-114">向窗<xref:System.Windows.Forms.ImageList>体`imageList1`添加一个名为的, 并使用属性窗口按顺序添加两个图像: 文件夹图像和文档图像。</span><span class="sxs-lookup"><span data-stu-id="f8822-114">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="f8822-115">向窗<xref:System.Windows.Forms.TreeView>体添加`treeview1`一个名为的控件, 并将其定位在<xref:System.Windows.Forms.SplitContainer>控件的左侧。</span><span class="sxs-lookup"><span data-stu-id="f8822-115">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="f8822-116">在属性窗口`treeView1`中, 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f8822-116">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="f8822-117">将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="f8822-117">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="f8822-118">将 <xref:System.Windows.Forms.TreeView.ImageList%2A> 属性设置为 `imagelist1.`</span><span class="sxs-lookup"><span data-stu-id="f8822-118">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="f8822-119">向窗<xref:System.Windows.Forms.ListView>体添加`listView1`一个名为的控件, 并将其定位在<xref:System.Windows.Forms.SplitContainer>控件的右侧。</span><span class="sxs-lookup"><span data-stu-id="f8822-119">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="f8822-120">在属性窗口`listview1`中, 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f8822-120">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="f8822-121">将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="f8822-121">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="f8822-122">将 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Details>。</span><span class="sxs-lookup"><span data-stu-id="f8822-122">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="f8822-123">通过![单击<xref:System.Windows.Forms.ListView.Columns%2A>属性中的 "Visual](./media/visual-studio-ellipsis-button.png)Studio 属性窗口中的省略号按钮 (...) 来打开" ColumnHeader 集合编辑器 "。</span><span class="sxs-lookup"><span data-stu-id="f8822-123">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="f8822-124">添加三列, 并分别<xref:System.Windows.Forms.ColumnHeader.Text%2A>将其`Name`属性`Type`设置为`Last Modified`、和。</span><span class="sxs-lookup"><span data-stu-id="f8822-124">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="f8822-125">单击“确定”关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="f8822-125">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="f8822-126">将 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 属性设置为 `imageList1.`</span><span class="sxs-lookup"><span data-stu-id="f8822-126">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="f8822-127">实现代码以<xref:System.Windows.Forms.TreeView>用节点和子节点填充。</span><span class="sxs-lookup"><span data-stu-id="f8822-127">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="f8822-128">将此代码添加到`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="f8822-128">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="f8822-129">由于前面的代码使用 System.IO 命名空间, 因此请在窗体顶部添加适当的 using 或 import 语句。</span><span class="sxs-lookup"><span data-stu-id="f8822-129">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="f8822-130">在窗体的构造函数或<xref:System.Windows.Forms.Form.Load>事件处理方法中, 调用上一步中的设置方法。</span><span class="sxs-lookup"><span data-stu-id="f8822-130">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="f8822-131">将此代码添加到窗体构造函数中。</span><span class="sxs-lookup"><span data-stu-id="f8822-131">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="f8822-132">`listview1`处理的<xref:System.Windows.Forms.TreeView.NodeMouseClick> `treeview1`事件 **,** 并在单击节点时实现代码以填充节点的内容。</span><span class="sxs-lookup"><span data-stu-id="f8822-132">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="f8822-133">将此代码添加到`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="f8822-133">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="f8822-134">如果使用C#的是, 请确保<xref:System.Windows.Forms.TreeView.NodeMouseClick>事件与其事件处理方法关联。</span><span class="sxs-lookup"><span data-stu-id="f8822-134">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="f8822-135">将此代码添加到窗体构造函数中。</span><span class="sxs-lookup"><span data-stu-id="f8822-135">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="f8822-136">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="f8822-136">Testing the Application</span></span>

<span data-ttu-id="f8822-137">你现在可以对窗体进行测试, 以确保它按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="f8822-137">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="f8822-138">测试窗体</span><span class="sxs-lookup"><span data-stu-id="f8822-138">To test the form</span></span>

- <span data-ttu-id="f8822-139">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="f8822-139">Press F5 to run the application.</span></span>

     <span data-ttu-id="f8822-140">你将看到一个拆分窗体, <xref:System.Windows.Forms.TreeView>该窗体包含一个控件, 该控件在左侧显示你<xref:System.Windows.Forms.ListView>的项目目录, 在右侧显示一个具有三列的控件。</span><span class="sxs-lookup"><span data-stu-id="f8822-140">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="f8822-141">您可以<xref:System.Windows.Forms.TreeView>通过选择目录节点遍历, <xref:System.Windows.Forms.ListView>并使用所选目录的内容进行填充。</span><span class="sxs-lookup"><span data-stu-id="f8822-141">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8822-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f8822-142">Next Steps</span></span>

<span data-ttu-id="f8822-143">此应用程序提供了一种使用<xref:System.Windows.Forms.TreeView>和<xref:System.Windows.Forms.ListView>控制的方式的示例。</span><span class="sxs-lookup"><span data-stu-id="f8822-143">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="f8822-144">有关这些控件的详细信息, 请参阅以下主题:</span><span class="sxs-lookup"><span data-stu-id="f8822-144">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="f8822-145">如何：向 TreeView 或 ListView 控件添加自定义信息 (Windows 窗体)</span><span class="sxs-lookup"><span data-stu-id="f8822-145">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="f8822-146">如何：向 ListView 控件添加搜索功能</span><span class="sxs-lookup"><span data-stu-id="f8822-146">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="f8822-147">如何：将快捷菜单附加到 TreeView 节点</span><span class="sxs-lookup"><span data-stu-id="f8822-147">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="f8822-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8822-148">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="f8822-149">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="f8822-149">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="f8822-150">如何：在 Windows 窗体 TreeView 控件中添加和删除节点</span><span class="sxs-lookup"><span data-stu-id="f8822-150">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="f8822-151">如何：通过 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="f8822-151">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="f8822-152">如何：向 Windows 窗体 ListView 控件添加列</span><span class="sxs-lookup"><span data-stu-id="f8822-152">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
