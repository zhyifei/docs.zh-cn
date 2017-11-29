---
title: "演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2dce58776af84b1f4c733ddce2553e4b18b1b824
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a><span data-ttu-id="0e179-102">演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局</span><span class="sxs-lookup"><span data-stu-id="0e179-102">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>
<span data-ttu-id="0e179-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="0e179-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="0e179-104">**Windows 窗体设计器**为你提供许多布局工具实现此目的。</span><span class="sxs-lookup"><span data-stu-id="0e179-104">The **Windows Forms Designer** gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="0e179-105">三个最重要是<xref:System.Windows.Forms.Control.Margin%2A>， <xref:System.Windows.Forms.Control.Padding%2A>，和<xref:System.Windows.Forms.Control.AutoSize%2A>属性，所有 Windows 窗体控件存在。</span><span class="sxs-lookup"><span data-stu-id="0e179-105">Three of the most important are the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties, which are present on all Windows Forms controls.</span></span>  
  
 <span data-ttu-id="0e179-106"><xref:System.Windows.Forms.Control.Margin%2A> 属性定义控件周围的空间，该空间使其他控件与该控件的边框保持指定的距离。</span><span class="sxs-lookup"><span data-stu-id="0e179-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="0e179-107"><xref:System.Windows.Forms.Control.Padding%2A> 属性定义控件内部的空间，该空间使控件的内容（例如，其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值）与该控件的边框保持指定的距离。</span><span class="sxs-lookup"><span data-stu-id="0e179-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="0e179-108">下图显示控件上的 <xref:System.Windows.Forms.Control.Padding%2A> 和 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0e179-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="0e179-109">![填充和边距适用于 Windows 窗体控件](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="0e179-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="0e179-110"><xref:System.Windows.Forms.Control.AutoSize%2A>属性告知一个控件，用于自动调整自身大小对其内容。</span><span class="sxs-lookup"><span data-stu-id="0e179-110">The <xref:System.Windows.Forms.Control.AutoSize%2A> property tells a control to automatically size itself to its contents.</span></span> <span data-ttu-id="0e179-111">它将不调整自身大小要小于其原始值<xref:System.Windows.Forms.Control.Size%2A>属性，也将帐户的值其<xref:System.Windows.Forms.Control.Padding%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0e179-111">It will not resize itself to be smaller than the value of its original <xref:System.Windows.Forms.Control.Size%2A> property, and it will account for the value of its <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>  
  
 <span data-ttu-id="0e179-112">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="0e179-112">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="0e179-113">创建 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="0e179-113">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="0e179-114">边距设置为你的控件</span><span class="sxs-lookup"><span data-stu-id="0e179-114">Setting Margins for Your Controls</span></span>  
  
-   <span data-ttu-id="0e179-115">设置控件的填充</span><span class="sxs-lookup"><span data-stu-id="0e179-115">Setting Padding for Your Controls</span></span>  
  
-   <span data-ttu-id="0e179-116">自动调整控件大小</span><span class="sxs-lookup"><span data-stu-id="0e179-116">Automatically Sizing Your Controls</span></span>  
  
 <span data-ttu-id="0e179-117">完成上述操作后，你将会了解这些重要布局功能所发挥的作用。</span><span class="sxs-lookup"><span data-stu-id="0e179-117">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e179-118">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="0e179-118">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0e179-119">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="0e179-119">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0e179-120">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="0e179-120">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0e179-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="0e179-121">Prerequisites</span></span>  
 <span data-ttu-id="0e179-122">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="0e179-122">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="0e179-123">若要能够创建和运行 Windows 窗体应用程序项目的计算机上安装了 Visual Studio 的足够权限。</span><span class="sxs-lookup"><span data-stu-id="0e179-123">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="0e179-124">创建项目</span><span class="sxs-lookup"><span data-stu-id="0e179-124">Creating the Project</span></span>  
 <span data-ttu-id="0e179-125">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="0e179-125">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="0e179-126">创建项目</span><span class="sxs-lookup"><span data-stu-id="0e179-126">To create the project</span></span>  
  
1.  <span data-ttu-id="0e179-127">创建**Windows 应用程序**项目称为`LayoutExample`。</span><span class="sxs-lookup"><span data-stu-id="0e179-127">Create a **Windows Application** project called `LayoutExample`.</span></span> <span data-ttu-id="0e179-128">有关详细信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="0e179-128">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) .</span></span>  
  
2.  <span data-ttu-id="0e179-129">选择的窗体中**Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="0e179-129">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="setting-margins-for-your-controls"></a><span data-ttu-id="0e179-130">边距设置为你的控件</span><span class="sxs-lookup"><span data-stu-id="0e179-130">Setting Margins for Your Controls</span></span>  
 <span data-ttu-id="0e179-131">可以使用你控件之间设置的默认距离<xref:System.Windows.Forms.Control.Margin%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0e179-131">You can set the default distance between your controls using the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="0e179-132">当你将控件移到另一个控件足够近，您将看到对齐线显示两个控件的边距。</span><span class="sxs-lookup"><span data-stu-id="0e179-132">When you move a control close enough to another control, you will see a snapline that shows the margins for the two controls.</span></span> <span data-ttu-id="0e179-133">要移动的控件也将对齐到由边距定义的距离。</span><span class="sxs-lookup"><span data-stu-id="0e179-133">The control you are moving will also snap to the distance defined by the margins.</span></span>  
  
#### <a name="to-arrange-controls-on-your-form-using-the-margin-property"></a><span data-ttu-id="0e179-134">若要在你使用的是 Margin 属性的窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="0e179-134">To arrange controls on your form using the Margin property</span></span>  
  
1.  <span data-ttu-id="0e179-135">将两个<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="0e179-135">Drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="0e179-136">选择其中一个<xref:System.Windows.Forms.Button>控制并将其移近另一个，直到它们几乎接触。</span><span class="sxs-lookup"><span data-stu-id="0e179-136">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span>  
  
     <span data-ttu-id="0e179-137">观察它们之间的对齐线。</span><span class="sxs-lookup"><span data-stu-id="0e179-137">Observe the snapline that appears between them.</span></span> <span data-ttu-id="0e179-138">此距离为两个控件的总和<xref:System.Windows.Forms.Control.Margin%2A>值。</span><span class="sxs-lookup"><span data-stu-id="0e179-138">This distance is the sum of the two controls' <xref:System.Windows.Forms.Control.Margin%2A> values.</span></span> <span data-ttu-id="0e179-139">要移动的控件对齐到此距离。</span><span class="sxs-lookup"><span data-stu-id="0e179-139">The control you are moving snaps to this distance.</span></span> <span data-ttu-id="0e179-140">有关详细信息，请参阅[演练： 在 Windows 窗体使用对齐线上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="0e179-140">For details, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
3.  <span data-ttu-id="0e179-141">更改<xref:System.Windows.Forms.Control.Margin%2A>属性之一的展开控件<xref:System.Windows.Forms.Control.Margin%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设置为 20。</span><span class="sxs-lookup"><span data-stu-id="0e179-141">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of one of the controls by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 20.</span></span>  
  
4.  <span data-ttu-id="0e179-142">选择其中一个<xref:System.Windows.Forms.Button>控制并将其移接近另。</span><span class="sxs-lookup"><span data-stu-id="0e179-142">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other.</span></span>  
  
     <span data-ttu-id="0e179-143">对齐线定义边距值的总和是更长，并且该控件从其他控件对齐更远的距离。</span><span class="sxs-lookup"><span data-stu-id="0e179-143">The snapline defining the sum of the margin values is longer and that the control snaps to a greater distance from the other control.</span></span>  
  
5.  <span data-ttu-id="0e179-144">更改<xref:System.Windows.Forms.Control.Margin%2A>通过展开所选控件的属性<xref:System.Windows.Forms.Control.Margin%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.Top%2A>属性设置为 5。</span><span class="sxs-lookup"><span data-stu-id="0e179-144">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of the selected control by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.Top%2A> property to 5.</span></span>  
  
6.  <span data-ttu-id="0e179-145">移动到其他控件下方所选的控件并观察对齐线更短。</span><span class="sxs-lookup"><span data-stu-id="0e179-145">Move the selected control below the other control and observe that the snapline is shorter.</span></span> <span data-ttu-id="0e179-146">将所选的控件移动到另一个控件的左侧，并观察对齐线将保留在步骤 4 中观测的值。</span><span class="sxs-lookup"><span data-stu-id="0e179-146">Move the selected control to the left of the other control and observe that the snapline retains the value observed in step 4.</span></span>  
  
7.  <span data-ttu-id="0e179-147">您可以将每个的方面<xref:System.Windows.Forms.Control.Margin%2A>属性， <xref:System.Windows.Forms.Padding.Left%2A>， <xref:System.Windows.Forms.Padding.Top%2A>， <xref:System.Windows.Forms.Padding.Right%2A>， <xref:System.Windows.Forms.Padding.Bottom%2A>、 到不同的值，或者让你可以将它们设置为使用相同的值的所有<xref:System.Windows.Forms.Padding.All%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0e179-147">You can set each of the aspects of the <xref:System.Windows.Forms.Control.Margin%2A> property, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, to different values, or you can set them all to the same value with the <xref:System.Windows.Forms.Padding.All%2A> property.</span></span>  
  
## <a name="setting-padding-for-your-controls"></a><span data-ttu-id="0e179-148">设置控件的填充</span><span class="sxs-lookup"><span data-stu-id="0e179-148">Setting Padding for Your Controls</span></span>  
 <span data-ttu-id="0e179-149">若要实现你的应用程序所需的精确布局，你的控件通常将包含子控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-149">To achieve the precise layout required for your application, your controls will often contain child controls.</span></span> <span data-ttu-id="0e179-150">如果你想要指定父控件的边框的子控件的边框接近，使用父控件的<xref:System.Windows.Forms.Control.Padding%2A>结合子控件的属性<xref:System.Windows.Forms.Control.Margin%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0e179-150">When you want to specify the proximity of the child control's border to the parent control's border, use the parent control's <xref:System.Windows.Forms.Control.Padding%2A> property in conjunction with the child control's <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="0e179-151"><xref:System.Windows.Forms.Control.Padding%2A>属性还用于控制接近于控件的内容 (例如，<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Text%2A>属性) 为其边界。</span><span class="sxs-lookup"><span data-stu-id="0e179-151">The <xref:System.Windows.Forms.Control.Padding%2A> property is also used to control the proximity of a control's content (for example, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property) to its borders.</span></span>  
  
#### <a name="to-arrange-controls-on-your-form-using-padding"></a><span data-ttu-id="0e179-152">若要在使用填充窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="0e179-152">To arrange controls on your form using padding</span></span>  
  
1.  <span data-ttu-id="0e179-153">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="0e179-153">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="0e179-154">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0e179-154">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="0e179-155">更改<xref:System.Windows.Forms.Control.Padding%2A>属性通过展开<xref:System.Windows.Forms.Control.Padding%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设置为 5。</span><span class="sxs-lookup"><span data-stu-id="0e179-155">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 5.</span></span>  
  
     <span data-ttu-id="0e179-156">控件扩展以提供新的填充的空间。</span><span class="sxs-lookup"><span data-stu-id="0e179-156">The control expands to provide room for the new padding.</span></span>  
  
4.  <span data-ttu-id="0e179-157">拖动<xref:System.Windows.Forms.GroupBox>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="0e179-157">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="0e179-158">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-158">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="0e179-159">位置<xref:System.Windows.Forms.Button>控制以便与的右下角对齐<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-159">Position the <xref:System.Windows.Forms.Button> control so it is flush with the lower-right corner of the <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
     <span data-ttu-id="0e179-160">观察显示为对齐线<xref:System.Windows.Forms.Button>控件接近下边缘和右边框<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-160">Observe the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="0e179-161">这些对齐线对应于<xref:System.Windows.Forms.Control.Margin%2A>属性<xref:System.Windows.Forms.Button>。</span><span class="sxs-lookup"><span data-stu-id="0e179-161">These snaplines correspond to the <xref:System.Windows.Forms.Control.Margin%2A> property of the <xref:System.Windows.Forms.Button>.</span></span>  
  
5.  <span data-ttu-id="0e179-162">更改<xref:System.Windows.Forms.GroupBox>控件的<xref:System.Windows.Forms.Control.Padding%2A>属性通过展开<xref:System.Windows.Forms.Control.Padding%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设置为 20。</span><span class="sxs-lookup"><span data-stu-id="0e179-162">Change the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 20.</span></span>  
  
6.  <span data-ttu-id="0e179-163">选择<xref:System.Windows.Forms.Button>控件中<xref:System.Windows.Forms.GroupBox>控制并将其移向的中心<xref:System.Windows.Forms.GroupBox>。</span><span class="sxs-lookup"><span data-stu-id="0e179-163">Select the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and move it toward the center of the <xref:System.Windows.Forms.GroupBox>.</span></span>  
  
     <span data-ttu-id="0e179-164">对齐线在更大的距离出现与的边框<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-164">The snaplines appear at a greater distance from the borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="0e179-165">此距离之<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Margin%2A>属性和<xref:System.Windows.Forms.GroupBox>控件的<xref:System.Windows.Forms.Control.Padding%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0e179-165">This distance is the sum of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property and the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>  
  
## <a name="automatically-sizing-your-controls"></a><span data-ttu-id="0e179-166">自动调整控件大小</span><span class="sxs-lookup"><span data-stu-id="0e179-166">Automatically Sizing Your Controls</span></span>  
 <span data-ttu-id="0e179-167">在某些应用程序，控件的大小将不能相同在运行时在设计时那样。</span><span class="sxs-lookup"><span data-stu-id="0e179-167">In some applications, the size of a control will not be the same at run time as it was at design time.</span></span> <span data-ttu-id="0e179-168">文本<xref:System.Windows.Forms.Button>控件，例如，可能来自一个数据库，并将不能预先知道其长度。</span><span class="sxs-lookup"><span data-stu-id="0e179-168">The text of a <xref:System.Windows.Forms.Button> control, for example, may be taken from a database, and its length will not be known in advance.</span></span>  
  
 <span data-ttu-id="0e179-169">当<xref:System.Windows.Forms.Control.AutoSize%2A>属性设置为`true`，控件将调整自身大小对其内容。</span><span class="sxs-lookup"><span data-stu-id="0e179-169">When the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `true`, the control will size itself to its content.</span></span> <span data-ttu-id="0e179-170">有关详细信息，请参阅[AutoSize 属性概述](../../../../docs/framework/winforms/controls/autosize-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0e179-170">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
#### <a name="to-arrange-controls-on-your-form-using-the-autosize-property"></a><span data-ttu-id="0e179-171">若要在你使用 AutoSize 属性的窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="0e179-171">To arrange controls on your form using the AutoSize property</span></span>  
  
1.  <span data-ttu-id="0e179-172">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="0e179-172">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="0e179-173">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0e179-173">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="0e179-174">更改<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Text%2A>属性设置为"**针对其 Text 属性的长字符串，该按钮才**。"</span><span class="sxs-lookup"><span data-stu-id="0e179-174">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property**."</span></span>  
  
     <span data-ttu-id="0e179-175">如果提交了更改，<xref:System.Windows.Forms.Button>控件自行调整大小以容纳新的文本。</span><span class="sxs-lookup"><span data-stu-id="0e179-175">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself to fit the new text.</span></span>  
  
4.  <span data-ttu-id="0e179-176">将另一个<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="0e179-176">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
5.  <span data-ttu-id="0e179-177">更改<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Text%2A>属性设置为"**针对其 Text 属性的长字符串，该按钮才。**"</span><span class="sxs-lookup"><span data-stu-id="0e179-177">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>  
  
     <span data-ttu-id="0e179-178">如果提交了更改，<xref:System.Windows.Forms.Button>控件不调整大小本身，并且文本剪切的控件的右边缘。</span><span class="sxs-lookup"><span data-stu-id="0e179-178">When you commit the change, the <xref:System.Windows.Forms.Button> control does not resize itself, and the text is clipped by the right edge of the control.</span></span>  
  
6.  <span data-ttu-id="0e179-179">更改<xref:System.Windows.Forms.Control.Padding%2A>属性通过展开<xref:System.Windows.Forms.Control.Padding%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设置为 5。</span><span class="sxs-lookup"><span data-stu-id="0e179-179">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 5.</span></span>  
  
     <span data-ttu-id="0e179-180">所有四个边情况下，在控件的内部文本将被剪裁。</span><span class="sxs-lookup"><span data-stu-id="0e179-180">The text in the control's interior is clipped on all four sides.</span></span>  
  
7.  <span data-ttu-id="0e179-181">更改<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.AutoSize%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="0e179-181">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="0e179-182"><xref:System.Windows.Forms.Button>控件自行调整大小以容纳整个字符串。</span><span class="sxs-lookup"><span data-stu-id="0e179-182">The <xref:System.Windows.Forms.Button> control resizes itself to encompass the entire string.</span></span> <span data-ttu-id="0e179-183">此外，还将填充添加将文本环绕导致<xref:System.Windows.Forms.Button>控件展开所有四个方向。</span><span class="sxs-lookup"><span data-stu-id="0e179-183">Also, padding has been added around the text, causing the <xref:System.Windows.Forms.Button> control to expand in all four directions.</span></span>  
  
8.  <span data-ttu-id="0e179-184">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="0e179-184">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="0e179-185">将其置于窗体右下角附近。</span><span class="sxs-lookup"><span data-stu-id="0e179-185">Position it near the lower-right corner of the form.</span></span>  
  
9. <span data-ttu-id="0e179-186">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0e179-186">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
10. <span data-ttu-id="0e179-187">设置<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性<xref:System.Windows.Forms.AnchorStyles.Right>， <xref:System.Windows.Forms.AnchorStyles.Bottom>。</span><span class="sxs-lookup"><span data-stu-id="0e179-187">Set the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.</span></span>  
  
11. <span data-ttu-id="0e179-188">更改<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Text%2A>属性设置为"**针对其 Text 属性的长字符串，该按钮才。**"</span><span class="sxs-lookup"><span data-stu-id="0e179-188">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>  
  
     <span data-ttu-id="0e179-189">如果提交了更改，<xref:System.Windows.Forms.Button>控件在调整自身大小的左侧。</span><span class="sxs-lookup"><span data-stu-id="0e179-189">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself toward the left.</span></span> <span data-ttu-id="0e179-190">一般情况下，自动调整大小将增加相反的方向中的控件的大小及其<xref:System.Windows.Forms.Control.Anchor%2A>属性设置。</span><span class="sxs-lookup"><span data-stu-id="0e179-190">In general, automatic sizing will increase the size of a control in the direction opposite its <xref:System.Windows.Forms.Control.Anchor%2A> property setting.</span></span>  
  
## <a name="autosize-and-autosizemode-properties"></a><span data-ttu-id="0e179-191">AutoSize 和 AutoSizeMode 属性</span><span class="sxs-lookup"><span data-stu-id="0e179-191">AutoSize and AutoSizeMode Properties</span></span>  
 <span data-ttu-id="0e179-192">某些控件支持`AutoSizeMode`属性，这为你提供更好地控制细化控件自动调整大小行为。</span><span class="sxs-lookup"><span data-stu-id="0e179-192">Some controls support the `AutoSizeMode` property, which gives you more fine-grained control over the automatic sizing behavior of a control.</span></span>  
  
#### <a name="to-use-the-autosizemode-property"></a><span data-ttu-id="0e179-193">若要使用 AutoSizeMode 属性</span><span class="sxs-lookup"><span data-stu-id="0e179-193">To use the AutoSizeMode property</span></span>  
  
1.  <span data-ttu-id="0e179-194">拖动<xref:System.Windows.Forms.Panel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="0e179-194">Drag a <xref:System.Windows.Forms.Panel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="0e179-195">设置的值<xref:System.Windows.Forms.Panel>控件的<xref:System.Windows.Forms.Control.AutoSize%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="0e179-195">Set the value of the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="0e179-196">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到<xref:System.Windows.Forms.Panel>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-196">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
4.  <span data-ttu-id="0e179-197">位置<xref:System.Windows.Forms.Button>控件的右下角附近<xref:System.Windows.Forms.Panel>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-197">Place the <xref:System.Windows.Forms.Button> control near the lower-right corner of the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
5.  <span data-ttu-id="0e179-198">选择<xref:System.Windows.Forms.Panel>控件并抓住右下角尺寸控点。</span><span class="sxs-lookup"><span data-stu-id="0e179-198">Select the <xref:System.Windows.Forms.Panel> control and grab the lower-right sizing handle.</span></span> <span data-ttu-id="0e179-199">调整大小<xref:System.Windows.Forms.Panel>控件，使其更大、 更小。</span><span class="sxs-lookup"><span data-stu-id="0e179-199">Resize the <xref:System.Windows.Forms.Panel> control to be larger and smaller.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0e179-200">你可以自由地调整大小<xref:System.Windows.Forms.Panel>控件，但你无法调整其大小小于的位置<xref:System.Windows.Forms.Button>控件的右下角。</span><span class="sxs-lookup"><span data-stu-id="0e179-200">You can freely resize the <xref:System.Windows.Forms.Panel> control, but you cannot size it smaller than the position of the <xref:System.Windows.Forms.Button> control's lower-right corner.</span></span> <span data-ttu-id="0e179-201">此行为的默认值由指定`AutoSizeMode`属性，它是<xref:System.Windows.Forms.AutoSizeMode.GrowOnly>。</span><span class="sxs-lookup"><span data-stu-id="0e179-201">This behavior is specified by the default value of the `AutoSizeMode` property, which is <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.</span></span>  
  
6.  <span data-ttu-id="0e179-202">设置的值<xref:System.Windows.Forms.Panel>控件的`AutoSizeMode`属性<xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>。</span><span class="sxs-lookup"><span data-stu-id="0e179-202">Set the value of the <xref:System.Windows.Forms.Panel> control's `AutoSizeMode` property to <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.</span></span>  
  
     <span data-ttu-id="0e179-203"><xref:System.Windows.Forms.Panel>控件自行调整大小以环绕<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-203">The <xref:System.Windows.Forms.Panel> control sizes itself to surround the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="0e179-204">不能调整<xref:System.Windows.Forms.Panel>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-204">You cannot resize the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
7.  <span data-ttu-id="0e179-205">拖动<xref:System.Windows.Forms.Button>朝着的左上角的控件<xref:System.Windows.Forms.Panel>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-205">Drag the <xref:System.Windows.Forms.Button> control toward the upper-left corner of the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
     <span data-ttu-id="0e179-206"><xref:System.Windows.Forms.Panel>控件的大小调整为<xref:System.Windows.Forms.Button>控件的新位置。</span><span class="sxs-lookup"><span data-stu-id="0e179-206">The <xref:System.Windows.Forms.Panel> control resizes to the <xref:System.Windows.Forms.Button> control's new position.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0e179-207">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0e179-207">Next Steps</span></span>  
 <span data-ttu-id="0e179-208">有许多其他布局功能，用于在 Windows 窗体应用程序排列控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-208">There are many other layout features for arranging controls in your Windows Forms applications.</span></span> <span data-ttu-id="0e179-209">下面是可能会尝试某些组合：</span><span class="sxs-lookup"><span data-stu-id="0e179-209">Here are some combinations you might try:</span></span>  
  
-   <span data-ttu-id="0e179-210">生成窗体使用<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-210">Build a form using a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="0e179-211">有关详细信息，请参阅[演练： 在 Windows 窗体使用 TableLayoutPanel 上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="0e179-211">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span> <span data-ttu-id="0e179-212">请尝试更改的值<xref:System.Windows.Forms.TableLayoutPanel>控件的<xref:System.Windows.Forms.Control.Padding%2A>属性，以及<xref:System.Windows.Forms.Control.Margin%2A>及其子控件上的属性。</span><span class="sxs-lookup"><span data-stu-id="0e179-212">Try changing the values of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.Control.Padding%2A> property, as well as the <xref:System.Windows.Forms.Control.Margin%2A> property on its child controls.</span></span>  
  
-   <span data-ttu-id="0e179-213">请尝试相同的试验使用<xref:System.Windows.Forms.FlowLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-213">Try the same experiment using a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="0e179-214">有关详细信息，请参阅[演练： 在 Windows 窗体使用 FlowLayoutPanel 上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="0e179-214">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>  
  
-   <span data-ttu-id="0e179-215">停靠子控件在试验<xref:System.Windows.Forms.Panel>控件。</span><span class="sxs-lookup"><span data-stu-id="0e179-215">Experiment with docking child controls in a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="0e179-216"><xref:System.Windows.Forms.Control.Padding%2A>属性是的更多常规实现<xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>属性，并且可以满足自己这种情况，通过将子控件放入<xref:System.Windows.Forms.Panel>控件并设置子控件的<xref:System.Windows.Forms.Control.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="0e179-216">The <xref:System.Windows.Forms.Control.Padding%2A> property is a more general realization of the <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> property, and you can satisfy yourself that this is the case by putting a child control in a <xref:System.Windows.Forms.Panel> control and setting the child control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="0e179-217">设置<xref:System.Windows.Forms.Panel>控件的<xref:System.Windows.Forms.Control.Padding%2A>到各种值并记下影响的属性。</span><span class="sxs-lookup"><span data-stu-id="0e179-217">Set the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.Padding%2A> property to various values and note the effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e179-218">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e179-218">See Also</span></span>  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 [<span data-ttu-id="0e179-219">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="0e179-219">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="0e179-220">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="0e179-220">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="0e179-221">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="0e179-221">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="0e179-222">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="0e179-222">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
