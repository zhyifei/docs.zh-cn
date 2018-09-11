---
title: 演练：使用设计器创建带有 ListView 和 TreeView 控件的资源管理器样式的界面
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
ms.openlocfilehash: 73d3a0bef1ab075aee8e06f676ef17b853773552
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267211"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="e83a4-102">演练：使用设计器创建带有 ListView 和 TreeView 控件的资源管理器样式的界面</span><span class="sxs-lookup"><span data-stu-id="e83a4-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>
<span data-ttu-id="e83a4-103">Visual Studio 的优势之一是时间的能够在较短中创建具有专业外观的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="e83a4-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="e83a4-104">一种常见方案使用创建用户界面 (UI)<xref:System.Windows.Forms.ListView>和<xref:System.Windows.Forms.TreeView>类似于 Windows 操作系统的 Windows 资源管理器功能的控件。</span><span class="sxs-lookup"><span data-stu-id="e83a4-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="e83a4-105">Windows 资源管理器中显示用户的计算机上的文件和文件夹的层次结构。</span><span class="sxs-lookup"><span data-stu-id="e83a4-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e83a4-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="e83a4-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e83a4-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="e83a4-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e83a4-108">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="e83a4-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="e83a4-109">若要创建包含 ListView 和 TreeView 控件的窗体</span><span class="sxs-lookup"><span data-stu-id="e83a4-109">To create the form containing a ListView and TreeView control</span></span>  
  
1.  <span data-ttu-id="e83a4-110">在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="e83a4-110">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="e83a4-111">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e83a4-111">In the **New Project** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="e83a4-112">在类别中，选择**Visual Basic**或**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="e83a4-112">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>  
  
    2.  <span data-ttu-id="e83a4-113">在模板列表中，选择**Windows 窗体应用程序**。</span><span class="sxs-lookup"><span data-stu-id="e83a4-113">In the list of templates, choose **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="e83a4-114">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e83a4-114">Click **OK**.</span></span> <span data-ttu-id="e83a4-115">创建一个新的 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="e83a4-115">A new Windows Forms project is created.</span></span>  
  
4.  <span data-ttu-id="e83a4-116">添加<xref:System.Windows.Forms.SplitContainer>向窗体控件，并设置其<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="e83a4-116">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="e83a4-117">添加<xref:System.Windows.Forms.ImageList>名为`imageList1`到窗体，使用属性窗口添加两个映像： 一个文件夹图像和文档图像，按该顺序。</span><span class="sxs-lookup"><span data-stu-id="e83a4-117">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>  
  
6.  <span data-ttu-id="e83a4-118">添加<xref:System.Windows.Forms.TreeView>名为控件`treeview1`窗体，并将其置于的左侧<xref:System.Windows.Forms.SplitContainer>控件。</span><span class="sxs-lookup"><span data-stu-id="e83a4-118">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="e83a4-119">在属性窗口中`treeView1`执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e83a4-119">In the Properties window for `treeView1` do the following:</span></span>  
  
    1.  <span data-ttu-id="e83a4-120">将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="e83a4-120">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2.  <span data-ttu-id="e83a4-121">将 <xref:System.Windows.Forms.TreeView.ImageList%2A> 属性设置为 `imagelist1.`</span><span class="sxs-lookup"><span data-stu-id="e83a4-121">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>  
  
7.  <span data-ttu-id="e83a4-122">添加<xref:System.Windows.Forms.ListView>名为控件`listView1`窗体，并将其置于的右侧<xref:System.Windows.Forms.SplitContainer>控件。</span><span class="sxs-lookup"><span data-stu-id="e83a4-122">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="e83a4-123">在属性窗口中`listview1`执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e83a4-123">In the Properties window for `listview1` do the following:</span></span>  
  
    1.  <span data-ttu-id="e83a4-124">将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="e83a4-124">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2.  <span data-ttu-id="e83a4-125">将 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Details>。</span><span class="sxs-lookup"><span data-stu-id="e83a4-125">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
    3.  <span data-ttu-id="e83a4-126">通过单击省略号打开 ColumnHeader 集合编辑器 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 中<xref:System.Windows.Forms.ListView.Columns%2A>属性 **。**</span><span class="sxs-lookup"><span data-stu-id="e83a4-126">Open the ColumnHeader Collection Editor by clicking the ellipses (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="e83a4-127">添加三个列，并设置其<xref:System.Windows.Forms.ColumnHeader.Text%2A>属性设置为`Name`， `Type`，和`Last Modified`分别。</span><span class="sxs-lookup"><span data-stu-id="e83a4-127">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="e83a4-128">单击“确定”关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="e83a4-128">Click **OK** to close the dialog box.</span></span>  
  
    4.  <span data-ttu-id="e83a4-129">将 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 属性设置为 `imageList1.`</span><span class="sxs-lookup"><span data-stu-id="e83a4-129">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>  
  
8.  <span data-ttu-id="e83a4-130">实现代码来填充<xref:System.Windows.Forms.TreeView>节点和子节点。</span><span class="sxs-lookup"><span data-stu-id="e83a4-130">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="e83a4-131">添加到此代码`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="e83a4-131">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. <span data-ttu-id="e83a4-132">由于前面的代码使用 System.IO 命名空间，添加相应的使用或导入窗体顶部的语句。</span><span class="sxs-lookup"><span data-stu-id="e83a4-132">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="e83a4-133">从上一步中窗体的构造函数调用设置方法或<xref:System.Windows.Forms.Form.Load>事件处理方法。</span><span class="sxs-lookup"><span data-stu-id="e83a4-133">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="e83a4-134">将此代码添加到窗体构造函数。</span><span class="sxs-lookup"><span data-stu-id="e83a4-134">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. <span data-ttu-id="e83a4-135">处理<xref:System.Windows.Forms.TreeView.NodeMouseClick>事件`treeview1` **，** 并实现代码来填充`listview1`单击节点时的节点的内容。</span><span class="sxs-lookup"><span data-stu-id="e83a4-135">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="e83a4-136">添加到此代码`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="e83a4-136">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     <span data-ttu-id="e83a4-137">如果使用的 C#，请确保你有<xref:System.Windows.Forms.TreeView.NodeMouseClick>事件与其事件处理方法关联。</span><span class="sxs-lookup"><span data-stu-id="e83a4-137">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="e83a4-138">将此代码添加到窗体构造函数。</span><span class="sxs-lookup"><span data-stu-id="e83a4-138">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="e83a4-139">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="e83a4-139">Testing the Application</span></span>  
 <span data-ttu-id="e83a4-140">现在可以测试窗体，以确保其行为符合预期。</span><span class="sxs-lookup"><span data-stu-id="e83a4-140">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="e83a4-141">若要测试窗体</span><span class="sxs-lookup"><span data-stu-id="e83a4-141">To test the form</span></span>  
  
-   <span data-ttu-id="e83a4-142">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e83a4-142">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="e83a4-143">你将看到一个拆分窗体，其中包含<xref:System.Windows.Forms.TreeView>控件，用于左侧和右侧，显示你的项目目录和一个<xref:System.Windows.Forms.ListView>包含三列右侧的控件。</span><span class="sxs-lookup"><span data-stu-id="e83a4-143">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="e83a4-144">您可以遍历<xref:System.Windows.Forms.TreeView>通过选择目录节点和<xref:System.Windows.Forms.ListView>填充与所选目录的内容。</span><span class="sxs-lookup"><span data-stu-id="e83a4-144">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e83a4-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e83a4-145">Next Steps</span></span>  
 <span data-ttu-id="e83a4-146">此应用程序提供的一种方法可以使用示例<xref:System.Windows.Forms.TreeView>和<xref:System.Windows.Forms.ListView>一起控制。</span><span class="sxs-lookup"><span data-stu-id="e83a4-146">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="e83a4-147">有关这些控件的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="e83a4-147">For more information on these controls, see the following topics:</span></span>  
  
-   [<span data-ttu-id="e83a4-148">如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息</span><span class="sxs-lookup"><span data-stu-id="e83a4-148">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [<span data-ttu-id="e83a4-149">如何：向 ListView 控件添加搜索功能</span><span class="sxs-lookup"><span data-stu-id="e83a4-149">How to: Add Search Capabilities to a ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [<span data-ttu-id="e83a4-150">如何：将快捷菜单附加到 TreeView 节点</span><span class="sxs-lookup"><span data-stu-id="e83a4-150">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a><span data-ttu-id="e83a4-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="e83a4-151">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.TreeView>  
 [<span data-ttu-id="e83a4-152">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="e83a4-152">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="e83a4-153">如何：使用 Windows 窗体 TreeView 控件添加和删除节点</span><span class="sxs-lookup"><span data-stu-id="e83a4-153">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="e83a4-154">如何：使用 Windows 窗体 ListView 控件添加和删除项</span><span class="sxs-lookup"><span data-stu-id="e83a4-154">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="e83a4-155">如何：向 Windows 窗体 ListView 控件添加列</span><span class="sxs-lookup"><span data-stu-id="e83a4-155">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
