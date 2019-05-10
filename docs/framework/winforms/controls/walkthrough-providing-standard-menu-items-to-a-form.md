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
ms.openlocfilehash: ebfacadfee3ea069359a72ea0402751e9e6280d7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211501"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="14d52-102">演练：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="14d52-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="14d52-103">可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。</span><span class="sxs-lookup"><span data-stu-id="14d52-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="14d52-104">本演练演示如何使用<xref:System.Windows.Forms.MenuStrip>控件创建标准菜单。</span><span class="sxs-lookup"><span data-stu-id="14d52-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="14d52-105">在窗体还时用户选择菜单项的响应。</span><span class="sxs-lookup"><span data-stu-id="14d52-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="14d52-106">在本演练阐释了以下任务：</span><span class="sxs-lookup"><span data-stu-id="14d52-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="14d52-107">创建一个 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="14d52-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="14d52-108">创建标准菜单。</span><span class="sxs-lookup"><span data-stu-id="14d52-108">Creating a standard menu.</span></span>

- <span data-ttu-id="14d52-109">创建<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="14d52-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="14d52-110">处理菜单项的选择。</span><span class="sxs-lookup"><span data-stu-id="14d52-110">Handling menu item selection.</span></span>

<span data-ttu-id="14d52-111">完成，你将拥有带有标准菜单显示菜单项选择中的窗体<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="14d52-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="14d52-112">要将本主题中的代码作为单个列表进行复制，请参阅[如何：向窗体提供标准菜单项](how-to-provide-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="14d52-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14d52-113">系统必备</span><span class="sxs-lookup"><span data-stu-id="14d52-113">Prerequisites</span></span>

<span data-ttu-id="14d52-114">你将需要 Visual Studio 来完成本演练。</span><span class="sxs-lookup"><span data-stu-id="14d52-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="14d52-115">创建项目</span><span class="sxs-lookup"><span data-stu-id="14d52-115">Create the project</span></span>

1. <span data-ttu-id="14d52-116">在 Visual Studio 中，创建一个名为 Windows 应用程序项目**StandardMenuForm** (**文件** > **新建** > **项目**  >  **Visual C#** 或**Visual Basic** > **经典桌面** >  **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="14d52-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="14d52-117">在 Windows 窗体设计器中，选择窗体。</span><span class="sxs-lookup"><span data-stu-id="14d52-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="14d52-118">创建标准菜单</span><span class="sxs-lookup"><span data-stu-id="14d52-118">Create a standard menu</span></span>

<span data-ttu-id="14d52-119">Windows 窗体设计器可以自动填充<xref:System.Windows.Forms.MenuStrip>带有标准菜单项控件。</span><span class="sxs-lookup"><span data-stu-id="14d52-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="14d52-120">从**工具箱**，拖动<xref:System.Windows.Forms.MenuStrip>控件拖到窗体上的。</span><span class="sxs-lookup"><span data-stu-id="14d52-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="14d52-121">单击<xref:System.Windows.Forms.MenuStrip>控件的智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))，然后选择**插入标准项**。</span><span class="sxs-lookup"><span data-stu-id="14d52-121">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="14d52-122"><xref:System.Windows.Forms.MenuStrip>使用标准菜单项填充控件。</span><span class="sxs-lookup"><span data-stu-id="14d52-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="14d52-123">单击**文件**菜单项以查看其默认菜单项和对应的图标。</span><span class="sxs-lookup"><span data-stu-id="14d52-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="14d52-124">创建 StatusStrip 控件</span><span class="sxs-lookup"><span data-stu-id="14d52-124">Create a StatusStrip control</span></span>

<span data-ttu-id="14d52-125">使用<xref:System.Windows.Forms.StatusStrip>控件来显示 Windows 窗体应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="14d52-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="14d52-126">在本示例中，用户选择菜单项显示在<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="14d52-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="14d52-127">从**工具箱**，拖动<xref:System.Windows.Forms.StatusStrip>控件拖到窗体上的。</span><span class="sxs-lookup"><span data-stu-id="14d52-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="14d52-128"><xref:System.Windows.Forms.StatusStrip>控件自动将停靠到窗体的底部。</span><span class="sxs-lookup"><span data-stu-id="14d52-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="14d52-129">单击<xref:System.Windows.Forms.StatusStrip>控件的下拉按钮并选择**statuslabel 设置**以添加<xref:System.Windows.Forms.ToolStripStatusLabel>控制对<xref:System.Windows.Forms.StatusStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="14d52-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="14d52-130">处理项选择</span><span class="sxs-lookup"><span data-stu-id="14d52-130">Handle item selection</span></span>

<span data-ttu-id="14d52-131">处理<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件，当用户选择菜单项时进行响应。</span><span class="sxs-lookup"><span data-stu-id="14d52-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="14d52-132">单击**文件**菜单项，在创建创建标准菜单部分。</span><span class="sxs-lookup"><span data-stu-id="14d52-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="14d52-133">在“属性”窗口中，单击“事件”。</span><span class="sxs-lookup"><span data-stu-id="14d52-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="14d52-134">双击<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件。</span><span class="sxs-lookup"><span data-stu-id="14d52-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="14d52-135">Windows 窗体设计器生成的事件处理程序<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>事件。</span><span class="sxs-lookup"><span data-stu-id="14d52-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="14d52-136">以下代码插入到的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="14d52-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="14d52-137">插入`UpdateStatus`到窗体的实用程序方法定义。</span><span class="sxs-lookup"><span data-stu-id="14d52-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="14d52-138">检查点-测试你的窗体</span><span class="sxs-lookup"><span data-stu-id="14d52-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="14d52-139">按**F5**编译并运行你的窗体。</span><span class="sxs-lookup"><span data-stu-id="14d52-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="14d52-140">单击**文件**要打开的菜单的菜单项。</span><span class="sxs-lookup"><span data-stu-id="14d52-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="14d52-141">上**文件**菜单中，单击某一项以将其选中。</span><span class="sxs-lookup"><span data-stu-id="14d52-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="14d52-142"><xref:System.Windows.Forms.StatusStrip>控件显示所选的项。</span><span class="sxs-lookup"><span data-stu-id="14d52-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="14d52-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="14d52-143">Next steps</span></span>

<span data-ttu-id="14d52-144">在本演练中，已创建带有标准菜单窗体。</span><span class="sxs-lookup"><span data-stu-id="14d52-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="14d52-145">可以使用<xref:System.Windows.Forms.ToolStrip>实现多种其他用途的控件的系列：</span><span class="sxs-lookup"><span data-stu-id="14d52-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="14d52-146">创建与控件的快捷菜单<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="14d52-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="14d52-147">有关详细信息，请参阅[ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="14d52-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="14d52-148">创建多文档界面 (MDI) 窗体通过停靠<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="14d52-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="14d52-149">有关详细信息，请参见[演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="14d52-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="14d52-150">提供你<xref:System.Windows.Forms.ToolStrip>控件专业的外观。</span><span class="sxs-lookup"><span data-stu-id="14d52-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="14d52-151">有关详细信息，请参阅[如何：设置 ToolStrip 呈现程序](how-to-set-the-toolstrip-renderer-for-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="14d52-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14d52-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="14d52-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="14d52-153">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="14d52-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
