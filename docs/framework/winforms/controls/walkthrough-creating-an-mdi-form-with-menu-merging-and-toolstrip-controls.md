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
ms.openlocfilehash: d5fa1ebcc044a18e21e57aa2f66bd8486369fe42
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "43255688"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="79b65-102">演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体</span><span class="sxs-lookup"><span data-stu-id="79b65-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="79b65-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。</span><span class="sxs-lookup"><span data-stu-id="79b65-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="79b65-104">MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="79b65-105">本演练演示如何使用<xref:System.Windows.Forms.ToolStripPanel>具有的 MDI 窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="79b65-106">此窗体还支持菜单与子菜单合并。</span><span class="sxs-lookup"><span data-stu-id="79b65-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="79b65-107">在本演练阐释了以下任务：</span><span class="sxs-lookup"><span data-stu-id="79b65-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="79b65-108">创建一个 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="79b65-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="79b65-109">正在创建你的窗体的主菜单。</span><span class="sxs-lookup"><span data-stu-id="79b65-109">Creating the main menu for your form.</span></span> <span data-ttu-id="79b65-110">在菜单的实际名称将有所不同。</span><span class="sxs-lookup"><span data-stu-id="79b65-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="79b65-111">添加<xref:System.Windows.Forms.ToolStripPanel>控制对**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="79b65-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="79b65-112">创建子窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="79b65-113">排列<xref:System.Windows.Forms.ToolStripPanel>按 z 顺序的控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="79b65-114">完成，你将拥有支持菜单合并功能和可移动的 MDI 窗体<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="79b65-115">若要将代码复制本主题中的一个列表，请参阅[如何： 创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="79b65-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79b65-116">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="79b65-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="79b65-117">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="79b65-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="79b65-118">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="79b65-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="79b65-119">系统必备</span><span class="sxs-lookup"><span data-stu-id="79b65-119">Prerequisites</span></span>  
 <span data-ttu-id="79b65-120">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="79b65-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="79b65-121">若要能够创建和安装 Visual Studio 的计算机上运行 Windows 窗体应用程序项目的足够权限。</span><span class="sxs-lookup"><span data-stu-id="79b65-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="79b65-122">创建项目</span><span class="sxs-lookup"><span data-stu-id="79b65-122">Creating the Project</span></span>  
 <span data-ttu-id="79b65-123">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="79b65-124">要创建项目</span><span class="sxs-lookup"><span data-stu-id="79b65-124">To create the project</span></span>  
  
1.  <span data-ttu-id="79b65-125">创建一个名为 Windows 应用程序项目**mdi 窗体**(**文件** > **新建** > **项目** > **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**).</span><span class="sxs-lookup"><span data-stu-id="79b65-125">Create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="79b65-126">在 Windows 窗体设计器中，选择窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-126">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="79b65-127">在属性窗口中设置的值<xref:System.Windows.Forms.Form.IsMdiContainer%2A>到`true`。</span><span class="sxs-lookup"><span data-stu-id="79b65-127">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="79b65-128">创建主菜单</span><span class="sxs-lookup"><span data-stu-id="79b65-128">Creating the Main Menu</span></span>  
 <span data-ttu-id="79b65-129">MDI 父窗体包含主菜单。</span><span class="sxs-lookup"><span data-stu-id="79b65-129">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="79b65-130">主菜单有一个名为菜单项**窗口**。</span><span class="sxs-lookup"><span data-stu-id="79b65-130">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="79b65-131">与**窗口**菜单项，可以创建子窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-131">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="79b65-132">从子窗体的菜单项合并到主菜单中。</span><span class="sxs-lookup"><span data-stu-id="79b65-132">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="79b65-133">若要创建主菜单</span><span class="sxs-lookup"><span data-stu-id="79b65-133">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="79b65-134">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="79b65-135">添加<xref:System.Windows.Forms.ToolStripMenuItem>到<xref:System.Windows.Forms.MenuStrip>控制并将其命名**窗口**。</span><span class="sxs-lookup"><span data-stu-id="79b65-135">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="79b65-136">选择 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-136">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="79b65-137">在属性窗口中设置的值<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>属性设置为`ToolStripMenuItem1`。</span><span class="sxs-lookup"><span data-stu-id="79b65-137">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="79b65-138">添加到子项**窗口**菜单项，并将其命名**新建**。</span><span class="sxs-lookup"><span data-stu-id="79b65-138">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="79b65-139">在属性窗口中，单击**事件**。</span><span class="sxs-lookup"><span data-stu-id="79b65-139">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="79b65-140">双击<xref:System.Windows.Forms.ToolStripItem.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="79b65-140">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="79b65-141">Windows 窗体设计器生成的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="79b65-141">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="79b65-142">以下代码插入到的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="79b65-142">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="79b65-143">向工具箱添加 ToolStripPanel 控件</span><span class="sxs-lookup"><span data-stu-id="79b65-143">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="79b65-144">当你使用<xref:System.Windows.Forms.MenuStrip>必须具有的 MDI 窗体控件<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-144">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="79b65-145">必须添加<xref:System.Windows.Forms.ToolStripPanel>控制对**工具箱**来生成你在 Windows 窗体设计器中的 MDI 窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-145">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="79b65-146">ToolStripPanel 控件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="79b65-146">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="79b65-147">打开**工具箱**，然后单击**所有 Windows 窗体**选项卡以显示可用的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-147">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="79b65-148">若要打开快捷菜单中，右键单击并选择**选择项**。</span><span class="sxs-lookup"><span data-stu-id="79b65-148">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="79b65-149">在中**选择工具箱项**对话框中，向下滚动**名称**列，直到找到**ToolStripPanel**。</span><span class="sxs-lookup"><span data-stu-id="79b65-149">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="79b65-150">选中的复选框**ToolStripPanel**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="79b65-150">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="79b65-151"><xref:System.Windows.Forms.ToolStripPanel>控件会出现在**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="79b65-151">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="79b65-152">创建子窗体</span><span class="sxs-lookup"><span data-stu-id="79b65-152">Creating a Child Form</span></span>  
 <span data-ttu-id="79b65-153">在此过程中，您将定义具有其自己的单独的子窗体类<xref:System.Windows.Forms.MenuStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-153">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="79b65-154">此窗体的菜单项将与父窗体的合并。</span><span class="sxs-lookup"><span data-stu-id="79b65-154">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="79b65-155">若要定义子窗体</span><span class="sxs-lookup"><span data-stu-id="79b65-155">To define a child form</span></span>  
  
1.  <span data-ttu-id="79b65-156">添加名为一个新窗体`ChildForm`到项目。</span><span class="sxs-lookup"><span data-stu-id="79b65-156">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="79b65-157">有关详细信息，请参阅[如何： 向项目添加 Windows 窗体](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1)。</span><span class="sxs-lookup"><span data-stu-id="79b65-157">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="79b65-158">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>到子窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-158">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="79b65-159">单击<xref:System.Windows.Forms.MenuStrip>控件的智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))，然后选择**编辑项**。</span><span class="sxs-lookup"><span data-stu-id="79b65-159">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="79b65-160">在中**项集合编辑器**对话框框中，添加一个新<xref:System.Windows.Forms.ToolStripMenuItem>名为**ChildMenuItem**到子菜单。</span><span class="sxs-lookup"><span data-stu-id="79b65-160">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="79b65-161">有关详细信息，请参阅[ToolStrip 项集合编辑器](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25)。</span><span class="sxs-lookup"><span data-stu-id="79b65-161">For more information, see [ToolStrip Items Collection Editor](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="79b65-162">测试窗体</span><span class="sxs-lookup"><span data-stu-id="79b65-162">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="79b65-163">若要测试你的窗体</span><span class="sxs-lookup"><span data-stu-id="79b65-163">To test your form</span></span>  
  
1.  <span data-ttu-id="79b65-164">按 F5 编译并运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-164">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="79b65-165">单击**窗口**菜单项以打开菜单，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="79b65-165">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="79b65-166">窗体的 MDI 客户端区域中创建新的子窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-166">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="79b65-167">与主菜单合并子窗体的菜单。</span><span class="sxs-lookup"><span data-stu-id="79b65-167">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="79b65-168">关闭子窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-168">Close the child form.</span></span>  
  
     <span data-ttu-id="79b65-169">从主菜单中删除子窗体的菜单。</span><span class="sxs-lookup"><span data-stu-id="79b65-169">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="79b65-170">单击**新建**几次。</span><span class="sxs-lookup"><span data-stu-id="79b65-170">Click **New** several times.</span></span>  
  
     <span data-ttu-id="79b65-171">子窗体自动列入 W**窗口**菜单项，因为<xref:System.Windows.Forms.MenuStrip>控件的<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>分配属性。</span><span class="sxs-lookup"><span data-stu-id="79b65-171">The child forms are automatically listed under the W**indow** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="79b65-172">添加 ToolStrip 的支持</span><span class="sxs-lookup"><span data-stu-id="79b65-172">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="79b65-173">在此过程中，您将添加四个<xref:System.Windows.Forms.ToolStrip>到 MDI 父窗体控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-173">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="79b65-174">每个<xref:System.Windows.Forms.ToolStrip>控件添加内部<xref:System.Windows.Forms.ToolStripPanel>控件停靠到窗体的边缘。</span><span class="sxs-lookup"><span data-stu-id="79b65-174">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="79b65-175">若要添加到 MDI 父窗体的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="79b65-175">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="79b65-176">从**工具箱**，拖动<xref:System.Windows.Forms.ToolStripPanel>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-176">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="79b65-177">与<xref:System.Windows.Forms.ToolStripPanel>控件处于选中状态，双击<xref:System.Windows.Forms.ToolStrip>控制**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="79b65-177">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="79b65-178">一个<xref:System.Windows.Forms.ToolStrip>控件中创建<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-178">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="79b65-179">选择 <xref:System.Windows.Forms.ToolStripPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-179">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="79b65-180">在属性窗口更改控件的值<xref:System.Windows.Forms.Control.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.Left>。</span><span class="sxs-lookup"><span data-stu-id="79b65-180">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="79b65-181"><xref:System.Windows.Forms.ToolStripPanel>控件停靠到窗体中，主菜单下的左侧。</span><span class="sxs-lookup"><span data-stu-id="79b65-181">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="79b65-182">在 MDI 工作区调整大小以适合<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-182">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="79b65-183">重复步骤 1 至 4。</span><span class="sxs-lookup"><span data-stu-id="79b65-183">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="79b65-184">停靠新<xref:System.Windows.Forms.ToolStripPanel>到窗体顶部的控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-184">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="79b65-185"><xref:System.Windows.Forms.ToolStripPanel>控件下方主菜单中，但第一个右侧停靠<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-185">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="79b65-186">本步骤说明了在正确定位的 z 顺序的重要性<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-186">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="79b65-187">对两个重复步骤 1 到 4<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-187">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="79b65-188">停靠新<xref:System.Windows.Forms.ToolStripPanel>向右侧和底部的窗体控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-188">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="79b65-189">排列按 Z 顺序的 ToolStripPanel 控件</span><span class="sxs-lookup"><span data-stu-id="79b65-189">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="79b65-190">停靠的位置<xref:System.Windows.Forms.ToolStripPanel>MDI 窗体上的控件由 z 顺序中的控件的位置。</span><span class="sxs-lookup"><span data-stu-id="79b65-190">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="79b65-191">您可以轻松地排列在文档大纲窗口中控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="79b65-191">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="79b65-192">若要排列按 Z 顺序的 ToolStripPanel 控件</span><span class="sxs-lookup"><span data-stu-id="79b65-192">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="79b65-193">在中**视图**菜单上，单击**其他 Windows**，然后单击**文档大纲**。</span><span class="sxs-lookup"><span data-stu-id="79b65-193">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="79b65-194">排列方式在<xref:System.Windows.Forms.ToolStripPanel>控件从前面的过程是使用了非标准。</span><span class="sxs-lookup"><span data-stu-id="79b65-194">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="79b65-195">这是因为 z 顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="79b65-195">This is because the z-order is not correct.</span></span> <span data-ttu-id="79b65-196">使用文档大纲窗口更改控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="79b65-196">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="79b65-197">在文档大纲窗口中，选择**ToolStripPanel4**。</span><span class="sxs-lookup"><span data-stu-id="79b65-197">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="79b65-198">单击向下箭头按钮重复，直到**ToolStripPanel4**位于列表的底部。</span><span class="sxs-lookup"><span data-stu-id="79b65-198">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="79b65-199">**ToolStripPanel4**控件停靠到窗体中，在其他控件下的底部。</span><span class="sxs-lookup"><span data-stu-id="79b65-199">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="79b65-200">选择**ToolStripPanel2**。</span><span class="sxs-lookup"><span data-stu-id="79b65-200">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="79b65-201">一次单击向下箭头按钮以在列表中第三个放置控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-201">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="79b65-202">**ToolStripPanel2**控件停靠到窗体，下面的主菜单和高于其他控件的顶部。</span><span class="sxs-lookup"><span data-stu-id="79b65-202">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="79b65-203">选择中的各个控件**文档大纲**窗口并将它们移动到不同的 z 顺序中的位置。</span><span class="sxs-lookup"><span data-stu-id="79b65-203">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="79b65-204">请注意对停靠控件的位置的 z 顺序的影响。</span><span class="sxs-lookup"><span data-stu-id="79b65-204">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="79b65-205">使用 CTRL-Z 或**撤消**上**编辑**菜单上，若要撤消所做的更改。</span><span class="sxs-lookup"><span data-stu-id="79b65-205">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="79b65-206">检查点</span><span class="sxs-lookup"><span data-stu-id="79b65-206">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="79b65-207">若要测试你的窗体</span><span class="sxs-lookup"><span data-stu-id="79b65-207">To test your form</span></span>  
  
1.  <span data-ttu-id="79b65-208">按 F5 编译并运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-208">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="79b65-209">单击的手柄<xref:System.Windows.Forms.ToolStrip>控件，窗体上将控件拖到不同的位置。</span><span class="sxs-lookup"><span data-stu-id="79b65-209">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="79b65-210">可以拖动<xref:System.Windows.Forms.ToolStrip>控件从一个<xref:System.Windows.Forms.ToolStripPanel>到另一个控件。</span><span class="sxs-lookup"><span data-stu-id="79b65-210">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="79b65-211">后续步骤</span><span class="sxs-lookup"><span data-stu-id="79b65-211">Next Steps</span></span>  
 <span data-ttu-id="79b65-212">在本演练中，您创建了一个 MDI 父窗体<xref:System.Windows.Forms.ToolStrip>控件和菜单合并。</span><span class="sxs-lookup"><span data-stu-id="79b65-212">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="79b65-213">可以使用<xref:System.Windows.Forms.ToolStrip>实现多种其他用途的控件的系列：</span><span class="sxs-lookup"><span data-stu-id="79b65-213">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="79b65-214">创建与控件的快捷菜单<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="79b65-214">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="79b65-215">有关详细信息，请参阅[ContextMenu 组件概述](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="79b65-215">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="79b65-216">创建一个自动填充的标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="79b65-216">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="79b65-217">有关详细信息，请参阅[演练： 向窗体提供标准菜单项](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="79b65-217">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="79b65-218">提供你<xref:System.Windows.Forms.ToolStrip>控件专业的外观。</span><span class="sxs-lookup"><span data-stu-id="79b65-218">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="79b65-219">有关详细信息，请参阅[如何： 设置 ToolStrip 呈现程序](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="79b65-219">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b65-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="79b65-220">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="79b65-221">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="79b65-221">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="79b65-222">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="79b65-222">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="79b65-223">如何：将 MenuStrip 插入 MDI 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="79b65-223">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="79b65-224">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="79b65-224">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
