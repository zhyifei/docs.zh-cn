---
title: 演练：向窗体提供标准菜单项
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00988266804207e85bc715342f888fd29348066e
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="a2b4a-102">演练：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="a2b4a-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="a2b4a-103">可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="a2b4a-104">本演练演示如何使用<xref:System.Windows.Forms.MenuStrip>控件创建标准菜单。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="a2b4a-105">窗体还时用户选择菜单项的响应。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="a2b4a-106">在本演练阐释了以下任务：</span><span class="sxs-lookup"><span data-stu-id="a2b4a-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="a2b4a-107">创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="a2b4a-108">创建标准菜单。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="a2b4a-109">创建<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="a2b4a-110">处理菜单项的选择。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="a2b4a-111">完成后，你将具有带有显示菜单项选择在标准菜单的窗体<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="a2b4a-112">若要将代码复制本主题中的一个单独的清单，请参阅[如何： 向窗体提供标准菜单项](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2b4a-113">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a2b4a-114">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a2b4a-115">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a2b4a-116">系统必备</span><span class="sxs-lookup"><span data-stu-id="a2b4a-116">Prerequisites</span></span>  
 <span data-ttu-id="a2b4a-117">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="a2b4a-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="a2b4a-118">若要能够创建和运行 Windows 窗体应用程序项目的计算机上安装了 Visual Studio 的足够权限。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="a2b4a-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="a2b4a-119">Creating the Project</span></span>  
 <span data-ttu-id="a2b4a-120">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="a2b4a-121">要创建项目</span><span class="sxs-lookup"><span data-stu-id="a2b4a-121">To create the project</span></span>  
  
1.  <span data-ttu-id="a2b4a-122">创建一个名为的 Windows 应用程序项目**StandardMenuForm**。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-122">Create a Windows application project called **StandardMenuForm**.</span></span>  
  
     <span data-ttu-id="a2b4a-123">有关详细信息，请参阅[如何：创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="a2b4a-124">在 Windows 窗体设计器中，选择窗体。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-124">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="a2b4a-125">创建标准菜单</span><span class="sxs-lookup"><span data-stu-id="a2b4a-125">Creating a Standard Menu</span></span>  
 <span data-ttu-id="a2b4a-126">Windows 窗体设计器可以自动填充<xref:System.Windows.Forms.MenuStrip>具有标准菜单项控件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-126">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="a2b4a-127">创建标准菜单</span><span class="sxs-lookup"><span data-stu-id="a2b4a-127">To create a standard menu</span></span>  
  
1.  <span data-ttu-id="a2b4a-128">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>拖动到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-128">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2.  <span data-ttu-id="a2b4a-129">单击<xref:System.Windows.Forms.MenuStrip>控件的智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))，然后选择**插入标准项**。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-129">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="a2b4a-130"><xref:System.Windows.Forms.MenuStrip>控件中填充标准菜单项。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-130">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3.  <span data-ttu-id="a2b4a-131">单击**文件**菜单项以查看其默认菜单项和对应的图标。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-131">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="a2b4a-132">创建 StatusStrip 控件</span><span class="sxs-lookup"><span data-stu-id="a2b4a-132">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="a2b4a-133">使用<xref:System.Windows.Forms.StatusStrip>控件来显示 Windows 窗体应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-133">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="a2b4a-134">在本示例中，由用户选择的菜单项显示在<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-134">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="a2b4a-135">若要创建 StatusStrip 控件</span><span class="sxs-lookup"><span data-stu-id="a2b4a-135">To create a StatusStrip control</span></span>  
  
1.  <span data-ttu-id="a2b4a-136">从**工具箱**，拖动<xref:System.Windows.Forms.StatusStrip>拖动到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-136">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="a2b4a-137"><xref:System.Windows.Forms.StatusStrip>控件自动停靠到窗体的底部。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-137">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2.  <span data-ttu-id="a2b4a-138">单击<xref:System.Windows.Forms.StatusStrip>控件的下拉列表按钮，然后选择**StatusLabel**添加<xref:System.Windows.Forms.ToolStripStatusLabel>控制转移到<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-138">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="a2b4a-139">处理项选择</span><span class="sxs-lookup"><span data-stu-id="a2b4a-139">Handling Item Selection</span></span>  
 <span data-ttu-id="a2b4a-140">处理<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件，当用户选择菜单项时进行响应。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-140">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="a2b4a-141">若要处理项选择</span><span class="sxs-lookup"><span data-stu-id="a2b4a-141">To handle item selection</span></span>  
  
1.  <span data-ttu-id="a2b4a-142">单击**文件**菜单项在创建中创建标准菜单部分。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-142">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2.  <span data-ttu-id="a2b4a-143">在**属性**窗口中，单击**事件**。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-143">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="a2b4a-144">双击<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-144">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="a2b4a-145">Windows 窗体设计器生成的事件处理程序<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-145">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4.  <span data-ttu-id="a2b4a-146">下列代码插入到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-146">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  <span data-ttu-id="a2b4a-147">插入`UpdateStatus`到该窗体的实用工具方法定义。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-147">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="a2b4a-148">检查点</span><span class="sxs-lookup"><span data-stu-id="a2b4a-148">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="a2b4a-149">若要测试你的窗体</span><span class="sxs-lookup"><span data-stu-id="a2b4a-149">To test your form</span></span>  
  
1.  <span data-ttu-id="a2b4a-150">按 F5 编译和运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-150">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="a2b4a-151">单击**文件**要打开的菜单的菜单项。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-151">Click the **File** menu item to open the menu.</span></span>  
  
3.  <span data-ttu-id="a2b4a-152">上**文件**菜单上，单击某一项以将其选中。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-152">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="a2b4a-153"><xref:System.Windows.Forms.StatusStrip>控件将显示选定的项。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-153">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a2b4a-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a2b4a-154">Next Steps</span></span>  
 <span data-ttu-id="a2b4a-155">在本演练中，已创建带有标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-155">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="a2b4a-156">你可以使用<xref:System.Windows.Forms.ToolStrip>系列实现多种其他用途的控件：</span><span class="sxs-lookup"><span data-stu-id="a2b4a-156">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="a2b4a-157">创建与你的控件的快捷菜单<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-157">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="a2b4a-158">有关详细信息，请参阅[ContextMenu 组件概述](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-158">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="a2b4a-159">使用停靠创建多文档界面 (MDI) 窗体<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-159">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="a2b4a-160">有关详细信息，请参阅[演练： 创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-160">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="a2b4a-161">提供你<xref:System.Windows.Forms.ToolStrip>控件专业的外观。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-161">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="a2b4a-162">有关详细信息，请参阅[如何： 设置 ToolStrip 呈现程序应用程序](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a2b4a-162">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b4a-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2b4a-163">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="a2b4a-164">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="a2b4a-164">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
