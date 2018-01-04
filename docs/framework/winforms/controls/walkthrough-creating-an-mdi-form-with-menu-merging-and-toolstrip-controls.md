---
title: "演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体"
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
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b170c3e3311dbbfb070a66107bd4f22407647bae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="37d2b-102">演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体</span><span class="sxs-lookup"><span data-stu-id="37d2b-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="37d2b-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。</span><span class="sxs-lookup"><span data-stu-id="37d2b-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="37d2b-104">MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="37d2b-105">本演练演示如何使用<xref:System.Windows.Forms.ToolStripPanel>具有的 MDI 窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="37d2b-106">此窗体还支持菜单与子菜单合并。</span><span class="sxs-lookup"><span data-stu-id="37d2b-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="37d2b-107">在本演练阐释了以下任务：</span><span class="sxs-lookup"><span data-stu-id="37d2b-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="37d2b-108">创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="37d2b-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="37d2b-109">创建你的窗体的主菜单。</span><span class="sxs-lookup"><span data-stu-id="37d2b-109">Creating the main menu for your form.</span></span> <span data-ttu-id="37d2b-110">菜单上的实际名称将有所不同。</span><span class="sxs-lookup"><span data-stu-id="37d2b-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="37d2b-111">添加<xref:System.Windows.Forms.ToolStripPanel>控制转移到**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="37d2b-112">创建子窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="37d2b-113">排列<xref:System.Windows.Forms.ToolStripPanel>按 z 顺序的控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="37d2b-114">完成后，你将具有支持菜单合并功能和可移动的 MDI 窗体<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="37d2b-115">若要将代码复制本主题中的一个单独的清单，请参阅[如何： 创建具有菜单合并和 ToolStrip 控件的 MDI 窗体](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="37d2b-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37d2b-116">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="37d2b-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="37d2b-117">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="37d2b-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="37d2b-118">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="37d2b-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="37d2b-119">系统必备</span><span class="sxs-lookup"><span data-stu-id="37d2b-119">Prerequisites</span></span>  
 <span data-ttu-id="37d2b-120">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="37d2b-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="37d2b-121">若要能够创建和运行的计算机上的 Windows 窗体应用程序项目的足够权限其中[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="37d2b-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="37d2b-122">创建项目</span><span class="sxs-lookup"><span data-stu-id="37d2b-122">Creating the Project</span></span>  
 <span data-ttu-id="37d2b-123">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="37d2b-124">要创建项目</span><span class="sxs-lookup"><span data-stu-id="37d2b-124">To create the project</span></span>  
  
1.  <span data-ttu-id="37d2b-125">创建一个名为的 Windows 应用程序项目**mdi 窗体**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-125">Create a Windows Application project called **MdiForm**.</span></span>  
  
     <span data-ttu-id="37d2b-126">有关详细信息，请参阅 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="37d2b-126">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="37d2b-127">在 Windows 窗体设计器中，选择窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-127">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="37d2b-128">在属性窗口中，将的值设置<xref:System.Windows.Forms.Form.IsMdiContainer%2A>到`true`。</span><span class="sxs-lookup"><span data-stu-id="37d2b-128">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="37d2b-129">创建主菜单</span><span class="sxs-lookup"><span data-stu-id="37d2b-129">Creating the Main Menu</span></span>  
 <span data-ttu-id="37d2b-130">MDI 父窗体包含主菜单。</span><span class="sxs-lookup"><span data-stu-id="37d2b-130">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="37d2b-131">主菜单有一个名为菜单项**窗口**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-131">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="37d2b-132">与**窗口**菜单项，你可以创建子窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-132">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="37d2b-133">从子窗体的菜单项合并到主菜单中。</span><span class="sxs-lookup"><span data-stu-id="37d2b-133">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="37d2b-134">若要创建主菜单</span><span class="sxs-lookup"><span data-stu-id="37d2b-134">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="37d2b-135">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="37d2b-136">添加<xref:System.Windows.Forms.ToolStripMenuItem>到<xref:System.Windows.Forms.MenuStrip>控制并将其命名**窗口**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-136">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="37d2b-137">选择 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-137">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="37d2b-138">在属性窗口中，将的值设置<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>属性`ToolStripMenuItem1`。</span><span class="sxs-lookup"><span data-stu-id="37d2b-138">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="37d2b-139">添加到一个子项**窗口**菜单项，并将其命名**新建**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-139">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="37d2b-140">在属性窗口中，单击**事件**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-140">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="37d2b-141">双击<xref:System.Windows.Forms.ToolStripItem.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-141">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="37d2b-142">Windows 窗体设计器生成的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-142">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="37d2b-143">下列代码插入到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="37d2b-143">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="37d2b-144">将 ToolStripPanel 控件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="37d2b-144">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="37d2b-145">当你使用<xref:System.Windows.Forms.MenuStrip>具有必须具有的 MDI 窗体的控件<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-145">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="37d2b-146">你必须添加<xref:System.Windows.Forms.ToolStripPanel>控制转移到**工具箱**来生成你在 Windows 窗体设计器中的 MDI 窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-146">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="37d2b-147">ToolStripPanel 控件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="37d2b-147">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="37d2b-148">打开**工具箱**，然后单击**所有 Windows 窗体**选项卡来显示可用的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-148">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="37d2b-149">右键单击以打开快捷菜单，然后选择**选择项**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-149">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="37d2b-150">在**选择工具箱项**对话框中，向下滚动**名称**列直到找到**ToolStripPanel**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-150">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="37d2b-151">选中的复选框通过**ToolStripPanel**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-151">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="37d2b-152"><xref:System.Windows.Forms.ToolStripPanel>控件会出现在**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-152">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="37d2b-153">创建子窗体</span><span class="sxs-lookup"><span data-stu-id="37d2b-153">Creating a Child Form</span></span>  
 <span data-ttu-id="37d2b-154">在此过程中，你将定义具有其自己的单独的子窗体类<xref:System.Windows.Forms.MenuStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-154">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="37d2b-155">此窗体的菜单项会与父窗体的合并。</span><span class="sxs-lookup"><span data-stu-id="37d2b-155">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="37d2b-156">若要定义子窗体</span><span class="sxs-lookup"><span data-stu-id="37d2b-156">To define a child form</span></span>  
  
1.  <span data-ttu-id="37d2b-157">添加名为的新窗体`ChildForm`到项目。</span><span class="sxs-lookup"><span data-stu-id="37d2b-157">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="37d2b-158">有关详细信息，请参阅[如何： 向项目添加 Windows 窗体](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)。</span><span class="sxs-lookup"><span data-stu-id="37d2b-158">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="37d2b-159">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>拖到子窗体控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-159">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="37d2b-160">单击<xref:System.Windows.Forms.MenuStrip>控件的智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))，然后选择**编辑项**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-160">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="37d2b-161">在**项集合编辑器**对话框框中，添加一个新<xref:System.Windows.Forms.ToolStripMenuItem>名为**ChildMenuItem**到子菜单。</span><span class="sxs-lookup"><span data-stu-id="37d2b-161">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="37d2b-162">有关详细信息，请参阅[ToolStrip 项集合编辑器](http://msdn.microsoft.com/en-us/e681f3ab-94ba-4b2b-ac64-1dfad46caa25)。</span><span class="sxs-lookup"><span data-stu-id="37d2b-162">For more information, see [ToolStrip Items Collection Editor](http://msdn.microsoft.com/en-us/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="37d2b-163">测试窗体</span><span class="sxs-lookup"><span data-stu-id="37d2b-163">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="37d2b-164">若要测试你的窗体</span><span class="sxs-lookup"><span data-stu-id="37d2b-164">To test your form</span></span>  
  
1.  <span data-ttu-id="37d2b-165">按 F5 编译和运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-165">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="37d2b-166">单击**窗口**菜单项，以打开菜单，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-166">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="37d2b-167">在窗体的 MDI 工作区中创建新的子窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-167">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="37d2b-168">主菜单与子窗体的菜单合并。</span><span class="sxs-lookup"><span data-stu-id="37d2b-168">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="37d2b-169">关闭子窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-169">Close the child form.</span></span>  
  
     <span data-ttu-id="37d2b-170">从主菜单中删除子窗体的菜单。</span><span class="sxs-lookup"><span data-stu-id="37d2b-170">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="37d2b-171">单击**新建**多次。</span><span class="sxs-lookup"><span data-stu-id="37d2b-171">Click **New** several times.</span></span>  
  
     <span data-ttu-id="37d2b-172">子窗体自动下列出 W**窗口**菜单项，因为<xref:System.Windows.Forms.MenuStrip>控件的<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>属性分配。</span><span class="sxs-lookup"><span data-stu-id="37d2b-172">The child forms are automatically listed under the W**indow** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="37d2b-173">添加 ToolStrip 支持</span><span class="sxs-lookup"><span data-stu-id="37d2b-173">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="37d2b-174">在此过程中，你将添加四个<xref:System.Windows.Forms.ToolStrip>到 MDI 父窗体控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-174">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="37d2b-175">每个<xref:System.Windows.Forms.ToolStrip>内添加控件<xref:System.Windows.Forms.ToolStripPanel>控件，该窗体的边缘停靠。</span><span class="sxs-lookup"><span data-stu-id="37d2b-175">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="37d2b-176">若要添加到 MDI 父窗体的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="37d2b-176">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="37d2b-177">从**工具箱**，拖动<xref:System.Windows.Forms.ToolStripPanel>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-177">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="37d2b-178">与<xref:System.Windows.Forms.ToolStripPanel>选择控件中，双击<xref:System.Windows.Forms.ToolStrip>中控制**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-178">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="37d2b-179">A<xref:System.Windows.Forms.ToolStrip>控件中创建<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-179">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="37d2b-180">选择 <xref:System.Windows.Forms.ToolStripPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-180">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="37d2b-181">在属性窗口中，更改控件的值，<xref:System.Windows.Forms.Control.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Left>。</span><span class="sxs-lookup"><span data-stu-id="37d2b-181">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="37d2b-182"><xref:System.Windows.Forms.ToolStripPanel>控制停靠到窗体中，主菜单下的左侧。</span><span class="sxs-lookup"><span data-stu-id="37d2b-182">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="37d2b-183">MDI 客户端区域调整大小以适合<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-183">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="37d2b-184">重复步骤 1 至 4。</span><span class="sxs-lookup"><span data-stu-id="37d2b-184">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="37d2b-185">停靠新<xref:System.Windows.Forms.ToolStripPanel>控件添加到窗体顶部。</span><span class="sxs-lookup"><span data-stu-id="37d2b-185">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="37d2b-186"><xref:System.Windows.Forms.ToolStripPanel>控件停靠下方主菜单中，但第一个右侧<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-186">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="37d2b-187">本步骤说明了中正确定位的 z 顺序的重要性<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-187">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="37d2b-188">对两个以上重复步骤 1 至 4<xref:System.Windows.Forms.ToolStripPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-188">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="37d2b-189">停靠新<xref:System.Windows.Forms.ToolStripPanel>向右侧和底部的窗体控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-189">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="37d2b-190">排列按 Z 顺序的 ToolStripPanel 控件</span><span class="sxs-lookup"><span data-stu-id="37d2b-190">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="37d2b-191">停靠的位置<xref:System.Windows.Forms.ToolStripPanel>MDI 窗体上的控件由在 z 顺序中的控件的位置。</span><span class="sxs-lookup"><span data-stu-id="37d2b-191">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="37d2b-192">你可以方便地排列的文档大纲窗口中控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="37d2b-192">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="37d2b-193">排列按 Z 顺序的 ToolStripPanel 控件</span><span class="sxs-lookup"><span data-stu-id="37d2b-193">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="37d2b-194">在**视图**菜单上，单击**其他窗口**，然后单击**文档大纲**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-194">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="37d2b-195">排列方式你<xref:System.Windows.Forms.ToolStripPanel>控件从前面的过程是使用了非标准。</span><span class="sxs-lookup"><span data-stu-id="37d2b-195">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="37d2b-196">这是因为 z 顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="37d2b-196">This is because the z-order is not correct.</span></span> <span data-ttu-id="37d2b-197">使用文档大纲窗口更改控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="37d2b-197">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="37d2b-198">在文档大纲窗口中，选择**ToolStripPanel4**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-198">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="37d2b-199">单击向下箭头按钮重复，直到**ToolStripPanel4**位于列表的底部。</span><span class="sxs-lookup"><span data-stu-id="37d2b-199">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="37d2b-200">**ToolStripPanel4**控件停靠到窗体，其他控件下的底部。</span><span class="sxs-lookup"><span data-stu-id="37d2b-200">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="37d2b-201">选择**ToolStripPanel2**。</span><span class="sxs-lookup"><span data-stu-id="37d2b-201">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="37d2b-202">一次单击向下箭头按钮在列表中的第三个定位控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-202">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="37d2b-203">**ToolStripPanel2**控件停靠到窗体，下方的主菜单和其他控件上方的顶部。</span><span class="sxs-lookup"><span data-stu-id="37d2b-203">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="37d2b-204">选择在不同的控件**文档大纲**窗口并将它们移到不同的 z 顺序的位置。</span><span class="sxs-lookup"><span data-stu-id="37d2b-204">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="37d2b-205">请注意对放置停靠的控件的 z 顺序的影响。</span><span class="sxs-lookup"><span data-stu-id="37d2b-205">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="37d2b-206">使用 CTRL-Z 或**撤消**上**编辑**菜单上，若要撤消所做的更改。</span><span class="sxs-lookup"><span data-stu-id="37d2b-206">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="37d2b-207">检查点</span><span class="sxs-lookup"><span data-stu-id="37d2b-207">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="37d2b-208">若要测试你的窗体</span><span class="sxs-lookup"><span data-stu-id="37d2b-208">To test your form</span></span>  
  
1.  <span data-ttu-id="37d2b-209">按 F5 编译和运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-209">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="37d2b-210">单击的手柄<xref:System.Windows.Forms.ToolStrip>控件并将控件拖动到不同的位置，在窗体上。</span><span class="sxs-lookup"><span data-stu-id="37d2b-210">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="37d2b-211">您可以拖动<xref:System.Windows.Forms.ToolStrip>控件从一个<xref:System.Windows.Forms.ToolStripPanel>到另一个控件。</span><span class="sxs-lookup"><span data-stu-id="37d2b-211">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="37d2b-212">后续步骤</span><span class="sxs-lookup"><span data-stu-id="37d2b-212">Next Steps</span></span>  
 <span data-ttu-id="37d2b-213">在本演练中，您已经创建具有一个 MDI 父窗体<xref:System.Windows.Forms.ToolStrip>控件和菜单合并。</span><span class="sxs-lookup"><span data-stu-id="37d2b-213">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="37d2b-214">你可以使用<xref:System.Windows.Forms.ToolStrip>系列实现多种其他用途的控件：</span><span class="sxs-lookup"><span data-stu-id="37d2b-214">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="37d2b-215">创建与你的控件的快捷菜单<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="37d2b-215">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="37d2b-216">有关详细信息，请参阅[ContextMenu 组件概述](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="37d2b-216">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="37d2b-217">创建一个自动填充的标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="37d2b-217">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="37d2b-218">有关详细信息，请参阅[演练： 向窗体提供标准菜单项](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="37d2b-218">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="37d2b-219">提供你<xref:System.Windows.Forms.ToolStrip>控件专业的外观。</span><span class="sxs-lookup"><span data-stu-id="37d2b-219">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="37d2b-220">有关详细信息，请参阅[如何： 设置 ToolStrip 呈现程序应用程序](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="37d2b-220">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d2b-221">请参阅</span><span class="sxs-lookup"><span data-stu-id="37d2b-221">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="37d2b-222">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="37d2b-222">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="37d2b-223">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="37d2b-223">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="37d2b-224">如何：将 MenuStrip 插入 MDI 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="37d2b-224">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="37d2b-225">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="37d2b-225">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
