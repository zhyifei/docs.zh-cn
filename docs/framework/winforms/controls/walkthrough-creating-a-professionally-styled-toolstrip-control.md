---
title: "演练：创建具有专业样式的 ToolStrip 控件"
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
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3d47f285643f0b989db9419392eed736d0efbea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="09464-102">演练：创建具有专业样式的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="09464-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="09464-103">可让你的应用程序<xref:System.Windows.Forms.ToolStrip>控制专业的外观和行为，通过编写您自己的类派生自<xref:System.Windows.Forms.ToolStripProfessionalRenderer>类型。</span><span class="sxs-lookup"><span data-stu-id="09464-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="09464-104">本演练演示如何使用<xref:System.Windows.Forms.ToolStrip>控件，创建复合控件类似于**导航窗格中**Microsoft Outlook® 提供的。</span><span class="sxs-lookup"><span data-stu-id="09464-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="09464-105">在本演练阐释了以下任务：</span><span class="sxs-lookup"><span data-stu-id="09464-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="09464-106">创建 Windows 控件库项目。</span><span class="sxs-lookup"><span data-stu-id="09464-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="09464-107">设计 StackView 控件。</span><span class="sxs-lookup"><span data-stu-id="09464-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="09464-108">实现自定义呈现器。</span><span class="sxs-lookup"><span data-stu-id="09464-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="09464-109">完成后，您可以在一个可重用的自定义客户端的 Microsoft Office® XP 控件专业的外观。</span><span class="sxs-lookup"><span data-stu-id="09464-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="09464-110">若要将代码复制本主题中的一个单独的清单，请参阅[如何： 创建具有专业样式的 ToolStrip 控件](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md)。</span><span class="sxs-lookup"><span data-stu-id="09464-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09464-111">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="09464-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="09464-112">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="09464-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="09464-113">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="09464-113">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="09464-114">系统必备</span><span class="sxs-lookup"><span data-stu-id="09464-114">Prerequisites</span></span>  
 <span data-ttu-id="09464-115">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="09464-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="09464-116">若要能够创建和运行的计算机上的 Windows 窗体应用程序项目的足够权限其中[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="09464-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="09464-117">创建 Windows 控件库项目</span><span class="sxs-lookup"><span data-stu-id="09464-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="09464-118">第一步是创建控件库项目。</span><span class="sxs-lookup"><span data-stu-id="09464-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="09464-119">若要创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="09464-119">To create the control library project</span></span>  
  
1.  <span data-ttu-id="09464-120">创建名为的新 Windows 控件库项目`StackViewLibrary`。</span><span class="sxs-lookup"><span data-stu-id="09464-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2.  <span data-ttu-id="09464-121">在**解决方案资源管理器**，通过删除名为了"UserControl1.cs"或"UserControl1.vb"，具体取决于所用语言的源文件来删除项目的默认控件。</span><span class="sxs-lookup"><span data-stu-id="09464-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="09464-122">有关详细信息，请参阅[NIB： 如何： 删除、 删除和排除项](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)。</span><span class="sxs-lookup"><span data-stu-id="09464-122">For more information, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
3.  <span data-ttu-id="09464-123">添加新<xref:System.Windows.Forms.UserControl>项以**StackViewLibrary**项目。</span><span class="sxs-lookup"><span data-stu-id="09464-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="09464-124">为新的源文件提供的基名称`StackView`。</span><span class="sxs-lookup"><span data-stu-id="09464-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="09464-125">设计 StackView 控件</span><span class="sxs-lookup"><span data-stu-id="09464-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="09464-126">`StackView`控件是带有一个子级的复合控件<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="09464-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="09464-127">复合控件有关的详细信息，请参阅[类型的自定义控件](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="09464-127">For more information about composite controls, see [Varieties of Custom Controls](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="09464-128">设计 StackView 控件</span><span class="sxs-lookup"><span data-stu-id="09464-128">To design the StackView control</span></span>  
  
1.  <span data-ttu-id="09464-129">从**工具箱**，拖动<xref:System.Windows.Forms.ToolStrip>到设计图面上的控件。</span><span class="sxs-lookup"><span data-stu-id="09464-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2.  <span data-ttu-id="09464-130">在**属性**窗口中，设置<xref:System.Windows.Forms.ToolStrip>根据下表的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="09464-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="09464-131">属性</span><span class="sxs-lookup"><span data-stu-id="09464-131">Property</span></span>|<span data-ttu-id="09464-132">值</span><span class="sxs-lookup"><span data-stu-id="09464-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="09464-133">name</span><span class="sxs-lookup"><span data-stu-id="09464-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="09464-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="09464-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="09464-135">停靠</span><span class="sxs-lookup"><span data-stu-id="09464-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="09464-136">字体</span><span class="sxs-lookup"><span data-stu-id="09464-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="09464-137">GripStyle</span><span class="sxs-lookup"><span data-stu-id="09464-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="09464-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="09464-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="09464-139">填充</span><span class="sxs-lookup"><span data-stu-id="09464-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="09464-140">RenderMode</span><span class="sxs-lookup"><span data-stu-id="09464-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  <span data-ttu-id="09464-141">在 Windows 窗体设计器中，单击<xref:System.Windows.Forms.ToolStrip>控件的**添加**按钮，然后添加<xref:System.Windows.Forms.ToolStripButton>到`stackStrip`控件。</span><span class="sxs-lookup"><span data-stu-id="09464-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4.  <span data-ttu-id="09464-142">在**属性**窗口中，设置<xref:System.Windows.Forms.ToolStripButton>根据下表的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="09464-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="09464-143">属性</span><span class="sxs-lookup"><span data-stu-id="09464-143">Property</span></span>|<span data-ttu-id="09464-144">值</span><span class="sxs-lookup"><span data-stu-id="09464-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="09464-145">name</span><span class="sxs-lookup"><span data-stu-id="09464-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="09464-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="09464-146">CheckOnClick</span></span>|<span data-ttu-id="09464-147">true</span><span class="sxs-lookup"><span data-stu-id="09464-147">true</span></span>|  
    |<span data-ttu-id="09464-148">复选</span><span class="sxs-lookup"><span data-stu-id="09464-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="09464-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="09464-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="09464-150">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="09464-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="09464-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="09464-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="09464-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="09464-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="09464-153">边距</span><span class="sxs-lookup"><span data-stu-id="09464-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="09464-154">填充</span><span class="sxs-lookup"><span data-stu-id="09464-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="09464-155">Text</span><span class="sxs-lookup"><span data-stu-id="09464-155">Text</span></span>|<span data-ttu-id="09464-156">**邮件**</span><span class="sxs-lookup"><span data-stu-id="09464-156">**Mail**</span></span>|  
    |<span data-ttu-id="09464-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="09464-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  <span data-ttu-id="09464-158">重复步骤 7 对于另外三个<xref:System.Windows.Forms.ToolStripButton>控件。</span><span class="sxs-lookup"><span data-stu-id="09464-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="09464-159">为控件命名`calendarStackButton`， `contactsStackButton`，和`tasksStackButton`。</span><span class="sxs-lookup"><span data-stu-id="09464-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="09464-160">设置的值<xref:System.Windows.Forms.Control.Text%2A>属性**日历**，**联系人**，和**任务**分别。</span><span class="sxs-lookup"><span data-stu-id="09464-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="09464-161">处理事件</span><span class="sxs-lookup"><span data-stu-id="09464-161">Handling Events</span></span>  
 <span data-ttu-id="09464-162">两个事件很重要使`StackView`控件正常运行。</span><span class="sxs-lookup"><span data-stu-id="09464-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="09464-163">处理<xref:System.Windows.Forms.UserControl.Load>以正确定位该控件的事件。</span><span class="sxs-lookup"><span data-stu-id="09464-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="09464-164">处理<xref:System.Windows.Forms.ToolStripItem.Click>每个事件<xref:System.Windows.Forms.ToolStripButton>以便`StackView`控制状态行为类似于<xref:System.Windows.Forms.RadioButton>控件。</span><span class="sxs-lookup"><span data-stu-id="09464-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="09464-165">若要处理的事件</span><span class="sxs-lookup"><span data-stu-id="09464-165">To handle events</span></span>  
  
1.  <span data-ttu-id="09464-166">在 Windows 窗体设计器中，选择`StackView`控件。</span><span class="sxs-lookup"><span data-stu-id="09464-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2.  <span data-ttu-id="09464-167">在**属性**窗口中，单击**事件**。</span><span class="sxs-lookup"><span data-stu-id="09464-167">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="09464-168">双击要生成的负载事件`StackView_Load`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="09464-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4.  <span data-ttu-id="09464-169">在 `StackView_Load` 事件处理程序中，复制并粘贴以下代码。</span><span class="sxs-lookup"><span data-stu-id="09464-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  <span data-ttu-id="09464-170">在 Windows 窗体设计器中，选择`mailStackButton`控件。</span><span class="sxs-lookup"><span data-stu-id="09464-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6.  <span data-ttu-id="09464-171">在**属性**窗口中，单击**事件**。</span><span class="sxs-lookup"><span data-stu-id="09464-171">In the **Properties** window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="09464-172">双击 Click 事件。</span><span class="sxs-lookup"><span data-stu-id="09464-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="09464-173">Windows 窗体设计器生成`mailStackButton_Click`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="09464-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8.  <span data-ttu-id="09464-174">重命名`mailStackButton_Click`事件处理程序`stackButton_Click`。</span><span class="sxs-lookup"><span data-stu-id="09464-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="09464-175">有关详细信息，请参阅[如何： 重命名标识符 (Visual Basic 中)](http://msdn.microsoft.com/en-us/e5a5edf8-3dba-4119-81f4-fc2aba180e0c)。</span><span class="sxs-lookup"><span data-stu-id="09464-175">For more information, see [How to: Rename an Identifier (Visual Basic)](http://msdn.microsoft.com/en-us/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).</span></span>  
  
9. <span data-ttu-id="09464-176">将以下代码插入`stackButton_Click`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="09464-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="09464-177">在 Windows 窗体设计器中，选择`calendarStackButton`控件。</span><span class="sxs-lookup"><span data-stu-id="09464-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="09464-178">在**属性**窗口中，设置为单击事件`stackButton_Click`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="09464-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="09464-179">重复步骤 10 和 11 for`contactsStackButton`和`tasksStackButton`控件。</span><span class="sxs-lookup"><span data-stu-id="09464-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="09464-180">定义图标</span><span class="sxs-lookup"><span data-stu-id="09464-180">Defining Icons</span></span>  
 <span data-ttu-id="09464-181">每个`StackView`按钮都有一个关联的图标。</span><span class="sxs-lookup"><span data-stu-id="09464-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="09464-182">为方便起见，每个图标都表示为 Base64 编码的字符串，其中进行反序列化之前<xref:System.Drawing.Bitmap>从其创建。</span><span class="sxs-lookup"><span data-stu-id="09464-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="09464-183">在生产环境中，为资源，存储位图数据和图标将显示在 Windows 窗体设计器。</span><span class="sxs-lookup"><span data-stu-id="09464-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="09464-184">有关详细信息，请参阅[如何： 向 Windows 窗体添加背景图像](http://msdn.microsoft.com/en-us/7a509ba2-055c-4ae6-b88a-54625c6d9aff)。</span><span class="sxs-lookup"><span data-stu-id="09464-184">For more information, see [How to: Add Background Images to Windows Forms](http://msdn.microsoft.com/en-us/7a509ba2-055c-4ae6-b88a-54625c6d9aff).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="09464-185">若要定义图标</span><span class="sxs-lookup"><span data-stu-id="09464-185">To define icons</span></span>  
  
1.  <span data-ttu-id="09464-186">在代码编辑器中，将以下代码插入`StackView`类定义。</span><span class="sxs-lookup"><span data-stu-id="09464-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="09464-187">此代码将初始化为位图<xref:System.Windows.Forms.ToolStripButton>图标。</span><span class="sxs-lookup"><span data-stu-id="09464-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  <span data-ttu-id="09464-188">添加对的调用`InitializeImages`中的方法`StackView`类构造函数。</span><span class="sxs-lookup"><span data-stu-id="09464-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="09464-189">实现自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="09464-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="09464-190">你可以自定义的大多数元素`StackView`控制我实现派生自的类<xref:System.Windows.Forms.ToolStripRenderer>类。</span><span class="sxs-lookup"><span data-stu-id="09464-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="09464-191">在此过程中，你将实现<xref:System.Windows.Forms.ToolStripProfessionalRenderer>类自定义手柄并绘制为渐变背景<xref:System.Windows.Forms.ToolStripButton>控件。</span><span class="sxs-lookup"><span data-stu-id="09464-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="09464-192">若要实现自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="09464-192">To implement a custom renderer</span></span>  
  
1.  <span data-ttu-id="09464-193">将以下代码插入`StackView`控制定义。</span><span class="sxs-lookup"><span data-stu-id="09464-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="09464-194">这是用于定义`StackRenderer`类，该类会重写<xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>， <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>，和<xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground>方法生成的自定义外观。</span><span class="sxs-lookup"><span data-stu-id="09464-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  <span data-ttu-id="09464-195">在`StackView`控件的构造函数创建的新实例`StackRenderer`类，将分配到此实例`stackStrip`控件的<xref:System.Windows.Forms.ToolStrip.Renderer%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="09464-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="09464-196">测试 StackView 控件</span><span class="sxs-lookup"><span data-stu-id="09464-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="09464-197">`StackView`控件派生自<xref:System.Windows.Forms.UserControl>类。</span><span class="sxs-lookup"><span data-stu-id="09464-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="09464-198">因此，你可以测试控件**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="09464-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="09464-199">有关详细信息，请参阅[如何：测试 UserControl 的运行时行为](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="09464-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="09464-200">若要测试 StackView 控件</span><span class="sxs-lookup"><span data-stu-id="09464-200">To test the StackView control</span></span>  
  
1.  <span data-ttu-id="09464-201">按 F5 以生成项目并启动**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="09464-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="09464-202">将指针移到按钮的`StackView`控件，，然后单击一个按钮以查看其所选状态的外观。</span><span class="sxs-lookup"><span data-stu-id="09464-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="09464-203">后续步骤</span><span class="sxs-lookup"><span data-stu-id="09464-203">Next Steps</span></span>  
 <span data-ttu-id="09464-204">在本演练中，你创建了一个可重用的自定义客户端控件使用 Office XP 控件的专业的外观。</span><span class="sxs-lookup"><span data-stu-id="09464-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="09464-205">你可以使用<xref:System.Windows.Forms.ToolStrip>系列实现多种其他用途的控件：</span><span class="sxs-lookup"><span data-stu-id="09464-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="09464-206">创建与你的控件的快捷菜单<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="09464-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="09464-207">有关详细信息，请参阅[ContextMenu 组件概述](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="09464-207">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="09464-208">创建带有一个自动填充的标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="09464-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="09464-209">有关详细信息，请参阅[演练： 向窗体提供标准菜单项](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="09464-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="09464-210">使用停靠创建多文档界面 (MDI) 窗体<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="09464-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="09464-211">有关详细信息，请参阅[如何： 创建具有菜单合并和 ToolStrip 控件的 MDI 窗体](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="09464-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09464-212">请参阅</span><span class="sxs-lookup"><span data-stu-id="09464-212">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="09464-213">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="09464-213">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="09464-214">如何：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="09464-214">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
