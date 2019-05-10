---
title: 演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211563"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="f045e-102">演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体</span><span class="sxs-lookup"><span data-stu-id="f045e-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="f045e-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。</span><span class="sxs-lookup"><span data-stu-id="f045e-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="f045e-104">MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="f045e-105">本演练演示如何使用<xref:System.Windows.Forms.ToolStripPanel>具有的 MDI 窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="f045e-106">此窗体还支持菜单与子菜单合并。</span><span class="sxs-lookup"><span data-stu-id="f045e-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="f045e-107">在本演练阐释了以下任务：</span><span class="sxs-lookup"><span data-stu-id="f045e-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="f045e-108">创建一个 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="f045e-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="f045e-109">正在创建你的窗体的主菜单。</span><span class="sxs-lookup"><span data-stu-id="f045e-109">Creating the main menu for your form.</span></span> <span data-ttu-id="f045e-110">在菜单的实际名称将有所不同。</span><span class="sxs-lookup"><span data-stu-id="f045e-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="f045e-111">添加<xref:System.Windows.Forms.ToolStripPanel>控制对**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="f045e-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="f045e-112">创建子窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-112">Creating a child form.</span></span>

- <span data-ttu-id="f045e-113">排列<xref:System.Windows.Forms.ToolStripPanel>按 z 顺序的控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="f045e-114">完成，你将拥有支持菜单合并功能和可移动的 MDI 窗体<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="f045e-115">要将本主题中的代码作为单个列表进行复制，请参阅[如何：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="f045e-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f045e-116">系统必备</span><span class="sxs-lookup"><span data-stu-id="f045e-116">Prerequisites</span></span>

<span data-ttu-id="f045e-117">你将需要 Visual Studio 来完成本演练。</span><span class="sxs-lookup"><span data-stu-id="f045e-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f045e-118">创建项目</span><span class="sxs-lookup"><span data-stu-id="f045e-118">Create the project</span></span>

1. <span data-ttu-id="f045e-119">在 Visual Studio 中，创建一个名为 Windows 应用程序项目**mdi 窗体**(**文件** > **新建** > **项目**  >  **Visual C#** 或**Visual Basic** > **经典桌面** >  **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="f045e-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="f045e-120">在 Windows 窗体设计器中，选择窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="f045e-121">在属性窗口中设置的值<xref:System.Windows.Forms.Form.IsMdiContainer%2A>到`true`。</span><span class="sxs-lookup"><span data-stu-id="f045e-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="f045e-122">创建主菜单</span><span class="sxs-lookup"><span data-stu-id="f045e-122">Create the main menu</span></span>

<span data-ttu-id="f045e-123">MDI 父窗体包含主菜单。</span><span class="sxs-lookup"><span data-stu-id="f045e-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="f045e-124">主菜单有一个名为菜单项**窗口**。</span><span class="sxs-lookup"><span data-stu-id="f045e-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="f045e-125">与**窗口**菜单项，可以创建子窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="f045e-126">从子窗体的菜单项合并到主菜单中。</span><span class="sxs-lookup"><span data-stu-id="f045e-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="f045e-127">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="f045e-128">添加<xref:System.Windows.Forms.ToolStripMenuItem>到<xref:System.Windows.Forms.MenuStrip>控制并将其命名**窗口**。</span><span class="sxs-lookup"><span data-stu-id="f045e-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="f045e-129">选择 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="f045e-130">在属性窗口中设置的值<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>属性设置为`ToolStripMenuItem1`。</span><span class="sxs-lookup"><span data-stu-id="f045e-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="f045e-131">添加到子项**窗口**菜单项，并将其命名**新建**。</span><span class="sxs-lookup"><span data-stu-id="f045e-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="f045e-132">在属性窗口中，单击**事件**。</span><span class="sxs-lookup"><span data-stu-id="f045e-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="f045e-133">双击<xref:System.Windows.Forms.ToolStripItem.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="f045e-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="f045e-134">Windows 窗体设计器生成的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="f045e-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="f045e-135">以下代码插入到的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f045e-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="f045e-136">向工具箱添加 ToolStripPanel 控件</span><span class="sxs-lookup"><span data-stu-id="f045e-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="f045e-137">当你使用<xref:System.Windows.Forms.MenuStrip>必须具有的 MDI 窗体控件<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="f045e-138">必须添加<xref:System.Windows.Forms.ToolStripPanel>控制对**工具箱**来生成你在 Windows 窗体设计器中的 MDI 窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="f045e-139">打开**工具箱**，然后单击**所有 Windows 窗体**选项卡以显示可用的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="f045e-140">若要打开快捷菜单中，右键单击并选择**选择项**。</span><span class="sxs-lookup"><span data-stu-id="f045e-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="f045e-141">在中**选择工具箱项**对话框中，向下滚动**名称**列，直到找到**ToolStripPanel**。</span><span class="sxs-lookup"><span data-stu-id="f045e-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="f045e-142">选中的复选框**ToolStripPanel**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f045e-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="f045e-143"><xref:System.Windows.Forms.ToolStripPanel>控件会出现在**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="f045e-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="f045e-144">创建子窗体</span><span class="sxs-lookup"><span data-stu-id="f045e-144">Create a child form</span></span>

<span data-ttu-id="f045e-145">在此过程中，您将定义具有其自己的单独的子窗体类<xref:System.Windows.Forms.MenuStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="f045e-146">此窗体的菜单项将与父窗体的合并。</span><span class="sxs-lookup"><span data-stu-id="f045e-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="f045e-147">添加名为一个新窗体`ChildForm`到项目。</span><span class="sxs-lookup"><span data-stu-id="f045e-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="f045e-148">有关详细信息，请参阅[如何：向项目添加 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="f045e-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="f045e-149">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>到子窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="f045e-150">单击<xref:System.Windows.Forms.MenuStrip>控件的智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))，然后选择**编辑项**。</span><span class="sxs-lookup"><span data-stu-id="f045e-150">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="f045e-151">在中**项集合编辑器**对话框框中，添加一个新<xref:System.Windows.Forms.ToolStripMenuItem>名为**ChildMenuItem**到子菜单。</span><span class="sxs-lookup"><span data-stu-id="f045e-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="f045e-152">有关详细信息，请参阅[ToolStrip 项集合编辑器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="f045e-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="f045e-153">测试窗体</span><span class="sxs-lookup"><span data-stu-id="f045e-153">Test the form</span></span>

1. <span data-ttu-id="f045e-154">按**F5**编译并运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="f045e-155">单击**窗口**菜单项以打开菜单，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="f045e-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="f045e-156">窗体的 MDI 客户端区域中创建新的子窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="f045e-157">与主菜单合并子窗体的菜单。</span><span class="sxs-lookup"><span data-stu-id="f045e-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="f045e-158">关闭子窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-158">Close the child form.</span></span>

     <span data-ttu-id="f045e-159">从主菜单中删除子窗体的菜单。</span><span class="sxs-lookup"><span data-stu-id="f045e-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="f045e-160">单击**新建**几次。</span><span class="sxs-lookup"><span data-stu-id="f045e-160">Click **New** several times.</span></span>

     <span data-ttu-id="f045e-161">子窗体自动列入**窗口**菜单项，因为<xref:System.Windows.Forms.MenuStrip>控件的<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>分配属性。</span><span class="sxs-lookup"><span data-stu-id="f045e-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="f045e-162">添加 ToolStrip 的支持</span><span class="sxs-lookup"><span data-stu-id="f045e-162">Add ToolStrip support</span></span>

<span data-ttu-id="f045e-163">在此过程中，您将添加四个<xref:System.Windows.Forms.ToolStrip>到 MDI 父窗体控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="f045e-164">每个<xref:System.Windows.Forms.ToolStrip>控件添加内部<xref:System.Windows.Forms.ToolStripPanel>控件停靠到窗体的边缘。</span><span class="sxs-lookup"><span data-stu-id="f045e-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="f045e-165">从**工具箱**，拖动<xref:System.Windows.Forms.ToolStripPanel>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="f045e-166">与<xref:System.Windows.Forms.ToolStripPanel>控件处于选中状态，双击<xref:System.Windows.Forms.ToolStrip>控制**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="f045e-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="f045e-167">一个<xref:System.Windows.Forms.ToolStrip>控件中创建<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="f045e-168">选择 <xref:System.Windows.Forms.ToolStripPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="f045e-169">在属性窗口更改控件的值<xref:System.Windows.Forms.Control.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.Left>。</span><span class="sxs-lookup"><span data-stu-id="f045e-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="f045e-170"><xref:System.Windows.Forms.ToolStripPanel>控件停靠到窗体中，主菜单下的左侧。</span><span class="sxs-lookup"><span data-stu-id="f045e-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="f045e-171">在 MDI 工作区调整大小以适合<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="f045e-172">重复步骤 1 至 4。</span><span class="sxs-lookup"><span data-stu-id="f045e-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="f045e-173">停靠新<xref:System.Windows.Forms.ToolStripPanel>到窗体顶部的控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="f045e-174"><xref:System.Windows.Forms.ToolStripPanel>控件下方主菜单中，但第一个右侧停靠<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="f045e-175">本步骤说明了在正确定位的 z 顺序的重要性<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="f045e-176">对两个重复步骤 1 到 4<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="f045e-177">停靠新<xref:System.Windows.Forms.ToolStripPanel>向右侧和底部的窗体控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="f045e-178">排列按 Z 顺序的 ToolStripPanel 控件</span><span class="sxs-lookup"><span data-stu-id="f045e-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="f045e-179">停靠的位置<xref:System.Windows.Forms.ToolStripPanel>MDI 窗体上的控件由 z 顺序中的控件的位置。</span><span class="sxs-lookup"><span data-stu-id="f045e-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="f045e-180">您可以轻松地排列在文档大纲窗口中控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="f045e-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="f045e-181">在中**视图**菜单上，单击**其他 Windows**，然后单击**文档大纲**。</span><span class="sxs-lookup"><span data-stu-id="f045e-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="f045e-182">排列方式在<xref:System.Windows.Forms.ToolStripPanel>控件从前面的过程是使用了非标准。</span><span class="sxs-lookup"><span data-stu-id="f045e-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="f045e-183">这是因为 z 顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="f045e-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="f045e-184">使用文档大纲窗口更改控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="f045e-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="f045e-185">在文档大纲窗口中，选择**ToolStripPanel4**。</span><span class="sxs-lookup"><span data-stu-id="f045e-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="f045e-186">单击向下箭头按钮重复，直到**ToolStripPanel4**位于列表的底部。</span><span class="sxs-lookup"><span data-stu-id="f045e-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="f045e-187">**ToolStripPanel4**控件停靠到窗体中，在其他控件下的底部。</span><span class="sxs-lookup"><span data-stu-id="f045e-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="f045e-188">选择**ToolStripPanel2**。</span><span class="sxs-lookup"><span data-stu-id="f045e-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="f045e-189">一次单击向下箭头按钮以在列表中第三个放置控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="f045e-190">**ToolStripPanel2**控件停靠到窗体，下面的主菜单和高于其他控件的顶部。</span><span class="sxs-lookup"><span data-stu-id="f045e-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="f045e-191">选择中的各个控件**文档大纲**窗口并将它们移动到不同的 z 顺序中的位置。</span><span class="sxs-lookup"><span data-stu-id="f045e-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="f045e-192">请注意对停靠控件的位置的 z 顺序的影响。</span><span class="sxs-lookup"><span data-stu-id="f045e-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="f045e-193">使用 CTRL-Z 或**撤消**上**编辑**菜单上，若要撤消所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f045e-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="f045e-194">检查点-测试你的窗体</span><span class="sxs-lookup"><span data-stu-id="f045e-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="f045e-195">按**F5**编译并运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="f045e-196">单击的手柄<xref:System.Windows.Forms.ToolStrip>控件，窗体上将控件拖到不同的位置。</span><span class="sxs-lookup"><span data-stu-id="f045e-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="f045e-197">可以拖动<xref:System.Windows.Forms.ToolStrip>控件从一个<xref:System.Windows.Forms.ToolStripPanel>到另一个控件。</span><span class="sxs-lookup"><span data-stu-id="f045e-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f045e-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f045e-198">Next steps</span></span>

<span data-ttu-id="f045e-199">在本演练中，您创建了一个 MDI 父窗体<xref:System.Windows.Forms.ToolStrip>控件和菜单合并。</span><span class="sxs-lookup"><span data-stu-id="f045e-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="f045e-200">可以使用<xref:System.Windows.Forms.ToolStrip>实现多种其他用途的控件的系列：</span><span class="sxs-lookup"><span data-stu-id="f045e-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="f045e-201">创建与控件的快捷菜单<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="f045e-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="f045e-202">有关详细信息，请参阅[ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="f045e-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="f045e-203">创建一个自动填充的标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="f045e-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="f045e-204">有关详细信息，请参见[演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="f045e-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="f045e-205">提供你<xref:System.Windows.Forms.ToolStrip>控件专业的外观。</span><span class="sxs-lookup"><span data-stu-id="f045e-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="f045e-206">有关详细信息，请参阅[如何：设置 ToolStrip 呈现程序](how-to-set-the-toolstrip-renderer-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f045e-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f045e-207">请参阅</span><span class="sxs-lookup"><span data-stu-id="f045e-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="f045e-208">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="f045e-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="f045e-209">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="f045e-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="f045e-210">如何：将 MenuStrip 插入 MDI 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="f045e-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="f045e-211">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="f045e-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
