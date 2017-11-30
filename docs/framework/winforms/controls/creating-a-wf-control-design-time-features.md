---
title: "演练：创建一个利用 Visual Studio 设计时功能的 Windows 窗体控件"
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
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
caps.latest.revision: "46"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ba195656363b15407aed6a4da0ab804421a3d964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a><span data-ttu-id="02bcb-102">演练：创建一个利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-102">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>
<span data-ttu-id="02bcb-103">自定义控件的设计时体验可增强通过创作一个关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="02bcb-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>  
  
 <span data-ttu-id="02bcb-104">本演练阐释了如何创建自定义设计器中的为自定义控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-104">This walkthrough illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="02bcb-105">将实现`MarqueeControl`类型和一个关联的设计器类、 调用`MarqueeControlRootDesigner`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-105">You will implement a `MarqueeControl` type and an associated designer class, called `MarqueeControlRootDesigner`.</span></span>  
  
 <span data-ttu-id="02bcb-106">`MarqueeControl`类型实现类似于影院选框，具有动画的灯和闪烁的文本显示。</span><span class="sxs-lookup"><span data-stu-id="02bcb-106">The `MarqueeControl` type implements a display similar to a theater marquee, with animated lights and flashing text.</span></span>  
  
 <span data-ttu-id="02bcb-107">此控件的设计器与要提供自定义设计时体验的设计环境进行交互。</span><span class="sxs-lookup"><span data-stu-id="02bcb-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="02bcb-108">使用自定义设计器中，你可以将组合自定义`MarqueeControl`实施了动画的灯和闪烁文本以多种的组合。</span><span class="sxs-lookup"><span data-stu-id="02bcb-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="02bcb-109">你可以使用像任何其他 Windows 窗体控件的窗体上组合的控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>  
  
 <span data-ttu-id="02bcb-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="02bcb-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="02bcb-111">创建项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-111">Creating the Project</span></span>  
  
-   <span data-ttu-id="02bcb-112">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-112">Creating a Control Library Project</span></span>  
  
-   <span data-ttu-id="02bcb-113">引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-113">Referencing the Custom Control Project</span></span>  
  
-   <span data-ttu-id="02bcb-114">定义自定义控件和其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="02bcb-114">Defining a Custom Control and Its Custom Designer</span></span>  
  
-   <span data-ttu-id="02bcb-115">创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="02bcb-115">Creating an Instance of Your Custom Control</span></span>  
  
-   <span data-ttu-id="02bcb-116">设置项目以便进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="02bcb-116">Setting Up the Project for Design-Time Debugging</span></span>  
  
-   <span data-ttu-id="02bcb-117">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-117">Implementing Your Custom Control</span></span>  
  
-   <span data-ttu-id="02bcb-118">为自定义控件创建子控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-118">Creating a Child Control for Your Custom Control</span></span>  
  
-   <span data-ttu-id="02bcb-119">创建放子控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-119">Create the MarqueeBorder Child Control</span></span>  
  
-   <span data-ttu-id="02bcb-120">创建自定义设计器以隐藏和筛选器属性</span><span class="sxs-lookup"><span data-stu-id="02bcb-120">Creating a Custom Designer to Shadow and Filter Properties</span></span>  
  
-   <span data-ttu-id="02bcb-121">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="02bcb-121">Handling Component Changes</span></span>  
  
-   <span data-ttu-id="02bcb-122">将设计器谓词添加到你的自定义设计器</span><span class="sxs-lookup"><span data-stu-id="02bcb-122">Adding Designer Verbs to your Custom Designer</span></span>  
  
-   <span data-ttu-id="02bcb-123">创建自定义 UITypeEditor</span><span class="sxs-lookup"><span data-stu-id="02bcb-123">Creating a Custom UITypeEditor</span></span>  
  
-   <span data-ttu-id="02bcb-124">在设计器中测试自定义控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-124">Testing your Custom Control in the Designer</span></span>  
  
 <span data-ttu-id="02bcb-125">完成后，自定义控件将看起来类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="02bcb-125">When you are finished, your custom control will look something like the following:</span></span>  
  
 <span data-ttu-id="02bcb-126">![可能的 MarqueeControl 排列](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "器")</span><span class="sxs-lookup"><span data-stu-id="02bcb-126">![A possible MarqueeControl arrangement](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")</span></span>  
  
 <span data-ttu-id="02bcb-127">有关完整代码列表，请参阅[如何： 创建 Windows 窗体控件，采用利用的设计时功能](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-127">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02bcb-128">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="02bcb-128">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="02bcb-129">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="02bcb-129">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="02bcb-130">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-130">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="02bcb-131">先决条件</span><span class="sxs-lookup"><span data-stu-id="02bcb-131">Prerequisites</span></span>  
 <span data-ttu-id="02bcb-132">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="02bcb-132">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="02bcb-133">若要能够创建和运行 Windows 窗体应用程序项目的计算机上安装了 Visual Studio 的足够权限。</span><span class="sxs-lookup"><span data-stu-id="02bcb-133">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="02bcb-134">创建项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-134">Creating the Project</span></span>  
 <span data-ttu-id="02bcb-135">第一步是创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-135">The first step is to create the application project.</span></span> <span data-ttu-id="02bcb-136">此项目将用于生成承载自定义控件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="02bcb-136">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="02bcb-137">创建项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-137">To create the project</span></span>  
  
-   <span data-ttu-id="02bcb-138">创建一个名为"MarqueeControlTest。"的 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-138">Create a Windows Forms Application project called "MarqueeControlTest."</span></span> <span data-ttu-id="02bcb-139">有关详细信息，请参阅 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-139">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="02bcb-140">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-140">Creating a Control Library Project</span></span>  
 <span data-ttu-id="02bcb-141">下一步是创建控件库项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-141">The next step is to create the control library project.</span></span> <span data-ttu-id="02bcb-142">你将创建一个新的自定义控件和其相应的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="02bcb-142">You will create a new custom control and its corresponding custom designer.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="02bcb-143">若要创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-143">To create the control library project</span></span>  
  
1.  <span data-ttu-id="02bcb-144">将 Windows 窗体控件库项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="02bcb-144">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="02bcb-145">将项目"MarqueeControlLibrary。"</span><span class="sxs-lookup"><span data-stu-id="02bcb-145">Name the project "MarqueeControlLibrary."</span></span>  
  
2.  <span data-ttu-id="02bcb-146">使用**解决方案资源管理器**，通过删除名为了"UserControl1.cs"或"UserControl1.vb"，具体取决于所用语言的源文件来删除项目的默认控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-146">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span> <span data-ttu-id="02bcb-147">有关详细信息，请参阅[NIB： 如何： 删除、 删除和排除项](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-147">For more information, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
3.  <span data-ttu-id="02bcb-148">添加新<xref:System.Windows.Forms.UserControl>项以`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-148">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="02bcb-149">为新的源文件提供基本名称为"MarqueeControl。"</span><span class="sxs-lookup"><span data-stu-id="02bcb-149">Give the new source file a base name of "MarqueeControl."</span></span>  
  
4.  <span data-ttu-id="02bcb-150">使用**解决方案资源管理器**中, 创建一个新文件夹`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-150">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="02bcb-151">有关详细信息，请参阅[NIB： 如何： 添加新项目项](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-151">For more information, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="02bcb-152">将新文件夹命名为"设计"。</span><span class="sxs-lookup"><span data-stu-id="02bcb-152">Name the new folder "Design."</span></span>  
  
5.  <span data-ttu-id="02bcb-153">右键单击**设计**文件夹并添加新类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-153">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="02bcb-154">为源文件提供基本名称为"MarqueeControlRootDesigner。"</span><span class="sxs-lookup"><span data-stu-id="02bcb-154">Give the source file a base name of "MarqueeControlRootDesigner."</span></span>  
  
6.  <span data-ttu-id="02bcb-155">你将需要使用从 System.Design 的程序集中的类型，因此添加对此引用`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-155">You will need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02bcb-156">若要使用 System.Design 程序集，你的项目必须面向.NET Framework 中，而非.NET Framework 客户端配置文件的完整版本。</span><span class="sxs-lookup"><span data-stu-id="02bcb-156">To use the System.Design assembly, your project must target the full version of the .NET Framework, not the .NET Framework Client Profile.</span></span> <span data-ttu-id="02bcb-157">若要更改目标框架，请参阅[如何： 面向.NET Framework 版本](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-157">To change the target framework, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>  
  
## <a name="referencing-the-custom-control-project"></a><span data-ttu-id="02bcb-158">引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-158">Referencing the Custom Control Project</span></span>  
 <span data-ttu-id="02bcb-159">你将使用`MarqueeControlTest`项目来测试该自定义控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-159">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="02bcb-160">测试项目将意识到自定义控件添加到项目引用时`MarqueeControlLibrary`程序集。</span><span class="sxs-lookup"><span data-stu-id="02bcb-160">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>  
  
#### <a name="to-reference-the-custom-control-project"></a><span data-ttu-id="02bcb-161">若要引用该自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="02bcb-161">To reference the custom control project</span></span>  
  
-   <span data-ttu-id="02bcb-162">在`MarqueeControlTest`项目中，添加的项目引用`MarqueeControlLibrary`程序集。</span><span class="sxs-lookup"><span data-stu-id="02bcb-162">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="02bcb-163">请务必使用**项目**选项卡中**添加引用**对话框而不是引用`MarqueeControlLibrary`直接的程序集。</span><span class="sxs-lookup"><span data-stu-id="02bcb-163">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>  
  
## <a name="defining-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="02bcb-164">定义自定义控件和其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="02bcb-164">Defining a Custom Control and Its Custom Designer</span></span>  
 <span data-ttu-id="02bcb-165">自定义控件将派生自<xref:System.Windows.Forms.UserControl>类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-165">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="02bcb-166">这使控件，以包含其他控件，并且它能让你控制了大量的默认功能。</span><span class="sxs-lookup"><span data-stu-id="02bcb-166">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>  
  
 <span data-ttu-id="02bcb-167">自定义控件将具有关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="02bcb-167">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="02bcb-168">这样，你可以创建专门定制用于自定义控件的唯一设计体验。</span><span class="sxs-lookup"><span data-stu-id="02bcb-168">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>  
  
 <span data-ttu-id="02bcb-169">将控件与及其设计器关联使用<xref:System.ComponentModel.DesignerAttribute>类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-169">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="02bcb-170">因为你正在开发的自定义控件的整个设计时行为，自定义设计器将实现<xref:System.ComponentModel.Design.IRootDesigner>接口。</span><span class="sxs-lookup"><span data-stu-id="02bcb-170">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>  
  
#### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="02bcb-171">若要定义自定义控件和其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="02bcb-171">To define a custom control and its custom designer</span></span>  
  
1.  <span data-ttu-id="02bcb-172">打开`MarqueeControl`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-172">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="02bcb-173">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="02bcb-173">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  <span data-ttu-id="02bcb-174">添加<xref:System.ComponentModel.DesignerAttribute>到`MarqueeControl`类声明。</span><span class="sxs-lookup"><span data-stu-id="02bcb-174">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="02bcb-175">这将与及其设计器关联的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-175">This associates the custom control with its designer.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  <span data-ttu-id="02bcb-176">打开`MarqueeControlRootDesigner`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-176">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="02bcb-177">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="02bcb-177">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  <span data-ttu-id="02bcb-178">更改的声明`MarqueeControlRootDesigner`要从其继承<xref:System.Windows.Forms.Design.DocumentDesigner>类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-178">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="02bcb-179">应用<xref:System.ComponentModel.ToolboxItemFilterAttribute>指定与设计器之间的交互**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-179">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>  
  
     <span data-ttu-id="02bcb-180">**请注意**的定义`MarqueeControlRootDesigner`在调用"MarqueeControlLibrary.Design。"的命名空间括起来类</span><span class="sxs-lookup"><span data-stu-id="02bcb-180">**Note** The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called "MarqueeControlLibrary.Design."</span></span> <span data-ttu-id="02bcb-181">此声明将设计器中的特殊命名空间保留的设计相关的类型。</span><span class="sxs-lookup"><span data-stu-id="02bcb-181">This declaration places the designer in a special namespace reserved for design-related types.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  <span data-ttu-id="02bcb-182">定义的构造函数`MarqueeControlRootDesigner`类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-182">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="02bcb-183">插入<xref:System.Diagnostics.Trace.WriteLine%2A>构造函数正文中的语句。</span><span class="sxs-lookup"><span data-stu-id="02bcb-183">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="02bcb-184">这将很有用以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="02bcb-184">This will be useful for debugging purposes.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## <a name="creating-an-instance-of-your-custom-control"></a><span data-ttu-id="02bcb-185">创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="02bcb-185">Creating an Instance of Your Custom Control</span></span>  
 <span data-ttu-id="02bcb-186">若要观察的控件的自定义设计时行为，将放置在窗体上控件的实例`MarqueeControlTest`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-186">To observe the custom design-time behavior of your control, you will place an instance of your control on the form in `MarqueeControlTest` project.</span></span>  
  
#### <a name="to-create-an-instance-of-your-custom-control"></a><span data-ttu-id="02bcb-187">若要创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="02bcb-187">To create an instance of your custom control</span></span>  
  
1.  <span data-ttu-id="02bcb-188">添加新<xref:System.Windows.Forms.UserControl>项以`MarqueeControlTest`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-188">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="02bcb-189">为新的源文件提供基本名称为"器。"</span><span class="sxs-lookup"><span data-stu-id="02bcb-189">Give the new source file a base name of "DemoMarqueeControl."</span></span>  
  
2.  <span data-ttu-id="02bcb-190">打开`DemoMarqueeControl`文件中**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-190">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="02bcb-191">在文件的顶部，导入`MarqueeControlLibrary`命名空间：</span><span class="sxs-lookup"><span data-stu-id="02bcb-191">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  <span data-ttu-id="02bcb-192">更改的声明`DemoMarqueeControl`要从其继承`MarqueeControl`类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-192">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>  
  
2.  <span data-ttu-id="02bcb-193">生成项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-193">Build the project.</span></span>  
  
3.  <span data-ttu-id="02bcb-194">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-194">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="02bcb-195">查找**MarqueeControlTest 组件**选项卡中**工具箱**并将其打开。</span><span class="sxs-lookup"><span data-stu-id="02bcb-195">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="02bcb-196">拖动`DemoMarqueeControl`从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="02bcb-196">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>  
  
5.  <span data-ttu-id="02bcb-197">生成项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-197">Build the project.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="02bcb-198">设置项目以便进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="02bcb-198">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="02bcb-199">当你正在开发的自定义设计时体验时，它将需要调试控件和组件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-199">When you are developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="02bcb-200">没有一种简单的方法，以将你的项目设置为允许在设计时调试。</span><span class="sxs-lookup"><span data-stu-id="02bcb-200">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="02bcb-201">有关详细信息，请参阅[演练： 调试在设计时自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-201">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="02bcb-202">若要设置项目以便进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="02bcb-202">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="02bcb-203">右键单击`MarqueeControlLibrary`项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-203">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="02bcb-204">在"MarqueeControlLibrary 属性页"对话框中，选择**调试**页。</span><span class="sxs-lookup"><span data-stu-id="02bcb-204">In the "MarqueeControlLibrary Property Pages" dialog box, select the **Debug** page.</span></span>  
  
3.  <span data-ttu-id="02bcb-205">在**启动操作**部分中，选择**启动外部程序**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-205">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="02bcb-206">你将调试的单独实例的 Visual Studio 中，因此单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以浏览 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="02bcb-206">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="02bcb-207">可执行文件的名称是 devenv.exe，，如果你已安装到默认位置，其路径是 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe。</span><span class="sxs-lookup"><span data-stu-id="02bcb-207">The name of the executable file is devenv.exe, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
4.  <span data-ttu-id="02bcb-208">单击确定以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="02bcb-208">Click OK to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="02bcb-209">右键单击`MarqueeControlLibrary`项目，然后选择"设为启动项目"来启用此调试配置。</span><span class="sxs-lookup"><span data-stu-id="02bcb-209">Right-click the `MarqueeControlLibrary` project and select "Set as StartUp Project" to enable this debugging configuration.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="02bcb-210">检查点</span><span class="sxs-lookup"><span data-stu-id="02bcb-210">Checkpoint</span></span>  
 <span data-ttu-id="02bcb-211">现在你就可以调试自定义控件的设计时行为。</span><span class="sxs-lookup"><span data-stu-id="02bcb-211">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="02bcb-212">在你确定了正确设置调试环境，你将测试自定义控件和自定义设计器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="02bcb-212">Once you have determined that the debugging environment is set up correctly, you will test the association between the custom control and the custom designer.</span></span>  
  
#### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="02bcb-213">若要测试的调试环境和设计器关联</span><span class="sxs-lookup"><span data-stu-id="02bcb-213">To test the debugging environment and the designer association</span></span>  
  
1.  <span data-ttu-id="02bcb-214">打开`MarqueeControlRootDesigner`中的源文件**代码编辑器**并将断点放置在<xref:System.Diagnostics.Trace.WriteLine%2A>语句。</span><span class="sxs-lookup"><span data-stu-id="02bcb-214">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>  
  
2.  <span data-ttu-id="02bcb-215">按 F5 启动调试会话。</span><span class="sxs-lookup"><span data-stu-id="02bcb-215">Press F5 to start the debugging session.</span></span> <span data-ttu-id="02bcb-216">请注意，创建 Visual Studio 的新实例。</span><span class="sxs-lookup"><span data-stu-id="02bcb-216">Note that a new instance of Visual Studio is created.</span></span>  
  
3.  <span data-ttu-id="02bcb-217">在 Visual Studio 的新实例中，打开的"MarqueeControlTest"解决方案。</span><span class="sxs-lookup"><span data-stu-id="02bcb-217">In the new instance of Visual Studio, open the "MarqueeControlTest" solution.</span></span> <span data-ttu-id="02bcb-218">你可以轻松地找到解决方案，通过选择**最近项目**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="02bcb-218">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="02bcb-219">将列出"MarqueeControlTest.sln"解决方案文件，如最近使用的文件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-219">The "MarqueeControlTest.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="02bcb-220">打开`DemoMarqueeControl`设计器中。</span><span class="sxs-lookup"><span data-stu-id="02bcb-220">Open the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="02bcb-221">请注意，Visual Studio 的调试实例获取焦点执行在断点处停止。</span><span class="sxs-lookup"><span data-stu-id="02bcb-221">Note that the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="02bcb-222">按 F5 以继续调试会话。</span><span class="sxs-lookup"><span data-stu-id="02bcb-222">Press F5 to continue the debugging session.</span></span>  
  
 <span data-ttu-id="02bcb-223">此时，所有内容已准备好为你开发和调试自定义控件和其关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="02bcb-223">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="02bcb-224">本演练的剩余部分将专注于实现的控件和设计器功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="02bcb-224">The remainder of this walkthrough will concentrate on the details of implementing features of the control and the designer.</span></span>  
  
## <a name="implementing-your-custom-control"></a><span data-ttu-id="02bcb-225">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-225">Implementing Your Custom Control</span></span>  
 <span data-ttu-id="02bcb-226">`MarqueeControl`是<xref:System.Windows.Forms.UserControl>通过自定义很少。</span><span class="sxs-lookup"><span data-stu-id="02bcb-226">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="02bcb-227">它公开两个方法： `Start`，以启动字幕动画和`Stop`，是停止动画。</span><span class="sxs-lookup"><span data-stu-id="02bcb-227">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="02bcb-228">因为`MarqueeControl`包含子控件的实现`IMarqueeWidget`接口，`Start`和`Stop`枚举每个子控件和调用`StartMarquee`和`StopMarquee`方法，分别在每个子控件实现`IMarqueeWidget`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-228">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>  
  
 <span data-ttu-id="02bcb-229">外观`MarqueeBorder`和`MarqueeText`控件是依赖于布局，因此`MarqueeControl`重写<xref:System.Windows.Forms.Control.OnLayout%2A>方法，调用<xref:System.Windows.Forms.Control.PerformLayout%2A>此类型的子控件上。</span><span class="sxs-lookup"><span data-stu-id="02bcb-229">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>  
  
 <span data-ttu-id="02bcb-230">这是范围`MarqueeControl`自定义项。</span><span class="sxs-lookup"><span data-stu-id="02bcb-230">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="02bcb-231">运行时功能实现的`MarqueeBorder`和`MarqueeText`由实现控件和设计时功能`MarqueeBorderDesigner`和`MarqueeControlRootDesigner`类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-231">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>  
  
#### <a name="to-implement-your-custom-control"></a><span data-ttu-id="02bcb-232">若要实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-232">To implement your custom control</span></span>  
  
1.  <span data-ttu-id="02bcb-233">打开`MarqueeControl`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-233">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="02bcb-234">实现`Start`和`Stop`方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-234">Implement the `Start` and `Stop` methods.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  <span data-ttu-id="02bcb-235">重写 <xref:System.Windows.Forms.Control.OnLayout%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-235">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## <a name="creating-a-child-control-for-your-custom-control"></a><span data-ttu-id="02bcb-236">为自定义控件创建子控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-236">Creating a Child Control for Your Custom Control</span></span>  
 <span data-ttu-id="02bcb-237">`MarqueeControl`将承载两种类型的子控件：`MarqueeBorder`控件和`MarqueeText`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-237">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>  
  
-   <span data-ttu-id="02bcb-238">`MarqueeBorder`： 此控件绘制"lights"其边缘周围的边框。</span><span class="sxs-lookup"><span data-stu-id="02bcb-238">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="02bcb-239">灯 flash 在序列中，因此它们看起来围绕着边框移动。</span><span class="sxs-lookup"><span data-stu-id="02bcb-239">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="02bcb-240">由名为的属性控制从该处闪烁的速度`UpdatePeriod`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-240">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="02bcb-241">多个其他自定义属性确定控件的外观的其他方面。</span><span class="sxs-lookup"><span data-stu-id="02bcb-241">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="02bcb-242">两种方法，调用`StartMarquee`和`StopMarquee`，控制动画时启动和停止。</span><span class="sxs-lookup"><span data-stu-id="02bcb-242">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>  
  
-   <span data-ttu-id="02bcb-243">`MarqueeText`： 此控件绘制一个闪烁的字符串。</span><span class="sxs-lookup"><span data-stu-id="02bcb-243">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="02bcb-244">如`MarqueeBorder`控件，由控制文本的闪烁的速度`UpdatePeriod`属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-244">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="02bcb-245">`MarqueeText`控件还具有`StartMarquee`和`StopMarquee`共有方法`MarqueeBorder`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-245">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>  
  
 <span data-ttu-id="02bcb-246">在设计时，`MarqueeControlRootDesigner`允许这些两个控件类型添加到`MarqueeControl`采用任意组合。</span><span class="sxs-lookup"><span data-stu-id="02bcb-246">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>  
  
 <span data-ttu-id="02bcb-247">常见的两个控件的功能分解到一个接口，称为`IMarqueeWidget`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-247">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="02bcb-248">这允许`MarqueeControl`来发现任何选框相关子控件并为它们提供特殊处理。</span><span class="sxs-lookup"><span data-stu-id="02bcb-248">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>  
  
 <span data-ttu-id="02bcb-249">若要实现定期动画功能，你将使用<xref:System.ComponentModel.BackgroundWorker>对象从<xref:System.ComponentModel?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="02bcb-249">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="02bcb-250">你可以使用<xref:System.Windows.Forms.Timer>对象，但是在许多`IMarqueeWidget`对象是否存在后，单个 UI 线程可能会无法跟上动画。</span><span class="sxs-lookup"><span data-stu-id="02bcb-250">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>  
  
#### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="02bcb-251">若要创建自定义控件的子控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-251">To create a child control for your custom control</span></span>  
  
1.  <span data-ttu-id="02bcb-252">新类将项添加到`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-252">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="02bcb-253">为新的源文件提供基本名称为"IMarqueeWidget。"</span><span class="sxs-lookup"><span data-stu-id="02bcb-253">Give the new source file a base name of "IMarqueeWidget."</span></span>  
  
2.  <span data-ttu-id="02bcb-254">打开`IMarqueeWidget`中的源文件**代码编辑器**和更改从声明`class`到`interface`:</span><span class="sxs-lookup"><span data-stu-id="02bcb-254">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  <span data-ttu-id="02bcb-255">以下代码添加到`IMarqueeWidget`接口以公开两个方法和操作字幕动画的属性：</span><span class="sxs-lookup"><span data-stu-id="02bcb-255">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  <span data-ttu-id="02bcb-256">添加新**自定义控件**项以`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-256">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="02bcb-257">为新的源文件提供基本名称为"显示"。</span><span class="sxs-lookup"><span data-stu-id="02bcb-257">Give the new source file a base name of "MarqueeText."</span></span>  
  
5.  <span data-ttu-id="02bcb-258">拖动<xref:System.ComponentModel.BackgroundWorker>组件从**工具箱**拖到你`MarqueeText`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-258">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="02bcb-259">此组件将允许`MarqueeText`控制以异步方式将自行更新。</span><span class="sxs-lookup"><span data-stu-id="02bcb-259">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>  
  
6.  <span data-ttu-id="02bcb-260">在属性窗口中，设置<xref:System.ComponentModel.BackgroundWorker>组件的`WorkerReportsProgess`和<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-260">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgess` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="02bcb-261">这些设置允许<xref:System.ComponentModel.BackgroundWorker>组件定期引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件并用于取消异步更新。</span><span class="sxs-lookup"><span data-stu-id="02bcb-261">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="02bcb-262">有关详细信息，请参阅[BackgroundWorker 组件](../../../../docs/framework/winforms/controls/backgroundworker-component.md)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-262">For more information, see [BackgroundWorker Component](../../../../docs/framework/winforms/controls/backgroundworker-component.md).</span></span>  
  
7.  <span data-ttu-id="02bcb-263">打开`MarqueeText`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-263">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="02bcb-264">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="02bcb-264">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  <span data-ttu-id="02bcb-265">更改的声明`MarqueeText`要从其继承<xref:System.Windows.Forms.Label>并实现`IMarqueeWidget`接口：</span><span class="sxs-lookup"><span data-stu-id="02bcb-265">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. <span data-ttu-id="02bcb-266">声明实例变量对应公开的属性，并对其初始化构造函数中。</span><span class="sxs-lookup"><span data-stu-id="02bcb-266">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="02bcb-267">`isLit`字段确定是否在指定的颜色绘制文本`LightColor`属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-267">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. <span data-ttu-id="02bcb-268">实现 `IMarqueeWidget` 接口。</span><span class="sxs-lookup"><span data-stu-id="02bcb-268">Implement the `IMarqueeWidget` interface.</span></span>  
  
     <span data-ttu-id="02bcb-269">`StartMarquee`和`StopMarquee`方法调用<xref:System.ComponentModel.BackgroundWorker>组件的<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>和<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>方法来启动和停止动画。</span><span class="sxs-lookup"><span data-stu-id="02bcb-269">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>  
  
     <span data-ttu-id="02bcb-270"><xref:System.ComponentModel.CategoryAttribute.Category%2A>和<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>特性应用到`UpdatePeriod`属性，以便它将显示在属性窗口调用"选框。"自定义部分</span><span class="sxs-lookup"><span data-stu-id="02bcb-270">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. <span data-ttu-id="02bcb-271">实现属性访问器。</span><span class="sxs-lookup"><span data-stu-id="02bcb-271">Implement the property accessors.</span></span> <span data-ttu-id="02bcb-272">将公开给客户端的两个属性：`LightColor`和`DarkColor`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-272">You will expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="02bcb-273"><xref:System.ComponentModel.CategoryAttribute.Category%2A>和<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>特性应用到这些属性，因此这些属性将显示在属性窗口调用"选框。"的自定义部分</span><span class="sxs-lookup"><span data-stu-id="02bcb-273">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. <span data-ttu-id="02bcb-274">实现的处理程序<xref:System.ComponentModel.BackgroundWorker>组件的<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-274">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
     <span data-ttu-id="02bcb-275"><xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序休眠由指定的毫秒数`UpdatePeriod`然后引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件，直到你的代码通过调用停止动画<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-275">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>  
  
     <span data-ttu-id="02bcb-276"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序之间切换文本其浅色和深色状态，以提供闪烁的外观。</span><span class="sxs-lookup"><span data-stu-id="02bcb-276">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. <span data-ttu-id="02bcb-277">重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法，以使动画。</span><span class="sxs-lookup"><span data-stu-id="02bcb-277">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. <span data-ttu-id="02bcb-278">按 F6 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="02bcb-278">Press F6 to build the solution.</span></span>  
  
## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="02bcb-279">创建放子控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-279">Create the MarqueeBorder Child Control</span></span>  
 <span data-ttu-id="02bcb-280">`MarqueeBorder`控件是比稍许复杂`MarqueeText`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-280">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="02bcb-281">它还具有更多属性和中的动画<xref:System.Windows.Forms.Control.OnPaint%2A>方法是更多地涉及。</span><span class="sxs-lookup"><span data-stu-id="02bcb-281">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="02bcb-282">原则上，它是非常类似于`MarqueeText`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-282">In principle, it is quite similar to the `MarqueeText` control.</span></span>  
  
 <span data-ttu-id="02bcb-283">因为`MarqueeBorder`控件可以具有子控件，它必须要注意的<xref:System.Windows.Forms.Control.Layout>事件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-283">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>  
  
#### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="02bcb-284">若要创建放控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-284">To create the MarqueeBorder control</span></span>  
  
1.  <span data-ttu-id="02bcb-285">添加新**自定义控件**项以`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-285">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="02bcb-286">为新的源文件提供基本名称为"放。"</span><span class="sxs-lookup"><span data-stu-id="02bcb-286">Give the new source file a base name of "MarqueeBorder."</span></span>  
  
2.  <span data-ttu-id="02bcb-287">拖动<xref:System.ComponentModel.BackgroundWorker>组件从**工具箱**拖到你`MarqueeBorder`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-287">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="02bcb-288">此组件将允许`MarqueeBorder`控制以异步方式将自行更新。</span><span class="sxs-lookup"><span data-stu-id="02bcb-288">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>  
  
3.  <span data-ttu-id="02bcb-289">在属性窗口中，设置<xref:System.ComponentModel.BackgroundWorker>组件的`WorkerReportsProgess`和<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-289">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgess` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="02bcb-290">这些设置允许<xref:System.ComponentModel.BackgroundWorker>组件定期引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件并用于取消异步更新。</span><span class="sxs-lookup"><span data-stu-id="02bcb-290">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="02bcb-291">有关详细信息，请参阅[BackgroundWorker 组件](../../../../docs/framework/winforms/controls/backgroundworker-component.md)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-291">For more information, see [BackgroundWorker Component](../../../../docs/framework/winforms/controls/backgroundworker-component.md).</span></span>  
  
4.  <span data-ttu-id="02bcb-292">在属性窗口中，单击事件按钮。</span><span class="sxs-lookup"><span data-stu-id="02bcb-292">In the Properties window, click the Events button.</span></span> <span data-ttu-id="02bcb-293">附加处理程序<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-293">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
5.  <span data-ttu-id="02bcb-294">打开`MarqueeBorder`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-294">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="02bcb-295">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="02bcb-295">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  <span data-ttu-id="02bcb-296">更改的声明`MarqueeBorder`要从其继承<xref:System.Windows.Forms.Panel>并实现`IMarqueeWidget`接口。</span><span class="sxs-lookup"><span data-stu-id="02bcb-296">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  <span data-ttu-id="02bcb-297">声明用于管理的两个枚举`MarqueeBorder`控件的状态： `MarqueeSpinDirection`，用于确定在其中灯"启动"周围边框的方向和`MarqueeLightShape`，它确定形状的灯 （方形或循环）。</span><span class="sxs-lookup"><span data-stu-id="02bcb-297">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="02bcb-298">将这些声明`MarqueeBorder`类声明。</span><span class="sxs-lookup"><span data-stu-id="02bcb-298">Place these declarations before the `MarqueeBorder` class declaration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  <span data-ttu-id="02bcb-299">声明实例变量对应公开的属性，并对其初始化构造函数中。</span><span class="sxs-lookup"><span data-stu-id="02bcb-299">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. <span data-ttu-id="02bcb-300">实现 `IMarqueeWidget` 接口。</span><span class="sxs-lookup"><span data-stu-id="02bcb-300">Implement the `IMarqueeWidget` interface.</span></span>  
  
     <span data-ttu-id="02bcb-301">`StartMarquee`和`StopMarquee`方法调用<xref:System.ComponentModel.BackgroundWorker>组件的<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>和<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>方法来启动和停止动画。</span><span class="sxs-lookup"><span data-stu-id="02bcb-301">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>  
  
     <span data-ttu-id="02bcb-302">因为`MarqueeBorder`控件可以包含子控件`StartMarquee`方法枚举所有子控件和调用`StartMarquee`上实现的那些`IMarqueeWidget`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-302">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="02bcb-303">`StopMarquee`方法具有一个类似的实现。</span><span class="sxs-lookup"><span data-stu-id="02bcb-303">The `StopMarquee` method has a similar implementation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. <span data-ttu-id="02bcb-304">实现属性访问器。</span><span class="sxs-lookup"><span data-stu-id="02bcb-304">Implement the property accessors.</span></span> <span data-ttu-id="02bcb-305">`MarqueeBorder`控件具有多个属性用于控制其外观。</span><span class="sxs-lookup"><span data-stu-id="02bcb-305">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. <span data-ttu-id="02bcb-306">实现的处理程序<xref:System.ComponentModel.BackgroundWorker>组件的<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-306">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
     <span data-ttu-id="02bcb-307"><xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序休眠由指定的毫秒数`UpdatePeriod`然后引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件，直到你的代码通过调用停止动画<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-307">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>  
  
     <span data-ttu-id="02bcb-308"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序递增"基本"light，从中，确定其他灯的明暗状态，并在结尾调用位置<xref:System.Windows.Forms.Control.Refresh%2A>方法会使控件重绘窗体本身。</span><span class="sxs-lookup"><span data-stu-id="02bcb-308">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. <span data-ttu-id="02bcb-309">实现帮助器方法，`IsLit`和`DrawLight`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-309">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>  
  
     <span data-ttu-id="02bcb-310">`IsLit`方法确定给定位置处的光源的颜色。</span><span class="sxs-lookup"><span data-stu-id="02bcb-310">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="02bcb-311">中指定的颜色绘制"亮起"灯`LightColor`属性，以及那些"深色"中指定的颜色绘制`DarkColor`属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-311">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>  
  
     <span data-ttu-id="02bcb-312">`DrawLight`方法绘制灯光使用适当的颜色、 形状和位置。</span><span class="sxs-lookup"><span data-stu-id="02bcb-312">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. <span data-ttu-id="02bcb-313">重写<xref:System.Windows.Forms.Control.OnLayout%2A>和<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-313">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>  
  
     <span data-ttu-id="02bcb-314"><xref:System.Windows.Forms.Control.OnPaint%2A>方法绘制的边缘灯`MarqueeBorder`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-314">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>  
  
     <span data-ttu-id="02bcb-315">因为<xref:System.Windows.Forms.Control.OnPaint%2A>方法取决于的维度`MarqueeBorder`控件，你需要布局发生更改时调用它。</span><span class="sxs-lookup"><span data-stu-id="02bcb-315">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="02bcb-316">若要实现此目的，重写<xref:System.Windows.Forms.Control.OnLayout%2A>并调用<xref:System.Windows.Forms.Control.Refresh%2A>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-316">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="02bcb-317">创建自定义设计器以隐藏和筛选器属性</span><span class="sxs-lookup"><span data-stu-id="02bcb-317">Creating a Custom Designer to Shadow and Filter Properties</span></span>  
 <span data-ttu-id="02bcb-318">`MarqueeControlRootDesigner`类提供的根设计器的实现。</span><span class="sxs-lookup"><span data-stu-id="02bcb-318">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="02bcb-319">除了此设计器中，作用于`MarqueeControl`，你将需要专门与相关联的自定义设计`MarqueeBorder`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-319">In addition to this designer, which operates on the `MarqueeControl`, you will need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="02bcb-320">此设计器提供相应的自定义根设计器的上下文中的自定义行为。</span><span class="sxs-lookup"><span data-stu-id="02bcb-320">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>  
  
 <span data-ttu-id="02bcb-321">具体而言，`MarqueeBorderDesigner`将"阴影"和筛选某些属性`MarqueeBorder`控件，更改它们与设计环境交互。</span><span class="sxs-lookup"><span data-stu-id="02bcb-321">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>  
  
 <span data-ttu-id="02bcb-322">截获对组件的属性访问器的调用的过程被称为"隐藏"。</span><span class="sxs-lookup"><span data-stu-id="02bcb-322">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="02bcb-323">它允许设计器跟踪由用户设置的值，并选择性地将该值传递到正在设计的组件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-323">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>  
  
 <span data-ttu-id="02bcb-324">对于此示例，<xref:System.Windows.Forms.Control.Visible%2A>和<xref:System.Windows.Forms.Control.Enabled%2A>属性将通过灰显`MarqueeBorderDesigner`，它防止用户进行`MarqueeBorder`控件不可见或在设计时已禁用。</span><span class="sxs-lookup"><span data-stu-id="02bcb-324">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>  
  
 <span data-ttu-id="02bcb-325">设计器还可以添加和删除属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-325">Designers can also add and remove properties.</span></span> <span data-ttu-id="02bcb-326">对于此示例，<xref:System.Windows.Forms.Control.Padding%2A>属性将不再在设计时，因为`MarqueeBorder`控件以编程方式设置基于灯指定大小的空白`LightSize`属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-326">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>  
  
 <span data-ttu-id="02bcb-327">类的基类`MarqueeBorderDesigner`是<xref:System.ComponentModel.Design.ComponentDesigner>，它具有属性、 属性和事件公开由控件在设计时可以更改的方法：</span><span class="sxs-lookup"><span data-stu-id="02bcb-327">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 <span data-ttu-id="02bcb-328">当更改使用这些方法的组件的公共接口，必须遵循下列规则：</span><span class="sxs-lookup"><span data-stu-id="02bcb-328">When changing the public interface of a component using these methods, you must follow these rules:</span></span>  
  
-   <span data-ttu-id="02bcb-329">添加或删除中的项`PreFilter`仅方法</span><span class="sxs-lookup"><span data-stu-id="02bcb-329">Add or remove items in the `PreFilter` methods only</span></span>  
  
-   <span data-ttu-id="02bcb-330">修改中的现有项`PostFilter`仅方法</span><span class="sxs-lookup"><span data-stu-id="02bcb-330">Modify existing items in the `PostFilter` methods only</span></span>  
  
-   <span data-ttu-id="02bcb-331">始终应首先调用基实现`PreFilter`方法</span><span class="sxs-lookup"><span data-stu-id="02bcb-331">Always call the base implementation first in the `PreFilter` methods</span></span>  
  
-   <span data-ttu-id="02bcb-332">始终最后一个地调用基实现`PostFilter`方法</span><span class="sxs-lookup"><span data-stu-id="02bcb-332">Always call the base implementation last in the `PostFilter` methods</span></span>  
  
 <span data-ttu-id="02bcb-333">遵循这些规则可确保在设计时环境中的所有设计器有正在设计的所有组件的一致视图。</span><span class="sxs-lookup"><span data-stu-id="02bcb-333">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>  
  
 <span data-ttu-id="02bcb-334"><xref:System.ComponentModel.Design.ComponentDesigner>类提供一个字典，用于管理隐藏属性值，从而免除了您的需要创建特定实例变量。</span><span class="sxs-lookup"><span data-stu-id="02bcb-334">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>  
  
#### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="02bcb-335">若要创建自定义设计器为卷影和筛选器属性</span><span class="sxs-lookup"><span data-stu-id="02bcb-335">To create a custom designer to shadow and filter properties</span></span>  
  
1.  <span data-ttu-id="02bcb-336">右键单击**设计**文件夹并添加新类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-336">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="02bcb-337">为源文件提供基本名称为"MarqueeBorderDesigner。"</span><span class="sxs-lookup"><span data-stu-id="02bcb-337">Give the source file a base name of "MarqueeBorderDesigner."</span></span>  
  
2.  <span data-ttu-id="02bcb-338">打开`MarqueeBorderDesigner`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-338">Open the `MarqueeBorderDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="02bcb-339">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="02bcb-339">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  <span data-ttu-id="02bcb-340">更改的声明`MarqueeBorderDesigner`要从其继承<xref:System.Windows.Forms.Design.ParentControlDesigner>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-340">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>  
  
     <span data-ttu-id="02bcb-341">因为`MarqueeBorder`控件可以包含子控件`MarqueeBorderDesigner`继承自<xref:System.Windows.Forms.Design.ParentControlDesigner>，可处理的父-子交互。</span><span class="sxs-lookup"><span data-stu-id="02bcb-341">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  <span data-ttu-id="02bcb-342">重写的基实现<xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-342">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  <span data-ttu-id="02bcb-343">实现 <xref:System.Windows.Forms.Control.Enabled%2A> 和 <xref:System.Windows.Forms.Control.Visible%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-343">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="02bcb-344">这些实现隐藏控件的属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-344">These implementations shadow the control's properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## <a name="handling-component-changes"></a><span data-ttu-id="02bcb-345">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="02bcb-345">Handling Component Changes</span></span>  
 <span data-ttu-id="02bcb-346">`MarqueeControlRootDesigner`类提供的自定义设计时体验你`MarqueeControl`实例。</span><span class="sxs-lookup"><span data-stu-id="02bcb-346">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="02bcb-347">大多数的设计时功能从继承<xref:System.Windows.Forms.Design.DocumentDesigner>类; 实现两个特定自定义你的代码将： 处理组件更改和添加设计器谓词。</span><span class="sxs-lookup"><span data-stu-id="02bcb-347">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class; your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>  
  
 <span data-ttu-id="02bcb-348">为用户设计其`MarqueeControl`情况下，根设计器中，将跟踪更改`MarqueeControl`及其子控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-348">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="02bcb-349">设计时环境提供了一种可方便的服务， <xref:System.ComponentModel.Design.IComponentChangeService>，对于跟踪更改为组件状态。</span><span class="sxs-lookup"><span data-stu-id="02bcb-349">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>  
  
 <span data-ttu-id="02bcb-350">通过查询环境使用获取对此服务的引用<xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-350">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="02bcb-351">如果查询成功，则设计器中，可以将附加的处理程序<xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged>事件并执行任何任务所需在设计时维护一致的状态。</span><span class="sxs-lookup"><span data-stu-id="02bcb-351">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>  
  
 <span data-ttu-id="02bcb-352">情况下`MarqueeControlRootDesigner`类，将调用<xref:System.Windows.Forms.Control.Refresh%2A>上每个方法`IMarqueeWidget`对象包含的`MarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-352">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="02bcb-353">这将导致`IMarqueeWidget`对象时重绘自身适当属性如其父级的<xref:System.Windows.Forms.Control.Size%2A>更改。</span><span class="sxs-lookup"><span data-stu-id="02bcb-353">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>  
  
#### <a name="to-handle-component-changes"></a><span data-ttu-id="02bcb-354">若要处理组件更改</span><span class="sxs-lookup"><span data-stu-id="02bcb-354">To handle component changes</span></span>  
  
1.  <span data-ttu-id="02bcb-355">打开`MarqueeControlRootDesigner`中的源文件**代码编辑器**，并重写<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-355">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="02bcb-356">调用基实现的<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>并进行查询， <xref:System.ComponentModel.Design.IComponentChangeService>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-356">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  <span data-ttu-id="02bcb-357">实现<xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="02bcb-357">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="02bcb-358">测试发送组件的类型，以及它是否`IMarqueeWidget`，调用其<xref:System.Windows.Forms.Control.Refresh%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-358">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## <a name="adding-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="02bcb-359">将设计器谓词添加到你的自定义设计器</span><span class="sxs-lookup"><span data-stu-id="02bcb-359">Adding Designer Verbs to your Custom Designer</span></span>  
 <span data-ttu-id="02bcb-360">设计器谓词是链接到事件处理程序的菜单命令。</span><span class="sxs-lookup"><span data-stu-id="02bcb-360">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="02bcb-361">在设计时将设计器谓词添加到组件的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="02bcb-361">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="02bcb-362">有关更多信息，请参见<xref:System.ComponentModel.Design.DesignerVerb>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-362">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>  
  
 <span data-ttu-id="02bcb-363">你将向设计器添加两个设计器谓词：**运行测试**和**停止测试**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-363">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="02bcb-364">这些谓词将允许您查看的运行时行为`MarqueeControl`在设计时。</span><span class="sxs-lookup"><span data-stu-id="02bcb-364">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="02bcb-365">这些谓词将被添加到`MarqueeControlRootDesigner`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-365">These verbs will be added to the `MarqueeControlRootDesigner`.</span></span>  
  
 <span data-ttu-id="02bcb-366">当**运行测试**是调用，则谓词事件处理程序将调用`StartMarquee`方法`MarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-366">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="02bcb-367">当**停止测试**是调用，则谓词事件处理程序将调用`StopMarquee`方法`MarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-367">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="02bcb-368">实现`StartMarquee`和`StopMarquee`方法实现的所含控件上调用这些方法`IMarqueeWidget`，因此任何包含`IMarqueeWidget`控件还将参与测试。</span><span class="sxs-lookup"><span data-stu-id="02bcb-368">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>  
  
#### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="02bcb-369">若要将设计器谓词添加到你的自定义设计器</span><span class="sxs-lookup"><span data-stu-id="02bcb-369">To add designer verbs to your custom designers</span></span>  
  
1.  <span data-ttu-id="02bcb-370">在`MarqueeControlRootDesigner`类中，添加事件处理程序名为`OnVerbRunTest`和`OnVerbStopTest`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-370">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  <span data-ttu-id="02bcb-371">连接到其相应的设计器谓词这些事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="02bcb-371">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="02bcb-372">`MarqueeControlRootDesigner`继承<xref:System.ComponentModel.Design.DesignerVerbCollection>从其基类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-372">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="02bcb-373">你将创建两个新<xref:System.ComponentModel.Design.DesignerVerb>对象，并将它们添加到此集合中<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-373">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## <a name="creating-a-custom-uitypeeditor"></a><span data-ttu-id="02bcb-374">创建自定义 UITypeEditor</span><span class="sxs-lookup"><span data-stu-id="02bcb-374">Creating a Custom UITypeEditor</span></span>  
 <span data-ttu-id="02bcb-375">当你创建用户提供自定义设计时体验时，并通常想创建与属性窗口的自定义交互。</span><span class="sxs-lookup"><span data-stu-id="02bcb-375">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="02bcb-376">你可以通过创建完成此<xref:System.Drawing.Design.UITypeEditor>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-376">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span> <span data-ttu-id="02bcb-377">有关详细信息，请参阅[如何： 创建 UI 类型编辑器](http://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-377">For more information, see [How to: Create a UI Type Editor](http://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd).</span></span>  
  
 <span data-ttu-id="02bcb-378">`MarqueeBorder`控件可公开在属性窗口中的多个属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-378">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="02bcb-379">这些属性的两个`MarqueeSpinDirection`和`MarqueeLightShape`由枚举表示。</span><span class="sxs-lookup"><span data-stu-id="02bcb-379">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="02bcb-380">若要演示如何使用 UI 类型编辑器，`MarqueeLightShape`属性将具有一个关联<xref:System.Drawing.Design.UITypeEditor>类。</span><span class="sxs-lookup"><span data-stu-id="02bcb-380">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>  
  
#### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="02bcb-381">若要创建自定义的 UI 类型编辑器</span><span class="sxs-lookup"><span data-stu-id="02bcb-381">To create a custom UI type editor</span></span>  
  
1.  <span data-ttu-id="02bcb-382">打开`MarqueeBorder`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-382">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="02bcb-383">中的定义`MarqueeBorder`类，声明一个名为类`LightShapeEditor`派生自<xref:System.Drawing.Design.UITypeEditor>。</span><span class="sxs-lookup"><span data-stu-id="02bcb-383">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  <span data-ttu-id="02bcb-384">声明<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>实例变量调用`editorService`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-384">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  <span data-ttu-id="02bcb-385">重写 <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-385">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="02bcb-386">此实现返回<xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>，它指示在设计环境如何显示`LightShapeEditor`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-386">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  <span data-ttu-id="02bcb-387">重写 <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-387">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="02bcb-388">此实现查询的设计环境<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>对象。</span><span class="sxs-lookup"><span data-stu-id="02bcb-388">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="02bcb-389">如果成功，它将创建`LightShapeSelectionControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-389">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="02bcb-390"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>方法调用以启动`LightShapeEditor`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-390">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="02bcb-391">此调用的返回值将返回到设计环境中。</span><span class="sxs-lookup"><span data-stu-id="02bcb-391">The return value from this invocation is returned to the design environment.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="02bcb-392">为自定义 UITypeEditor 创建视图控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-392">Creating a View Control for your Custom UITypeEditor</span></span>  
  
1.  <span data-ttu-id="02bcb-393">`MarqueeLightShape`属性支持两种类型的形状浅色：`Square`和`Circle`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-393">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="02bcb-394">你将创建使用专门用于以图形方式在属性窗口中显示这些值的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-394">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="02bcb-395">此自定义控件将使用你<xref:System.Drawing.Design.UITypeEditor>与属性窗口进行交互。</span><span class="sxs-lookup"><span data-stu-id="02bcb-395">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>  
  
#### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="02bcb-396">若要为你的自定义 UI 类型编辑器创建的视图控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-396">To create a view control for your custom UI type editor</span></span>  
  
1.  <span data-ttu-id="02bcb-397">添加新<xref:System.Windows.Forms.UserControl>项以`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-397">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="02bcb-398">为新的源文件提供基本名称为"LightShapeSelectionControl。"</span><span class="sxs-lookup"><span data-stu-id="02bcb-398">Give the new source file a base name of "LightShapeSelectionControl."</span></span>  
  
2.  <span data-ttu-id="02bcb-399">将两个<xref:System.Windows.Forms.Panel>控件从**工具箱**到`LightShapeSelectionControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-399">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="02bcb-400">对其命名`squarePanel`和`circlePanel`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-400">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="02bcb-401">排列它们并排显示。</span><span class="sxs-lookup"><span data-stu-id="02bcb-401">Arrange them side by side.</span></span> <span data-ttu-id="02bcb-402">设置<xref:System.Windows.Forms.Control.Size%2A>属性均<xref:System.Windows.Forms.Panel>控件添加到 （60，60）。</span><span class="sxs-lookup"><span data-stu-id="02bcb-402">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to (60, 60).</span></span> <span data-ttu-id="02bcb-403">设置<xref:System.Windows.Forms.Control.Location%2A>属性`squarePanel`控制转移到 （8，10）。</span><span class="sxs-lookup"><span data-stu-id="02bcb-403">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to (8, 10).</span></span> <span data-ttu-id="02bcb-404">设置<xref:System.Windows.Forms.Control.Location%2A>属性`circlePanel`控制转移到 80 (10）。</span><span class="sxs-lookup"><span data-stu-id="02bcb-404">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to (80, 10).</span></span> <span data-ttu-id="02bcb-405">最后，设置<xref:System.Windows.Forms.Control.Size%2A>属性`LightShapeSelectionControl`到 150 (80）。</span><span class="sxs-lookup"><span data-stu-id="02bcb-405">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to (150, 80).</span></span>  
  
3.  <span data-ttu-id="02bcb-406">打开`LightShapeSelectionControl`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="02bcb-406">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="02bcb-407">在文件的顶部，导入<xref:System.Windows.Forms.Design?displayProperty=nameWithType>命名空间：</span><span class="sxs-lookup"><span data-stu-id="02bcb-407">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  <span data-ttu-id="02bcb-408">实现<xref:System.Windows.Forms.Control.Click>事件处理程序`squarePanel`和`circlePanel`控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-408">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="02bcb-409">这些方法调用<xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A>结束自定义<xref:System.Drawing.Design.UITypeEditor>编辑会话。</span><span class="sxs-lookup"><span data-stu-id="02bcb-409">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  <span data-ttu-id="02bcb-410">声明<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>实例变量调用`editorService`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-410">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  <span data-ttu-id="02bcb-411">声明`MarqueeLightShape`实例变量调用`lightShapeValue`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-411">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  <span data-ttu-id="02bcb-412">在`LightShapeSelectionControl`构造函数，将附加<xref:System.Windows.Forms.Control.Click>到事件处理程序`squarePanel`和`circlePanel`控件的<xref:System.Windows.Forms.Control.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-412">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="02bcb-413">另外，定义将分配一个构造函数重载`MarqueeLightShape`到设计环境中的值`lightShapeValue`字段。</span><span class="sxs-lookup"><span data-stu-id="02bcb-413">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  <span data-ttu-id="02bcb-414">在<xref:System.ComponentModel.Component.Dispose%2A>方法，分离<xref:System.Windows.Forms.Control.Click>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="02bcb-414">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  <span data-ttu-id="02bcb-415">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="02bcb-415">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="02bcb-416">打开 LightShapeSelectionControl.Designer.cs 或 LightShapeSelectionControl.Designer.vb 文件，并删除默认的定义的<xref:System.ComponentModel.Component.Dispose%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-416">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>  
  
5.  <span data-ttu-id="02bcb-417">实现 `LightShape` 属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-417">Implement the `LightShape` property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  <span data-ttu-id="02bcb-418">重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="02bcb-418">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="02bcb-419">此实现将绘制实心的方块或圆。</span><span class="sxs-lookup"><span data-stu-id="02bcb-419">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="02bcb-420">通过绘制一个形状或其他周围的边框，它还将突出显示所选的值。</span><span class="sxs-lookup"><span data-stu-id="02bcb-420">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## <a name="testing-your-custom-control-in-the-designer"></a><span data-ttu-id="02bcb-421">在设计器中测试自定义控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-421">Testing your Custom Control in the Designer</span></span>  
 <span data-ttu-id="02bcb-422">此时，你可以生成`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="02bcb-422">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="02bcb-423">通过创建继承自的控件来测试您的实现`MarqueeControl`类并在窗体上使用它。</span><span class="sxs-lookup"><span data-stu-id="02bcb-423">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>  
  
#### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="02bcb-424">若要创建自定义的 MarqueeControl 实现</span><span class="sxs-lookup"><span data-stu-id="02bcb-424">To create a custom MarqueeControl implementation</span></span>  
  
1.  <span data-ttu-id="02bcb-425">在 Windows 窗体设计器中打开 `DemoMarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-425">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="02bcb-426">这将创建的实例`DemoMarqueeControl`键入，并将其显示的实例中`MarqueeControlRootDesigner`类型。</span><span class="sxs-lookup"><span data-stu-id="02bcb-426">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>  
  
2.  <span data-ttu-id="02bcb-427">在**工具箱**，打开**MarqueeControlLibrary 组件**选项卡。你将看到`MarqueeBorder`和`MarqueeText`可供选择的控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-427">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>  
  
3.  <span data-ttu-id="02bcb-428">一个实例拖`MarqueeBorder`控件拖动到`DemoMarqueeControl`设计图面。</span><span class="sxs-lookup"><span data-stu-id="02bcb-428">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="02bcb-429">停靠此`MarqueeBorder`到父控件的控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-429">Dock this `MarqueeBorder` control to the parent control.</span></span>  
  
4.  <span data-ttu-id="02bcb-430">一个实例拖`MarqueeText`控件拖动到`DemoMarqueeControl`设计图面。</span><span class="sxs-lookup"><span data-stu-id="02bcb-430">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>  
  
5.  <span data-ttu-id="02bcb-431">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="02bcb-431">Build the solution.</span></span>  
  
6.  <span data-ttu-id="02bcb-432">右键单击`DemoMarqueeControl`并从快捷菜单中选择**运行测试**选项可启动动画。</span><span class="sxs-lookup"><span data-stu-id="02bcb-432">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="02bcb-433">单击**停止测试**停止动画。</span><span class="sxs-lookup"><span data-stu-id="02bcb-433">Click **Stop Test** to stop the animation.</span></span>  
  
7.  <span data-ttu-id="02bcb-434">打开**Form1**在设计视图中。</span><span class="sxs-lookup"><span data-stu-id="02bcb-434">Open **Form1** in Design view.</span></span>  
  
8.  <span data-ttu-id="02bcb-435">放入两个<xref:System.Windows.Forms.Button>表单上的控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-435">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="02bcb-436">对其命名`startButton`和`stopButton`，并更改<xref:System.Windows.Forms.Control.Text%2A>属性值复制到**启动**和**停止**分别。</span><span class="sxs-lookup"><span data-stu-id="02bcb-436">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>  
  
9. <span data-ttu-id="02bcb-437">实现<xref:System.Windows.Forms.Control.Click>事件处理程序同时<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-437">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>  
  
10. <span data-ttu-id="02bcb-438">在**工具箱**，打开**MarqueeControlTest 组件**选项卡。你将看到`DemoMarqueeControl`可供选择。</span><span class="sxs-lookup"><span data-stu-id="02bcb-438">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>  
  
11. <span data-ttu-id="02bcb-439">一个实例拖`DemoMarqueeControl`到**Form1**设计图面。</span><span class="sxs-lookup"><span data-stu-id="02bcb-439">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>  
  
12. <span data-ttu-id="02bcb-440">在<xref:System.Windows.Forms.Control.Click>事件处理程序调用`Start`和`Stop`方法`DemoMarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-440">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>  
  
```vb  
Private Sub startButton_Click(sender As Object, e As System.EventArgs)  
    Me.demoMarqueeControl1.Start()  
End Sub 'startButton_Click  
  
Private Sub stopButton_Click(sender As Object, e As System.EventArgs)  
Me.demoMarqueeControl1.Stop()  
End Sub 'stopButton_Click  
```  
  
```csharp  
private void startButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Start();  
}  
  
private void stopButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Stop();  
}  
```  
  
1.  <span data-ttu-id="02bcb-441">设置`MarqueeControlTest`项目为启动项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="02bcb-441">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="02bcb-442">你将看到窗体显示你`DemoMarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-442">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="02bcb-443">单击**启动**按钮以启动动画。</span><span class="sxs-lookup"><span data-stu-id="02bcb-443">Click the **Start** button to start the animation.</span></span> <span data-ttu-id="02bcb-444">你应看到围绕着边框移动灯和闪烁的文本。</span><span class="sxs-lookup"><span data-stu-id="02bcb-444">You should see the text flashing and the lights moving around the border.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="02bcb-445">后续步骤</span><span class="sxs-lookup"><span data-stu-id="02bcb-445">Next Steps</span></span>  
 <span data-ttu-id="02bcb-446">`MarqueeControlLibrary`演示了如何简单实现的自定义控件和关联的设计器。</span><span class="sxs-lookup"><span data-stu-id="02bcb-446">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="02bcb-447">你可以通过多种方式来进行此示例更复杂：</span><span class="sxs-lookup"><span data-stu-id="02bcb-447">You can make this sample more sophisticated in several ways:</span></span>  
  
-   <span data-ttu-id="02bcb-448">更改的属性值`DemoMarqueeControl`设计器中。</span><span class="sxs-lookup"><span data-stu-id="02bcb-448">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="02bcb-449">添加更多`MarqueBorder`控件并将其停靠在其父实例中以创建嵌套的效果。</span><span class="sxs-lookup"><span data-stu-id="02bcb-449">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="02bcb-450">试验不同的设置`UpdatePeriod`和 light 相关属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-450">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>  
  
-   <span data-ttu-id="02bcb-451">创作你自己的实现`IMarqueeWidget`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-451">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="02bcb-452">例如，可以使用多个映像创建闪烁的"霓虹灯登录"或动画的标志。</span><span class="sxs-lookup"><span data-stu-id="02bcb-452">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>  
  
-   <span data-ttu-id="02bcb-453">进一步自定义设计时体验。</span><span class="sxs-lookup"><span data-stu-id="02bcb-453">Further customize the design-time experience.</span></span> <span data-ttu-id="02bcb-454">你可以尝试更多属性比<xref:System.Windows.Forms.Control.Enabled%2A>和<xref:System.Windows.Forms.Control.Visible%2A>，并添加新属性。</span><span class="sxs-lookup"><span data-stu-id="02bcb-454">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="02bcb-455">添加新的设计器谓词以简化常见任务，比如停靠子控件。</span><span class="sxs-lookup"><span data-stu-id="02bcb-455">Add new designer verbs to simplify common tasks like docking child controls.</span></span>  
  
-   <span data-ttu-id="02bcb-456">许可证`MarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="02bcb-456">License the `MarqueeControl`.</span></span> <span data-ttu-id="02bcb-457">有关详细信息，请参阅[How to： 许可证组件和控件](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-457">For more information, see [How to: License Components and Controls](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57).</span></span>  
  
-   <span data-ttu-id="02bcb-458">控制如何序列化你的控件以及如何为其生成代码。</span><span class="sxs-lookup"><span data-stu-id="02bcb-458">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="02bcb-459">有关详细信息，请参阅[动态源代码生成和编译](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)。</span><span class="sxs-lookup"><span data-stu-id="02bcb-459">For more information, see [Dynamic Source Code Generation and Compilation](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02bcb-460">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02bcb-460">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Design.ParentControlDesigner>  
 <xref:System.Windows.Forms.Design.DocumentDesigner>  
 <xref:System.ComponentModel.Design.IRootDesigner>  
 <xref:System.ComponentModel.Design.DesignerVerb>  
 <xref:System.Drawing.Design.UITypeEditor>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="02bcb-461">如何：创建利用设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="02bcb-461">How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features</span></span>](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)  
 [<span data-ttu-id="02bcb-462">扩展设计时支持</span><span class="sxs-lookup"><span data-stu-id="02bcb-462">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="02bcb-463">自定义设计器</span><span class="sxs-lookup"><span data-stu-id="02bcb-463">Custom Designers</span></span>](http://msdn.microsoft.com/library/ca11988e-d38e-44d8-a05d-71362ae7844d)  
 [<span data-ttu-id="02bcb-464">.NET 形状库： 示例设计器</span><span class="sxs-lookup"><span data-stu-id="02bcb-464">.NET Shape Library: A Sample Designer</span></span>](http://windowsforms.net/articles/shapedesigner.aspx)
