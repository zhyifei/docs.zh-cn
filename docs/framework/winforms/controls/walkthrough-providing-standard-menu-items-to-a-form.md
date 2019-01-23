---
title: 演练：向窗体提供标准菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: b0f88f8c28b613b9eae580c851ee4dd1282e77e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505102"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="9ca58-102">演练：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="9ca58-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="9ca58-103">可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。</span><span class="sxs-lookup"><span data-stu-id="9ca58-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="9ca58-104">本演练演示如何使用<xref:System.Windows.Forms.MenuStrip>控件创建标准菜单。</span><span class="sxs-lookup"><span data-stu-id="9ca58-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="9ca58-105">在窗体还时用户选择菜单项的响应。</span><span class="sxs-lookup"><span data-stu-id="9ca58-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="9ca58-106">在本演练阐释了以下任务：</span><span class="sxs-lookup"><span data-stu-id="9ca58-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="9ca58-107">创建一个 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="9ca58-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="9ca58-108">创建标准菜单。</span><span class="sxs-lookup"><span data-stu-id="9ca58-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="9ca58-109">创建<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="9ca58-110">处理菜单项的选择。</span><span class="sxs-lookup"><span data-stu-id="9ca58-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="9ca58-111">完成，你将拥有带有标准菜单显示菜单项选择中的窗体<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="9ca58-112">若要将代码复制本主题中的一个列表，请参阅[如何：向窗体提供标准菜单项](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca58-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ca58-113">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="9ca58-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9ca58-114">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="9ca58-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9ca58-115">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="9ca58-115">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9ca58-116">系统必备</span><span class="sxs-lookup"><span data-stu-id="9ca58-116">Prerequisites</span></span>  
 <span data-ttu-id="9ca58-117">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="9ca58-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="9ca58-118">若要能够创建和安装 Visual Studio 的计算机上运行 Windows 窗体应用程序项目的足够权限。</span><span class="sxs-lookup"><span data-stu-id="9ca58-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="9ca58-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="9ca58-119">Creating the Project</span></span>  
 <span data-ttu-id="9ca58-120">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="9ca58-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="9ca58-121">要创建项目</span><span class="sxs-lookup"><span data-stu-id="9ca58-121">To create the project</span></span>  
  
1.  <span data-ttu-id="9ca58-122">创建一个名为 Windows 应用程序项目**StandardMenuForm** (**文件** > **新建** > **项目** >  **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="9ca58-122">Create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="9ca58-123">在 Windows 窗体设计器中，选择窗体。</span><span class="sxs-lookup"><span data-stu-id="9ca58-123">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="9ca58-124">创建标准菜单</span><span class="sxs-lookup"><span data-stu-id="9ca58-124">Creating a Standard Menu</span></span>  
 <span data-ttu-id="9ca58-125">Windows 窗体设计器可以自动填充<xref:System.Windows.Forms.MenuStrip>带有标准菜单项控件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-125">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="9ca58-126">创建标准菜单</span><span class="sxs-lookup"><span data-stu-id="9ca58-126">To create a standard menu</span></span>  
  
1.  <span data-ttu-id="9ca58-127">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>控件拖到窗体上的。</span><span class="sxs-lookup"><span data-stu-id="9ca58-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2.  <span data-ttu-id="9ca58-128">单击<xref:System.Windows.Forms.MenuStrip>控件的智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))，然后选择**插入标准项**。</span><span class="sxs-lookup"><span data-stu-id="9ca58-128">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="9ca58-129"><xref:System.Windows.Forms.MenuStrip>使用标准菜单项填充控件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-129">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3.  <span data-ttu-id="9ca58-130">单击**文件**菜单项以查看其默认菜单项和对应的图标。</span><span class="sxs-lookup"><span data-stu-id="9ca58-130">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="9ca58-131">创建 StatusStrip 控件</span><span class="sxs-lookup"><span data-stu-id="9ca58-131">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="9ca58-132">使用<xref:System.Windows.Forms.StatusStrip>控件来显示 Windows 窗体应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="9ca58-132">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="9ca58-133">在本示例中，用户选择菜单项显示在<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-133">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="9ca58-134">若要创建 StatusStrip 控件</span><span class="sxs-lookup"><span data-stu-id="9ca58-134">To create a StatusStrip control</span></span>  
  
1.  <span data-ttu-id="9ca58-135">从**工具箱**，拖动<xref:System.Windows.Forms.StatusStrip>控件拖到窗体上的。</span><span class="sxs-lookup"><span data-stu-id="9ca58-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="9ca58-136"><xref:System.Windows.Forms.StatusStrip>控件自动将停靠到窗体的底部。</span><span class="sxs-lookup"><span data-stu-id="9ca58-136">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2.  <span data-ttu-id="9ca58-137">单击<xref:System.Windows.Forms.StatusStrip>控件的下拉按钮并选择**statuslabel 设置**以添加<xref:System.Windows.Forms.ToolStripStatusLabel>控制对<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-137">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="9ca58-138">处理项选择</span><span class="sxs-lookup"><span data-stu-id="9ca58-138">Handling Item Selection</span></span>  
 <span data-ttu-id="9ca58-139">处理<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件，当用户选择菜单项时进行响应。</span><span class="sxs-lookup"><span data-stu-id="9ca58-139">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="9ca58-140">若要处理的项选择</span><span class="sxs-lookup"><span data-stu-id="9ca58-140">To handle item selection</span></span>  
  
1.  <span data-ttu-id="9ca58-141">单击**文件**菜单项，在创建创建标准菜单部分。</span><span class="sxs-lookup"><span data-stu-id="9ca58-141">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2.  <span data-ttu-id="9ca58-142">在“属性”窗口中，单击“事件”。</span><span class="sxs-lookup"><span data-stu-id="9ca58-142">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="9ca58-143">双击<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-143">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="9ca58-144">Windows 窗体设计器生成的事件处理程序<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-144">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4.  <span data-ttu-id="9ca58-145">以下代码插入到的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9ca58-145">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  <span data-ttu-id="9ca58-146">插入`UpdateStatus`到窗体的实用程序方法定义。</span><span class="sxs-lookup"><span data-stu-id="9ca58-146">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="9ca58-147">检查点</span><span class="sxs-lookup"><span data-stu-id="9ca58-147">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="9ca58-148">若要测试你的窗体</span><span class="sxs-lookup"><span data-stu-id="9ca58-148">To test your form</span></span>  
  
1.  <span data-ttu-id="9ca58-149">按 F5 编译并运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="9ca58-149">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="9ca58-150">单击**文件**要打开的菜单的菜单项。</span><span class="sxs-lookup"><span data-stu-id="9ca58-150">Click the **File** menu item to open the menu.</span></span>  
  
3.  <span data-ttu-id="9ca58-151">上**文件**菜单中，单击某一项以将其选中。</span><span class="sxs-lookup"><span data-stu-id="9ca58-151">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="9ca58-152"><xref:System.Windows.Forms.StatusStrip>控件显示所选的项。</span><span class="sxs-lookup"><span data-stu-id="9ca58-152">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9ca58-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9ca58-153">Next Steps</span></span>  
 <span data-ttu-id="9ca58-154">在本演练中，已创建带有标准菜单窗体。</span><span class="sxs-lookup"><span data-stu-id="9ca58-154">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="9ca58-155">可以使用<xref:System.Windows.Forms.ToolStrip>实现多种其他用途的控件的系列：</span><span class="sxs-lookup"><span data-stu-id="9ca58-155">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="9ca58-156">创建与控件的快捷菜单<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="9ca58-156">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="9ca58-157">有关详细信息，请参阅[ContextMenu 组件概述](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca58-157">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="9ca58-158">创建多文档界面 (MDI) 窗体通过停靠<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-158">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="9ca58-159">有关详细信息，请参见[演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca58-159">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="9ca58-160">提供你<xref:System.Windows.Forms.ToolStrip>控件专业的外观。</span><span class="sxs-lookup"><span data-stu-id="9ca58-160">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="9ca58-161">有关详细信息，请参阅[如何：设置 ToolStrip 呈现程序](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca58-161">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca58-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ca58-162">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="9ca58-163">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="9ca58-163">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
