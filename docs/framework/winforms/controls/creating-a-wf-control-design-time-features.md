---
title: 演练：创建一个利用 Visual Studio 设计时功能的 Windows 窗体控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
ms.openlocfilehash: aa30842ca72bb50767513cf387f59e29e40574e8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865860"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a><span data-ttu-id="7218f-102">演练：创建一个利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7218f-102">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>
<span data-ttu-id="7218f-103">可以通过创作的关联的自定义设计器增强自定义控件的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="7218f-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>  
  
 <span data-ttu-id="7218f-104">本演练演示如何创建自定义控件的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="7218f-104">This walkthrough illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="7218f-105">将实现`MarqueeControl`类型和关联的设计器类，名为`MarqueeControlRootDesigner`。</span><span class="sxs-lookup"><span data-stu-id="7218f-105">You will implement a `MarqueeControl` type and an associated designer class, called `MarqueeControlRootDesigner`.</span></span>  
  
 <span data-ttu-id="7218f-106">`MarqueeControl`类型实现类似于影院字幕，与经过动画处理的灯光和闪烁文本显示。</span><span class="sxs-lookup"><span data-stu-id="7218f-106">The `MarqueeControl` type implements a display similar to a theater marquee, with animated lights and flashing text.</span></span>  
  
 <span data-ttu-id="7218f-107">此控件的设计器与要提供自定义设计时体验的设计环境进行交互。</span><span class="sxs-lookup"><span data-stu-id="7218f-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="7218f-108">使用自定义设计器，来组合自定义`MarqueeControl`实现动画的灯光和闪烁文本以多种组合。</span><span class="sxs-lookup"><span data-stu-id="7218f-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="7218f-109">可以使用类似于任何其他 Windows 窗体控件在窗体上组合的控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>  
  
 <span data-ttu-id="7218f-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="7218f-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="7218f-111">创建项目</span><span class="sxs-lookup"><span data-stu-id="7218f-111">Creating the Project</span></span>  
  
-   <span data-ttu-id="7218f-112">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="7218f-112">Creating a Control Library Project</span></span>  
  
-   <span data-ttu-id="7218f-113">引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="7218f-113">Referencing the Custom Control Project</span></span>  
  
-   <span data-ttu-id="7218f-114">定义自定义控件和其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="7218f-114">Defining a Custom Control and Its Custom Designer</span></span>  
  
-   <span data-ttu-id="7218f-115">创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="7218f-115">Creating an Instance of Your Custom Control</span></span>  
  
-   <span data-ttu-id="7218f-116">设置设计时调试项目</span><span class="sxs-lookup"><span data-stu-id="7218f-116">Setting Up the Project for Design-Time Debugging</span></span>  
  
-   <span data-ttu-id="7218f-117">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="7218f-117">Implementing Your Custom Control</span></span>  
  
-   <span data-ttu-id="7218f-118">创建子控件的自定义控件</span><span class="sxs-lookup"><span data-stu-id="7218f-118">Creating a Child Control for Your Custom Control</span></span>  
  
-   <span data-ttu-id="7218f-119">创建放子控件</span><span class="sxs-lookup"><span data-stu-id="7218f-119">Create the MarqueeBorder Child Control</span></span>  
  
-   <span data-ttu-id="7218f-120">创建自定义设计器以隐藏和筛选器属性</span><span class="sxs-lookup"><span data-stu-id="7218f-120">Creating a Custom Designer to Shadow and Filter Properties</span></span>  
  
-   <span data-ttu-id="7218f-121">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="7218f-121">Handling Component Changes</span></span>  
  
-   <span data-ttu-id="7218f-122">将设计器谓词添加到自定义设计器</span><span class="sxs-lookup"><span data-stu-id="7218f-122">Adding Designer Verbs to your Custom Designer</span></span>  
  
-   <span data-ttu-id="7218f-123">创建自定义 UITypeEditor</span><span class="sxs-lookup"><span data-stu-id="7218f-123">Creating a Custom UITypeEditor</span></span>  
  
-   <span data-ttu-id="7218f-124">在设计器中测试自定义控件</span><span class="sxs-lookup"><span data-stu-id="7218f-124">Testing your Custom Control in the Designer</span></span>  
  
 <span data-ttu-id="7218f-125">完成后，自定义控件看起来类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="7218f-125">When you are finished, your custom control will look something like the following:</span></span>  
  
 <span data-ttu-id="7218f-126">![可能的 MarqueeControl 排列](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "器")</span><span class="sxs-lookup"><span data-stu-id="7218f-126">![A possible MarqueeControl arrangement](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")</span></span>  
  
 <span data-ttu-id="7218f-127">有关完整代码列表，请参阅[如何： 创建 Windows 窗体控件，需要利用设计时功能](https://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)。</span><span class="sxs-lookup"><span data-stu-id="7218f-127">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7218f-128">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="7218f-128">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7218f-129">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="7218f-129">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7218f-130">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="7218f-130">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7218f-131">系统必备</span><span class="sxs-lookup"><span data-stu-id="7218f-131">Prerequisites</span></span>  
 <span data-ttu-id="7218f-132">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="7218f-132">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="7218f-133">若要能够创建和安装 Visual Studio 的计算机上运行 Windows 窗体应用程序项目的足够权限。</span><span class="sxs-lookup"><span data-stu-id="7218f-133">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="7218f-134">创建项目</span><span class="sxs-lookup"><span data-stu-id="7218f-134">Creating the Project</span></span>  
 <span data-ttu-id="7218f-135">第一步是创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-135">The first step is to create the application project.</span></span> <span data-ttu-id="7218f-136">将使用此项目以生成承载自定义控件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7218f-136">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="7218f-137">要创建项目</span><span class="sxs-lookup"><span data-stu-id="7218f-137">To create the project</span></span>  
  
-   <span data-ttu-id="7218f-138">创建一个名为"MarqueeControlTest"的 Windows 窗体应用程序项目 (**文件** > **新建** > **项目** >  **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="7218f-138">Create a Windows Forms Application project called "MarqueeControlTest" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="7218f-139">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="7218f-139">Creating a Control Library Project</span></span>  
 <span data-ttu-id="7218f-140">下一步是创建控件库项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-140">The next step is to create the control library project.</span></span> <span data-ttu-id="7218f-141">您将创建一个新的自定义控件和其相应的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="7218f-141">You will create a new custom control and its corresponding custom designer.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="7218f-142">若要创建的控件库项目</span><span class="sxs-lookup"><span data-stu-id="7218f-142">To create the control library project</span></span>  
  
1.  <span data-ttu-id="7218f-143">向解决方案添加 Windows 窗体控件库项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-143">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="7218f-144">命名项目"MarqueeControlLibrary。"</span><span class="sxs-lookup"><span data-stu-id="7218f-144">Name the project "MarqueeControlLibrary."</span></span>  
  
2.  <span data-ttu-id="7218f-145">使用**解决方案资源管理器**，通过删除源文件，具体取决于你选择的语言中名为"UserControl1.cs"或"UserControl1.vb"来删除项目的默认控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-145">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span> <span data-ttu-id="7218f-146">有关详细信息，请参阅[NIB： 如何： 删除、 删除和排除项](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)。</span><span class="sxs-lookup"><span data-stu-id="7218f-146">For more information, see [NIB:How to: Remove, Delete, and Exclude Items](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
3.  <span data-ttu-id="7218f-147">添加一个新<xref:System.Windows.Forms.UserControl>项`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-147">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="7218f-148">新的源文件基名称指定为"MarqueeControl。"</span><span class="sxs-lookup"><span data-stu-id="7218f-148">Give the new source file a base name of "MarqueeControl."</span></span>  
  
4.  <span data-ttu-id="7218f-149">使用**解决方案资源管理器**，创建一个新文件夹中的`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-149">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="7218f-150">有关详细信息，请参阅[NIB： 如何： 添加新项目项](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)。</span><span class="sxs-lookup"><span data-stu-id="7218f-150">For more information, see [NIB:How to: Add New Project Items](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="7218f-151">将新文件夹命名为"设计"。</span><span class="sxs-lookup"><span data-stu-id="7218f-151">Name the new folder "Design."</span></span>  
  
5.  <span data-ttu-id="7218f-152">右键单击**设计**文件夹并添加新类。</span><span class="sxs-lookup"><span data-stu-id="7218f-152">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="7218f-153">源文件基名称指定为"MarqueeControlRootDesigner。"</span><span class="sxs-lookup"><span data-stu-id="7218f-153">Give the source file a base name of "MarqueeControlRootDesigner."</span></span>  
  
6.  <span data-ttu-id="7218f-154">将需要使用来自 System.Design 程序集类型，因此添加到此引用`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-154">You will need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7218f-155">若要使用 System.Design 程序集，你的项目必须面向.NET Framework 中，而非.NET Framework 客户端配置文件的完整版本。</span><span class="sxs-lookup"><span data-stu-id="7218f-155">To use the System.Design assembly, your project must target the full version of the .NET Framework, not the .NET Framework Client Profile.</span></span> <span data-ttu-id="7218f-156">若要更改目标框架，请参阅[如何： 面向.NET Framework 版本](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)。</span><span class="sxs-lookup"><span data-stu-id="7218f-156">To change the target framework, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>  
  
## <a name="referencing-the-custom-control-project"></a><span data-ttu-id="7218f-157">引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="7218f-157">Referencing the Custom Control Project</span></span>  
 <span data-ttu-id="7218f-158">将使用`MarqueeControlTest`项目，以测试自定义控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-158">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="7218f-159">测试项目就会变得注意的自定义控件添加到项目引用`MarqueeControlLibrary`程序集。</span><span class="sxs-lookup"><span data-stu-id="7218f-159">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>  
  
#### <a name="to-reference-the-custom-control-project"></a><span data-ttu-id="7218f-160">若要引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="7218f-160">To reference the custom control project</span></span>  
  
-   <span data-ttu-id="7218f-161">在中`MarqueeControlTest`项目中，添加到项目引用`MarqueeControlLibrary`程序集。</span><span class="sxs-lookup"><span data-stu-id="7218f-161">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="7218f-162">请务必使用**项目**选项卡**添加引用**而不是引用对话框的`MarqueeControlLibrary`直接的程序集。</span><span class="sxs-lookup"><span data-stu-id="7218f-162">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>  
  
## <a name="defining-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="7218f-163">定义自定义控件和其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="7218f-163">Defining a Custom Control and Its Custom Designer</span></span>  
 <span data-ttu-id="7218f-164">自定义控件都派生自<xref:System.Windows.Forms.UserControl>类。</span><span class="sxs-lookup"><span data-stu-id="7218f-164">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="7218f-165">这允许你控制用于包含其他控件，并为您的控件提供了大量的默认功能。</span><span class="sxs-lookup"><span data-stu-id="7218f-165">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>  
  
 <span data-ttu-id="7218f-166">自定义控件将具有关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="7218f-166">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="7218f-167">这允许您创建专门用于自定义控件量身定制的独特的设计体验。</span><span class="sxs-lookup"><span data-stu-id="7218f-167">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>  
  
 <span data-ttu-id="7218f-168">将控件与设计器关联使用<xref:System.ComponentModel.DesignerAttribute>类。</span><span class="sxs-lookup"><span data-stu-id="7218f-168">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="7218f-169">由于正在开发的自定义控件的整个设计时行为，自定义设计器将实现<xref:System.ComponentModel.Design.IRootDesigner>接口。</span><span class="sxs-lookup"><span data-stu-id="7218f-169">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>  
  
#### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="7218f-170">若要定义自定义控件和其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="7218f-170">To define a custom control and its custom designer</span></span>  
  
1.  <span data-ttu-id="7218f-171">打开`MarqueeControl`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-171">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="7218f-172">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="7218f-172">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  <span data-ttu-id="7218f-173">添加<xref:System.ComponentModel.DesignerAttribute>到`MarqueeControl`类声明。</span><span class="sxs-lookup"><span data-stu-id="7218f-173">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="7218f-174">这将与设计器关联的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-174">This associates the custom control with its designer.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  <span data-ttu-id="7218f-175">打开`MarqueeControlRootDesigner`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-175">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="7218f-176">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="7218f-176">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  <span data-ttu-id="7218f-177">更改的声明`MarqueeControlRootDesigner`从中继承<xref:System.Windows.Forms.Design.DocumentDesigner>类。</span><span class="sxs-lookup"><span data-stu-id="7218f-177">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="7218f-178">将应用<xref:System.ComponentModel.ToolboxItemFilterAttribute>以指定与设计器交互**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="7218f-178">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>  
  
     <span data-ttu-id="7218f-179">**请注意**的定义`MarqueeControlRootDesigner`类将其括在命名空间名为"MarqueeControlLibrary.Design。"</span><span class="sxs-lookup"><span data-stu-id="7218f-179">**Note** The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called "MarqueeControlLibrary.Design."</span></span> <span data-ttu-id="7218f-180">此声明会放在设计器中的特殊命名空间保留为与设计相关的类型。</span><span class="sxs-lookup"><span data-stu-id="7218f-180">This declaration places the designer in a special namespace reserved for design-related types.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  <span data-ttu-id="7218f-181">定义的构造函数`MarqueeControlRootDesigner`类。</span><span class="sxs-lookup"><span data-stu-id="7218f-181">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="7218f-182">插入<xref:System.Diagnostics.Trace.WriteLine%2A>构造函数主体中的语句。</span><span class="sxs-lookup"><span data-stu-id="7218f-182">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="7218f-183">这将是用于调试目的。</span><span class="sxs-lookup"><span data-stu-id="7218f-183">This will be useful for debugging purposes.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## <a name="creating-an-instance-of-your-custom-control"></a><span data-ttu-id="7218f-184">创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="7218f-184">Creating an Instance of Your Custom Control</span></span>  
 <span data-ttu-id="7218f-185">若要观察您的控件的自定义设计时行为，将放置在窗体上控件的实例`MarqueeControlTest`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-185">To observe the custom design-time behavior of your control, you will place an instance of your control on the form in `MarqueeControlTest` project.</span></span>  
  
#### <a name="to-create-an-instance-of-your-custom-control"></a><span data-ttu-id="7218f-186">若要创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="7218f-186">To create an instance of your custom control</span></span>  
  
1.  <span data-ttu-id="7218f-187">添加一个新<xref:System.Windows.Forms.UserControl>项`MarqueeControlTest`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-187">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="7218f-188">新的源文件基名称指定为"器。"</span><span class="sxs-lookup"><span data-stu-id="7218f-188">Give the new source file a base name of "DemoMarqueeControl."</span></span>  
  
2.  <span data-ttu-id="7218f-189">打开`DemoMarqueeControl`文件中**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-189">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="7218f-190">该文件顶部，导入`MarqueeControlLibrary`命名空间：</span><span class="sxs-lookup"><span data-stu-id="7218f-190">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  <span data-ttu-id="7218f-191">更改的声明`DemoMarqueeControl`从中继承`MarqueeControl`类。</span><span class="sxs-lookup"><span data-stu-id="7218f-191">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>  
  
2.  <span data-ttu-id="7218f-192">生成项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-192">Build the project.</span></span>  
  
3.  <span data-ttu-id="7218f-193">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="7218f-193">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="7218f-194">查找**MarqueeControlTest 组件**选项卡**工具箱**并将其打开。</span><span class="sxs-lookup"><span data-stu-id="7218f-194">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="7218f-195">拖动`DemoMarqueeControl`从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="7218f-195">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>  
  
5.  <span data-ttu-id="7218f-196">生成项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-196">Build the project.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="7218f-197">设置设计时调试项目</span><span class="sxs-lookup"><span data-stu-id="7218f-197">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="7218f-198">当你正在开发的自定义设计时体验时，将需要调试控件和组件。</span><span class="sxs-lookup"><span data-stu-id="7218f-198">When you are developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="7218f-199">没有将项目设置以允许在设计时调试的简单方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-199">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="7218f-200">有关详细信息，请参阅[演练： 调试在设计时自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="7218f-200">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="7218f-201">若要设置项目以便进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="7218f-201">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="7218f-202">右键单击`MarqueeControlLibrary`项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="7218f-202">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="7218f-203">在"MarqueeControlLibrary 属性页"对话框中，选择**调试**页。</span><span class="sxs-lookup"><span data-stu-id="7218f-203">In the "MarqueeControlLibrary Property Pages" dialog box, select the **Debug** page.</span></span>  
  
3.  <span data-ttu-id="7218f-204">在中**启动操作**部分中，选择**启动外部程序**。</span><span class="sxs-lookup"><span data-stu-id="7218f-204">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="7218f-205">你将调试的单独实例的 Visual Studio 中，因此请单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以浏览 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="7218f-205">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="7218f-206">可执行文件名称为 devenv.exe，并且如果已安装到默认位置，其路径为 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe。</span><span class="sxs-lookup"><span data-stu-id="7218f-206">The name of the executable file is devenv.exe, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
4.  <span data-ttu-id="7218f-207">单击确定以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="7218f-207">Click OK to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="7218f-208">右键单击`MarqueeControlLibrary`项目，然后选择"设为启动项目"来启用此调试配置。</span><span class="sxs-lookup"><span data-stu-id="7218f-208">Right-click the `MarqueeControlLibrary` project and select "Set as StartUp Project" to enable this debugging configuration.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="7218f-209">检查点</span><span class="sxs-lookup"><span data-stu-id="7218f-209">Checkpoint</span></span>  
 <span data-ttu-id="7218f-210">现在您就可以调试自定义控件的设计时行为。</span><span class="sxs-lookup"><span data-stu-id="7218f-210">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="7218f-211">一旦您已确定正确设置调试环境，您将测试自定义控件和自定义设计器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="7218f-211">Once you have determined that the debugging environment is set up correctly, you will test the association between the custom control and the custom designer.</span></span>  
  
#### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="7218f-212">若要测试的调试环境和设计器关联</span><span class="sxs-lookup"><span data-stu-id="7218f-212">To test the debugging environment and the designer association</span></span>  
  
1.  <span data-ttu-id="7218f-213">打开`MarqueeControlRootDesigner`中的源文件**代码编辑器**并将断点放置在<xref:System.Diagnostics.Trace.WriteLine%2A>语句。</span><span class="sxs-lookup"><span data-stu-id="7218f-213">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>  
  
2.  <span data-ttu-id="7218f-214">按 F5 启动调试会话。</span><span class="sxs-lookup"><span data-stu-id="7218f-214">Press F5 to start the debugging session.</span></span> <span data-ttu-id="7218f-215">请注意，创建 Visual Studio 的新实例。</span><span class="sxs-lookup"><span data-stu-id="7218f-215">Note that a new instance of Visual Studio is created.</span></span>  
  
3.  <span data-ttu-id="7218f-216">在 Visual Studio 的新实例中，打开"MarqueeControlTest"解决方案。</span><span class="sxs-lookup"><span data-stu-id="7218f-216">In the new instance of Visual Studio, open the "MarqueeControlTest" solution.</span></span> <span data-ttu-id="7218f-217">您可以轻松地找到解决方案，通过选择**最近使用的项目**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="7218f-217">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="7218f-218">将列出"MarqueeControlTest.sln"解决方案文件，如最近使用的文件。</span><span class="sxs-lookup"><span data-stu-id="7218f-218">The "MarqueeControlTest.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="7218f-219">打开`DemoMarqueeControl`在设计器中。</span><span class="sxs-lookup"><span data-stu-id="7218f-219">Open the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="7218f-220">请注意，Visual Studio 的调试实例获取焦点执行在断点处停止。</span><span class="sxs-lookup"><span data-stu-id="7218f-220">Note that the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="7218f-221">按 f5 键继续调试会话。</span><span class="sxs-lookup"><span data-stu-id="7218f-221">Press F5 to continue the debugging session.</span></span>  
  
 <span data-ttu-id="7218f-222">此时，所有内容已准备就绪，以便开发和调试自定义控件和其关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="7218f-222">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="7218f-223">本演练的其余部分将精力集中于实现的控件和设计器功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7218f-223">The remainder of this walkthrough will concentrate on the details of implementing features of the control and the designer.</span></span>  
  
## <a name="implementing-your-custom-control"></a><span data-ttu-id="7218f-224">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="7218f-224">Implementing Your Custom Control</span></span>  
 <span data-ttu-id="7218f-225">`MarqueeControl`是<xref:System.Windows.Forms.UserControl>极少量的自定义。</span><span class="sxs-lookup"><span data-stu-id="7218f-225">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="7218f-226">它公开两个方法： `Start`，从而启动字幕动画和`Stop`，后者会停止动画。</span><span class="sxs-lookup"><span data-stu-id="7218f-226">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="7218f-227">因为`MarqueeControl`包含实现的子控件`IMarqueeWidget`接口，`Start`并`Stop`枚举每个子控件和调用`StartMarquee`和`StopMarquee`方法，分别在每个子控件它实现`IMarqueeWidget`。</span><span class="sxs-lookup"><span data-stu-id="7218f-227">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>  
  
 <span data-ttu-id="7218f-228">外观`MarqueeBorder`并`MarqueeText`控件是依赖于布局，因此`MarqueeControl`重写<xref:System.Windows.Forms.Control.OnLayout%2A>方法并调用<xref:System.Windows.Forms.Control.PerformLayout%2A>上此类型的子控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-228">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>  
  
 <span data-ttu-id="7218f-229">这是程度`MarqueeControl`自定义项。</span><span class="sxs-lookup"><span data-stu-id="7218f-229">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="7218f-230">运行时功能由实现`MarqueeBorder`并`MarqueeText`控件和设计时功能由实现`MarqueeBorderDesigner`和`MarqueeControlRootDesigner`类。</span><span class="sxs-lookup"><span data-stu-id="7218f-230">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>  
  
#### <a name="to-implement-your-custom-control"></a><span data-ttu-id="7218f-231">若要实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="7218f-231">To implement your custom control</span></span>  
  
1.  <span data-ttu-id="7218f-232">打开`MarqueeControl`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-232">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="7218f-233">实现`Start`和`Stop`方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-233">Implement the `Start` and `Stop` methods.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  <span data-ttu-id="7218f-234">重写 <xref:System.Windows.Forms.Control.OnLayout%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-234">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## <a name="creating-a-child-control-for-your-custom-control"></a><span data-ttu-id="7218f-235">创建子控件的自定义控件</span><span class="sxs-lookup"><span data-stu-id="7218f-235">Creating a Child Control for Your Custom Control</span></span>  
 <span data-ttu-id="7218f-236">`MarqueeControl`将承载的子控件的两种类型：`MarqueeBorder`控件和`MarqueeText`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-236">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>  
  
-   <span data-ttu-id="7218f-237">`MarqueeBorder`： 此控件绘制"lights"其边缘周围的边框。</span><span class="sxs-lookup"><span data-stu-id="7218f-237">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="7218f-238">灯光闪烁在序列中，使其显示以围绕着边框移动。</span><span class="sxs-lookup"><span data-stu-id="7218f-238">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="7218f-239">由一个名为属性控制在其灯闪烁的速度`UpdatePeriod`。</span><span class="sxs-lookup"><span data-stu-id="7218f-239">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="7218f-240">多个其他自定义属性确定控件的外观的其他方面。</span><span class="sxs-lookup"><span data-stu-id="7218f-240">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="7218f-241">两种方法，称为`StartMarquee`和`StopMarquee`，控制动画启动和停止时。</span><span class="sxs-lookup"><span data-stu-id="7218f-241">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>  
  
-   <span data-ttu-id="7218f-242">`MarqueeText`： 此控件将绘制一个闪烁的字符串。</span><span class="sxs-lookup"><span data-stu-id="7218f-242">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="7218f-243">像`MarqueeBorder`控件中，文本会闪烁的速度由控制`UpdatePeriod`属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-243">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="7218f-244">`MarqueeText`控件还具有`StartMarquee`并`StopMarquee`方法与`MarqueeBorder`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-244">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>  
  
 <span data-ttu-id="7218f-245">在设计时`MarqueeControlRootDesigner`允许这些两个控件的类型添加到`MarqueeControl`的任意组合。</span><span class="sxs-lookup"><span data-stu-id="7218f-245">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>  
  
 <span data-ttu-id="7218f-246">两个控件的常见功能包含在一个名为`IMarqueeWidget`。</span><span class="sxs-lookup"><span data-stu-id="7218f-246">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="7218f-247">这允许`MarqueeControl`发现任何字幕相关子控件，并为它们提供特殊处理。</span><span class="sxs-lookup"><span data-stu-id="7218f-247">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>  
  
 <span data-ttu-id="7218f-248">若要实现定期动画功能，您将使用<xref:System.ComponentModel.BackgroundWorker>中的对象<xref:System.ComponentModel?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="7218f-248">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="7218f-249">可以使用<xref:System.Windows.Forms.Timer>对象，但是当许多`IMarqueeWidget`对象是否存在后，在单个 UI 线程可能无法及时了解动画。</span><span class="sxs-lookup"><span data-stu-id="7218f-249">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>  
  
#### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="7218f-250">若要创建自定义控件的子控件</span><span class="sxs-lookup"><span data-stu-id="7218f-250">To create a child control for your custom control</span></span>  
  
1.  <span data-ttu-id="7218f-251">添加到一个新类项`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-251">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="7218f-252">新的源文件基名称指定为"IMarqueeWidget。"</span><span class="sxs-lookup"><span data-stu-id="7218f-252">Give the new source file a base name of "IMarqueeWidget."</span></span>  
  
2.  <span data-ttu-id="7218f-253">打开`IMarqueeWidget`中的源文件**代码编辑器**并将更改从声明`class`到`interface`:</span><span class="sxs-lookup"><span data-stu-id="7218f-253">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  <span data-ttu-id="7218f-254">将以下代码添加到`IMarqueeWidget`接口，以公开两个方法和操作字幕动画的属性：</span><span class="sxs-lookup"><span data-stu-id="7218f-254">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  <span data-ttu-id="7218f-255">添加一个新**自定义控件**项`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-255">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="7218f-256">新的源文件基名称指定为"显示"。</span><span class="sxs-lookup"><span data-stu-id="7218f-256">Give the new source file a base name of "MarqueeText."</span></span>  
  
5.  <span data-ttu-id="7218f-257">拖动<xref:System.ComponentModel.BackgroundWorker>组件从**工具箱**拖动到你`MarqueeText`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-257">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="7218f-258">此组件将允许`MarqueeText`控件以异步方式将自行更新。</span><span class="sxs-lookup"><span data-stu-id="7218f-258">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>  
  
6.  <span data-ttu-id="7218f-259">在属性窗口中设置<xref:System.ComponentModel.BackgroundWorker>组件的`WorkerReportsProgess`并<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="7218f-259">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgess` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="7218f-260">这些设置允许<xref:System.ComponentModel.BackgroundWorker>组件来定期引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件并取消异步更新。</span><span class="sxs-lookup"><span data-stu-id="7218f-260">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="7218f-261">有关详细信息，请参阅[BackgroundWorker 组件](../../../../docs/framework/winforms/controls/backgroundworker-component.md)。</span><span class="sxs-lookup"><span data-stu-id="7218f-261">For more information, see [BackgroundWorker Component](../../../../docs/framework/winforms/controls/backgroundworker-component.md).</span></span>  
  
7.  <span data-ttu-id="7218f-262">打开`MarqueeText`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-262">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="7218f-263">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="7218f-263">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  <span data-ttu-id="7218f-264">更改的声明`MarqueeText`继承自<xref:System.Windows.Forms.Label>以及实现`IMarqueeWidget`接口：</span><span class="sxs-lookup"><span data-stu-id="7218f-264">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. <span data-ttu-id="7218f-265">声明与公开的属性相对应的实例变量，并在构造函数中对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="7218f-265">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="7218f-266">`isLit`字段确定是否要在指定的颜色绘制文本`LightColor`属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-266">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. <span data-ttu-id="7218f-267">实现 `IMarqueeWidget` 接口。</span><span class="sxs-lookup"><span data-stu-id="7218f-267">Implement the `IMarqueeWidget` interface.</span></span>  
  
     <span data-ttu-id="7218f-268">`StartMarquee`并`StopMarquee`方法调用<xref:System.ComponentModel.BackgroundWorker>组件的<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>和<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>方法来启动和停止动画。</span><span class="sxs-lookup"><span data-stu-id="7218f-268">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>  
  
     <span data-ttu-id="7218f-269"><xref:System.ComponentModel.CategoryAttribute.Category%2A>并<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>特性应用于`UpdatePeriod`属性使它出现在名为"Marquee。"属性窗口的自定义部分</span><span class="sxs-lookup"><span data-stu-id="7218f-269">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. <span data-ttu-id="7218f-270">实现属性访问器。</span><span class="sxs-lookup"><span data-stu-id="7218f-270">Implement the property accessors.</span></span> <span data-ttu-id="7218f-271">您将会向客户端的两个属性：`LightColor`和`DarkColor`。</span><span class="sxs-lookup"><span data-stu-id="7218f-271">You will expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="7218f-272"><xref:System.ComponentModel.CategoryAttribute.Category%2A>和<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>属性应用于这些属性，因此属性将出现在名为"Marquee。"属性窗口的自定义部分</span><span class="sxs-lookup"><span data-stu-id="7218f-272">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. <span data-ttu-id="7218f-273">实现的处理程序<xref:System.ComponentModel.BackgroundWorker>组件的<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="7218f-273">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
     <span data-ttu-id="7218f-274"><xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序指定的毫秒数将休眠`UpdatePeriod`然后引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件，直到你的代码通过调用停止动画<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>。</span><span class="sxs-lookup"><span data-stu-id="7218f-274">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>  
  
     <span data-ttu-id="7218f-275"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序切换其浅色和深色状态，以提供闪烁外观之间的文本。</span><span class="sxs-lookup"><span data-stu-id="7218f-275">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. <span data-ttu-id="7218f-276">重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法，以使动画。</span><span class="sxs-lookup"><span data-stu-id="7218f-276">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. <span data-ttu-id="7218f-277">按 F6 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="7218f-277">Press F6 to build the solution.</span></span>  
  
## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="7218f-278">创建放子控件</span><span class="sxs-lookup"><span data-stu-id="7218f-278">Create the MarqueeBorder Child Control</span></span>  
 <span data-ttu-id="7218f-279">`MarqueeBorder`控件是比要稍微复杂`MarqueeText`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-279">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="7218f-280">它具有更多属性和在动画<xref:System.Windows.Forms.Control.OnPaint%2A>方法是更为复杂。</span><span class="sxs-lookup"><span data-stu-id="7218f-280">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="7218f-281">从原理上讲，它是非常类似于`MarqueeText`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-281">In principle, it is quite similar to the `MarqueeText` control.</span></span>  
  
 <span data-ttu-id="7218f-282">因为`MarqueeBorder`控件可以有子控件，它必须要注意<xref:System.Windows.Forms.Control.Layout>事件。</span><span class="sxs-lookup"><span data-stu-id="7218f-282">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>  
  
#### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="7218f-283">若要创建放控件</span><span class="sxs-lookup"><span data-stu-id="7218f-283">To create the MarqueeBorder control</span></span>  
  
1.  <span data-ttu-id="7218f-284">添加一个新**自定义控件**项`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-284">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="7218f-285">新的源文件基名称指定为"放"。</span><span class="sxs-lookup"><span data-stu-id="7218f-285">Give the new source file a base name of "MarqueeBorder."</span></span>  
  
2.  <span data-ttu-id="7218f-286">拖动<xref:System.ComponentModel.BackgroundWorker>组件从**工具箱**拖动到你`MarqueeBorder`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-286">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="7218f-287">此组件将允许`MarqueeBorder`控件以异步方式将自行更新。</span><span class="sxs-lookup"><span data-stu-id="7218f-287">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>  
  
3.  <span data-ttu-id="7218f-288">在属性窗口中设置<xref:System.ComponentModel.BackgroundWorker>组件的`WorkerReportsProgess`并<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="7218f-288">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgess` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="7218f-289">这些设置允许<xref:System.ComponentModel.BackgroundWorker>组件来定期引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件并取消异步更新。</span><span class="sxs-lookup"><span data-stu-id="7218f-289">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="7218f-290">有关详细信息，请参阅[BackgroundWorker 组件](../../../../docs/framework/winforms/controls/backgroundworker-component.md)。</span><span class="sxs-lookup"><span data-stu-id="7218f-290">For more information, see [BackgroundWorker Component](../../../../docs/framework/winforms/controls/backgroundworker-component.md).</span></span>  
  
4.  <span data-ttu-id="7218f-291">在属性窗口中，单击事件按钮。</span><span class="sxs-lookup"><span data-stu-id="7218f-291">In the Properties window, click the Events button.</span></span> <span data-ttu-id="7218f-292">附加处理程序<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="7218f-292">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
5.  <span data-ttu-id="7218f-293">打开`MarqueeBorder`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-293">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="7218f-294">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="7218f-294">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  <span data-ttu-id="7218f-295">更改的声明`MarqueeBorder`继承自<xref:System.Windows.Forms.Panel>以及实现`IMarqueeWidget`接口。</span><span class="sxs-lookup"><span data-stu-id="7218f-295">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  <span data-ttu-id="7218f-296">声明用于管理的两个枚举`MarqueeBorder`控件的状态： `MarqueeSpinDirection`，用于确定在其中指示灯"旋转"周围边框的方向和`MarqueeLightShape`，用于确定形状的灯 （方形或循环）。</span><span class="sxs-lookup"><span data-stu-id="7218f-296">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="7218f-297">将这些声明`MarqueeBorder`类声明。</span><span class="sxs-lookup"><span data-stu-id="7218f-297">Place these declarations before the `MarqueeBorder` class declaration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  <span data-ttu-id="7218f-298">声明与公开的属性相对应的实例变量，并在构造函数中对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="7218f-298">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. <span data-ttu-id="7218f-299">实现 `IMarqueeWidget` 接口。</span><span class="sxs-lookup"><span data-stu-id="7218f-299">Implement the `IMarqueeWidget` interface.</span></span>  
  
     <span data-ttu-id="7218f-300">`StartMarquee`并`StopMarquee`方法调用<xref:System.ComponentModel.BackgroundWorker>组件的<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>和<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>方法来启动和停止动画。</span><span class="sxs-lookup"><span data-stu-id="7218f-300">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>  
  
     <span data-ttu-id="7218f-301">因为`MarqueeBorder`控件可以包含子控件`StartMarquee`方法枚举所有子控件并调用`StartMarquee`上即可实现`IMarqueeWidget`。</span><span class="sxs-lookup"><span data-stu-id="7218f-301">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="7218f-302">`StopMarquee`方法具有一个类似的实现。</span><span class="sxs-lookup"><span data-stu-id="7218f-302">The `StopMarquee` method has a similar implementation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. <span data-ttu-id="7218f-303">实现属性访问器。</span><span class="sxs-lookup"><span data-stu-id="7218f-303">Implement the property accessors.</span></span> <span data-ttu-id="7218f-304">`MarqueeBorder`控件具有多个属性用于控制其外观。</span><span class="sxs-lookup"><span data-stu-id="7218f-304">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. <span data-ttu-id="7218f-305">实现的处理程序<xref:System.ComponentModel.BackgroundWorker>组件的<xref:System.ComponentModel.BackgroundWorker.DoWork>和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="7218f-305">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
     <span data-ttu-id="7218f-306"><xref:System.ComponentModel.BackgroundWorker.DoWork>事件处理程序指定的毫秒数将休眠`UpdatePeriod`然后引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件，直到你的代码通过调用停止动画<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>。</span><span class="sxs-lookup"><span data-stu-id="7218f-306">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>  
  
     <span data-ttu-id="7218f-307"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序递增的位置的"基"浅，从其确定其他系统正常运行的浅/深状态，并调用<xref:System.Windows.Forms.Control.Refresh%2A>方法可使控件重绘其自身。</span><span class="sxs-lookup"><span data-stu-id="7218f-307">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. <span data-ttu-id="7218f-308">实现帮助器方法`IsLit`和`DrawLight`。</span><span class="sxs-lookup"><span data-stu-id="7218f-308">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>  
  
     <span data-ttu-id="7218f-309">`IsLit`方法确定给定位置处的光的颜色。</span><span class="sxs-lookup"><span data-stu-id="7218f-309">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="7218f-310">中指定的颜色绘制"点亮"的灯`LightColor`中指定的颜色绘制属性，以及那些"深色"`DarkColor`属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-310">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>  
  
     <span data-ttu-id="7218f-311">`DrawLight`方法绘制使用适当的颜色、 形状和位置的灯。</span><span class="sxs-lookup"><span data-stu-id="7218f-311">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. <span data-ttu-id="7218f-312">重写<xref:System.Windows.Forms.Control.OnLayout%2A>和<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-312">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>  
  
     <span data-ttu-id="7218f-313"><xref:System.Windows.Forms.Control.OnPaint%2A>方法绘制的边缘沿灯`MarqueeBorder`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-313">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>  
  
     <span data-ttu-id="7218f-314">因为<xref:System.Windows.Forms.Control.OnPaint%2A>方法取决于的维度`MarqueeBorder`控件，您需要布局发生更改时调用它。</span><span class="sxs-lookup"><span data-stu-id="7218f-314">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="7218f-315">若要实现此目的，重写<xref:System.Windows.Forms.Control.OnLayout%2A>，并调用<xref:System.Windows.Forms.Control.Refresh%2A>。</span><span class="sxs-lookup"><span data-stu-id="7218f-315">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="7218f-316">创建自定义设计器以隐藏和筛选器属性</span><span class="sxs-lookup"><span data-stu-id="7218f-316">Creating a Custom Designer to Shadow and Filter Properties</span></span>  
 <span data-ttu-id="7218f-317">`MarqueeControlRootDesigner`类提供的根设计器的实现。</span><span class="sxs-lookup"><span data-stu-id="7218f-317">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="7218f-318">除了此设计器中，这对`MarqueeControl`，你将需要专门与相关联的自定义设计`MarqueeBorder`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-318">In addition to this designer, which operates on the `MarqueeControl`, you will need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="7218f-319">此设计器提供了相应的自定义根设计器的上下文中的自定义行为。</span><span class="sxs-lookup"><span data-stu-id="7218f-319">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>  
  
 <span data-ttu-id="7218f-320">具体而言，`MarqueeBorderDesigner`将"隐藏"，并筛选某些属性`MarqueeBorder`控件，更改设计环境与它们交互。</span><span class="sxs-lookup"><span data-stu-id="7218f-320">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>  
  
 <span data-ttu-id="7218f-321">截获对组件的属性访问器的调用被称为"隐藏。</span><span class="sxs-lookup"><span data-stu-id="7218f-321">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="7218f-322">它允许设计器来跟踪用户设置的值，并根据需要将该值传递到正在设计的组件。</span><span class="sxs-lookup"><span data-stu-id="7218f-322">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>  
  
 <span data-ttu-id="7218f-323">对于本例，请<xref:System.Windows.Forms.Control.Visible%2A>和<xref:System.Windows.Forms.Control.Enabled%2A>属性将通过隐藏`MarqueeBorderDesigner`，这样用户将无法进行`MarqueeBorder`控件不可见或设计过程中已禁用。</span><span class="sxs-lookup"><span data-stu-id="7218f-323">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>  
  
 <span data-ttu-id="7218f-324">设计器还可以添加和删除属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-324">Designers can also add and remove properties.</span></span> <span data-ttu-id="7218f-325">对于本例，请<xref:System.Windows.Forms.Control.Padding%2A>属性将在设计时，删除，因为`MarqueeBorder`控件以编程方式设置基于指定的灯大小的填充`LightSize`属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-325">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>  
  
 <span data-ttu-id="7218f-326">类的基类`MarqueeBorderDesigner`是<xref:System.ComponentModel.Design.ComponentDesigner>，其中包含可以更改属性、 属性和控件在设计时公开的事件的方法：</span><span class="sxs-lookup"><span data-stu-id="7218f-326">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 <span data-ttu-id="7218f-327">在更改时使用这些方法的组件的公共接口，必须遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="7218f-327">When changing the public interface of a component using these methods, you must follow these rules:</span></span>  
  
-   <span data-ttu-id="7218f-328">添加或删除中的项`PreFilter`仅方法</span><span class="sxs-lookup"><span data-stu-id="7218f-328">Add or remove items in the `PreFilter` methods only</span></span>  
  
-   <span data-ttu-id="7218f-329">修改中的现有项`PostFilter`仅方法</span><span class="sxs-lookup"><span data-stu-id="7218f-329">Modify existing items in the `PostFilter` methods only</span></span>  
  
-   <span data-ttu-id="7218f-330">始终首次调用基实现`PreFilter`方法</span><span class="sxs-lookup"><span data-stu-id="7218f-330">Always call the base implementation first in the `PreFilter` methods</span></span>  
  
-   <span data-ttu-id="7218f-331">始终上一次调用基实现`PostFilter`方法</span><span class="sxs-lookup"><span data-stu-id="7218f-331">Always call the base implementation last in the `PostFilter` methods</span></span>  
  
 <span data-ttu-id="7218f-332">遵守这些规则可确保在设计时环境中的所有设计器正在设计的所有组件的一致视图。</span><span class="sxs-lookup"><span data-stu-id="7218f-332">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>  
  
 <span data-ttu-id="7218f-333"><xref:System.ComponentModel.Design.ComponentDesigner>类提供用于管理属性的值被隐藏，从而免除了您需要创建特定的实例变量的字典。</span><span class="sxs-lookup"><span data-stu-id="7218f-333">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>  
  
#### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="7218f-334">若要创建自定义设计器为卷影和筛选器属性</span><span class="sxs-lookup"><span data-stu-id="7218f-334">To create a custom designer to shadow and filter properties</span></span>  
  
1.  <span data-ttu-id="7218f-335">右键单击**设计**文件夹并添加新类。</span><span class="sxs-lookup"><span data-stu-id="7218f-335">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="7218f-336">源文件基名称指定为"MarqueeBorderDesigner。"</span><span class="sxs-lookup"><span data-stu-id="7218f-336">Give the source file a base name of "MarqueeBorderDesigner."</span></span>  
  
2.  <span data-ttu-id="7218f-337">打开`MarqueeBorderDesigner`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-337">Open the `MarqueeBorderDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="7218f-338">在该文件的顶部，导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="7218f-338">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  <span data-ttu-id="7218f-339">更改的声明`MarqueeBorderDesigner`从中继承<xref:System.Windows.Forms.Design.ParentControlDesigner>。</span><span class="sxs-lookup"><span data-stu-id="7218f-339">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>  
  
     <span data-ttu-id="7218f-340">因为`MarqueeBorder`控件可以包含子控件`MarqueeBorderDesigner`继承<xref:System.Windows.Forms.Design.ParentControlDesigner>，用于处理父-子交互。</span><span class="sxs-lookup"><span data-stu-id="7218f-340">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  <span data-ttu-id="7218f-341">重写的基实现<xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>。</span><span class="sxs-lookup"><span data-stu-id="7218f-341">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  <span data-ttu-id="7218f-342">实现 <xref:System.Windows.Forms.Control.Enabled%2A> 和 <xref:System.Windows.Forms.Control.Visible%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-342">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="7218f-343">这些实现隐藏控件的属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-343">These implementations shadow the control's properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## <a name="handling-component-changes"></a><span data-ttu-id="7218f-344">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="7218f-344">Handling Component Changes</span></span>  
 <span data-ttu-id="7218f-345">`MarqueeControlRootDesigner`类提供的自定义设计时体验您`MarqueeControl`实例。</span><span class="sxs-lookup"><span data-stu-id="7218f-345">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="7218f-346">大多数设计时功能继承自<xref:System.Windows.Forms.Design.DocumentDesigner>类; 您的代码将实现两个特定自定义： 处理组件更改和添加设计器谓词。</span><span class="sxs-lookup"><span data-stu-id="7218f-346">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class; your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>  
  
 <span data-ttu-id="7218f-347">为用户设计其`MarqueeControl`情况下，根设计器将跟踪更改`MarqueeControl`及其子控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-347">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="7218f-348">在设计时环境提供了一项便利服务<xref:System.ComponentModel.Design.IComponentChangeService>、 跟踪更改到组件的状态。</span><span class="sxs-lookup"><span data-stu-id="7218f-348">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>  
  
 <span data-ttu-id="7218f-349">通过查询与环境获取对此服务的引用<xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-349">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="7218f-350">如果查询成功，您的设计器可以处理程序附加到<xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged>事件并执行任何任务所需在设计时保持一致的状态。</span><span class="sxs-lookup"><span data-stu-id="7218f-350">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>  
  
 <span data-ttu-id="7218f-351">情况下`MarqueeControlRootDesigner`类，将调用<xref:System.Windows.Forms.Control.Refresh%2A>方法在每个`IMarqueeWidget`包含对象`MarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-351">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="7218f-352">这将导致`IMarqueeWidget`对象重绘其自身适当时属性，例如其父级的<xref:System.Windows.Forms.Control.Size%2A>发生更改。</span><span class="sxs-lookup"><span data-stu-id="7218f-352">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>  
  
#### <a name="to-handle-component-changes"></a><span data-ttu-id="7218f-353">若要处理组件更改</span><span class="sxs-lookup"><span data-stu-id="7218f-353">To handle component changes</span></span>  
  
1.  <span data-ttu-id="7218f-354">打开`MarqueeControlRootDesigner`中的源文件**代码编辑器**并重写<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-354">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="7218f-355">调用基实现的<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>并进行查询， <xref:System.ComponentModel.Design.IComponentChangeService>。</span><span class="sxs-lookup"><span data-stu-id="7218f-355">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  <span data-ttu-id="7218f-356">实现<xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7218f-356">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="7218f-357">测试发送组件的类型，如果它是`IMarqueeWidget`，调用其<xref:System.Windows.Forms.Control.Refresh%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-357">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## <a name="adding-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="7218f-358">将设计器谓词添加到自定义设计器</span><span class="sxs-lookup"><span data-stu-id="7218f-358">Adding Designer Verbs to your Custom Designer</span></span>  
 <span data-ttu-id="7218f-359">设计器谓词是链接到一个事件处理程序的菜单命令。</span><span class="sxs-lookup"><span data-stu-id="7218f-359">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="7218f-360">设计器谓词在设计时添加到组件的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="7218f-360">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="7218f-361">有关详细信息，请参阅<xref:System.ComponentModel.Design.DesignerVerb>。</span><span class="sxs-lookup"><span data-stu-id="7218f-361">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>  
  
 <span data-ttu-id="7218f-362">将两个设计器谓词添加到您的设计人员：**运行测试**并**停止测试**。</span><span class="sxs-lookup"><span data-stu-id="7218f-362">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="7218f-363">这些谓词将允许您查看的运行时行为`MarqueeControl`在设计时。</span><span class="sxs-lookup"><span data-stu-id="7218f-363">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="7218f-364">这些谓词将添加到`MarqueeControlRootDesigner`。</span><span class="sxs-lookup"><span data-stu-id="7218f-364">These verbs will be added to the `MarqueeControlRootDesigner`.</span></span>  
  
 <span data-ttu-id="7218f-365">当**运行测试**是调用，则谓词事件处理程序将调用`StartMarquee`方法`MarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-365">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="7218f-366">当**停止测试**是调用，则谓词事件处理程序将调用`StopMarquee`方法`MarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-366">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="7218f-367">实现`StartMarquee`并`StopMarquee`方法的实现包含控件上调用这些方法`IMarqueeWidget`，因此任何包含`IMarqueeWidget`控件还将参与测试。</span><span class="sxs-lookup"><span data-stu-id="7218f-367">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>  
  
#### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="7218f-368">若要将设计器谓词添加到自定义设计器</span><span class="sxs-lookup"><span data-stu-id="7218f-368">To add designer verbs to your custom designers</span></span>  
  
1.  <span data-ttu-id="7218f-369">在中`MarqueeControlRootDesigner`类中，添加事件处理程序名为`OnVerbRunTest`和`OnVerbStopTest`。</span><span class="sxs-lookup"><span data-stu-id="7218f-369">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  <span data-ttu-id="7218f-370">将这些事件处理程序连接到其相应设计器谓词。</span><span class="sxs-lookup"><span data-stu-id="7218f-370">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="7218f-371">`MarqueeControlRootDesigner` 继承<xref:System.ComponentModel.Design.DesignerVerbCollection>从其基类。</span><span class="sxs-lookup"><span data-stu-id="7218f-371">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="7218f-372">您将创建两个新<xref:System.ComponentModel.Design.DesignerVerb>对象，并将其添加到此集合中<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-372">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## <a name="creating-a-custom-uitypeeditor"></a><span data-ttu-id="7218f-373">创建自定义 UITypeEditor</span><span class="sxs-lookup"><span data-stu-id="7218f-373">Creating a Custom UITypeEditor</span></span>  
 <span data-ttu-id="7218f-374">时创建用户提供自定义设计时体验，它通常是需要创建与属性窗口的自定义式交互。</span><span class="sxs-lookup"><span data-stu-id="7218f-374">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="7218f-375">您可以完成此操作通过创建<xref:System.Drawing.Design.UITypeEditor>。</span><span class="sxs-lookup"><span data-stu-id="7218f-375">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span> <span data-ttu-id="7218f-376">有关详细信息，请参阅[如何： 创建 UI 类型编辑器](https://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd)。</span><span class="sxs-lookup"><span data-stu-id="7218f-376">For more information, see [How to: Create a UI Type Editor](https://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd).</span></span>  
  
 <span data-ttu-id="7218f-377">`MarqueeBorder`控件公开多个属性在属性窗口中的。</span><span class="sxs-lookup"><span data-stu-id="7218f-377">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="7218f-378">这些属性的两个`MarqueeSpinDirection`和`MarqueeLightShape`枚举表示。</span><span class="sxs-lookup"><span data-stu-id="7218f-378">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="7218f-379">举例说明的 UI 类型编辑器，使用`MarqueeLightShape`属性将具有一个关联<xref:System.Drawing.Design.UITypeEditor>类。</span><span class="sxs-lookup"><span data-stu-id="7218f-379">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>  
  
#### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="7218f-380">若要创建自定义 UI 类型编辑器</span><span class="sxs-lookup"><span data-stu-id="7218f-380">To create a custom UI type editor</span></span>  
  
1.  <span data-ttu-id="7218f-381">打开`MarqueeBorder`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-381">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="7218f-382">中的定义`MarqueeBorder`类中，声明一个名为类`LightShapeEditor`派生<xref:System.Drawing.Design.UITypeEditor>。</span><span class="sxs-lookup"><span data-stu-id="7218f-382">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  <span data-ttu-id="7218f-383">声明<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>调用的实例变量`editorService`。</span><span class="sxs-lookup"><span data-stu-id="7218f-383">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  <span data-ttu-id="7218f-384">重写 <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-384">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="7218f-385">此实现返回<xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>，它将告诉如何显示在设计环境`LightShapeEditor`。</span><span class="sxs-lookup"><span data-stu-id="7218f-385">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  <span data-ttu-id="7218f-386">重写 <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-386">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="7218f-387">此实现查询的设计环境<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>对象。</span><span class="sxs-lookup"><span data-stu-id="7218f-387">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="7218f-388">如果成功，它将创建`LightShapeSelectionControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-388">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="7218f-389"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>方法调用以启动`LightShapeEditor`。</span><span class="sxs-lookup"><span data-stu-id="7218f-389">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="7218f-390">此调用的返回值返回到设计环境。</span><span class="sxs-lookup"><span data-stu-id="7218f-390">The return value from this invocation is returned to the design environment.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="7218f-391">为自定义 UITypeEditor 创建视图控件</span><span class="sxs-lookup"><span data-stu-id="7218f-391">Creating a View Control for your Custom UITypeEditor</span></span>  
  
1.  <span data-ttu-id="7218f-392">`MarqueeLightShape`属性支持两种类型的光线的形状：`Square`和`Circle`。</span><span class="sxs-lookup"><span data-stu-id="7218f-392">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="7218f-393">您将创建专用于在属性窗口中以图形方式显示这些值的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-393">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="7218f-394">此自定义控件将由你<xref:System.Drawing.Design.UITypeEditor>与属性窗口进行交互。</span><span class="sxs-lookup"><span data-stu-id="7218f-394">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>  
  
#### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="7218f-395">若要创建自定义 UI 类型编辑器视图控件</span><span class="sxs-lookup"><span data-stu-id="7218f-395">To create a view control for your custom UI type editor</span></span>  
  
1.  <span data-ttu-id="7218f-396">添加一个新<xref:System.Windows.Forms.UserControl>项`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-396">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="7218f-397">新的源文件基名称指定为"LightShapeSelectionControl。"</span><span class="sxs-lookup"><span data-stu-id="7218f-397">Give the new source file a base name of "LightShapeSelectionControl."</span></span>  
  
2.  <span data-ttu-id="7218f-398">将两个<xref:System.Windows.Forms.Panel>控件从**工具箱**拖动到`LightShapeSelectionControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-398">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="7218f-399">命名它们`squarePanel`和`circlePanel`。</span><span class="sxs-lookup"><span data-stu-id="7218f-399">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="7218f-400">排列它们并排显示。</span><span class="sxs-lookup"><span data-stu-id="7218f-400">Arrange them side by side.</span></span> <span data-ttu-id="7218f-401">设置<xref:System.Windows.Forms.Control.Size%2A>属性均<xref:System.Windows.Forms.Panel>控件添加到 （60，60）。</span><span class="sxs-lookup"><span data-stu-id="7218f-401">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to (60, 60).</span></span> <span data-ttu-id="7218f-402">设置<xref:System.Windows.Forms.Control.Location%2A>属性的`squarePanel`控制对 （8，10）。</span><span class="sxs-lookup"><span data-stu-id="7218f-402">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to (8, 10).</span></span> <span data-ttu-id="7218f-403">设置<xref:System.Windows.Forms.Control.Location%2A>属性的`circlePanel`控制对 （80，10）。</span><span class="sxs-lookup"><span data-stu-id="7218f-403">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to (80, 10).</span></span> <span data-ttu-id="7218f-404">最后，设置<xref:System.Windows.Forms.Control.Size%2A>属性的`LightShapeSelectionControl`到 150 (80）。</span><span class="sxs-lookup"><span data-stu-id="7218f-404">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to (150, 80).</span></span>  
  
3.  <span data-ttu-id="7218f-405">打开`LightShapeSelectionControl`中的源文件**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7218f-405">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="7218f-406">该文件顶部，导入<xref:System.Windows.Forms.Design?displayProperty=nameWithType>命名空间：</span><span class="sxs-lookup"><span data-stu-id="7218f-406">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  <span data-ttu-id="7218f-407">实现<xref:System.Windows.Forms.Control.Click>事件处理程序`squarePanel`和`circlePanel`控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-407">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="7218f-408">这些方法调用<xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A>若要结束自定义<xref:System.Drawing.Design.UITypeEditor>编辑会话。</span><span class="sxs-lookup"><span data-stu-id="7218f-408">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  <span data-ttu-id="7218f-409">声明<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>调用的实例变量`editorService`。</span><span class="sxs-lookup"><span data-stu-id="7218f-409">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  <span data-ttu-id="7218f-410">声明`MarqueeLightShape`调用的实例变量`lightShapeValue`。</span><span class="sxs-lookup"><span data-stu-id="7218f-410">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  <span data-ttu-id="7218f-411">在中`LightShapeSelectionControl`构造函数中，附加<xref:System.Windows.Forms.Control.Click>的事件处理程序`squarePanel`并`circlePanel`控件的<xref:System.Windows.Forms.Control.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="7218f-411">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="7218f-412">另外，定义将分配一个构造函数重载`MarqueeLightShape`到设计环境中的值`lightShapeValue`字段。</span><span class="sxs-lookup"><span data-stu-id="7218f-412">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  <span data-ttu-id="7218f-413">在中<xref:System.ComponentModel.Component.Dispose%2A>方法中，分离<xref:System.Windows.Forms.Control.Click>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7218f-413">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  <span data-ttu-id="7218f-414">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="7218f-414">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="7218f-415">打开 LightShapeSelectionControl.Designer.cs 或 LightShapeSelectionControl.Designer.vb 文件，并删除的默认定义<xref:System.ComponentModel.Component.Dispose%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-415">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>  
  
5.  <span data-ttu-id="7218f-416">实现 `LightShape` 属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-416">Implement the `LightShape` property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  <span data-ttu-id="7218f-417">重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7218f-417">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="7218f-418">此实现将绘制一个实心的方形和圆。</span><span class="sxs-lookup"><span data-stu-id="7218f-418">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="7218f-419">它还将通过绘制一个形状或其他周围的边框来突出显示所选的值。</span><span class="sxs-lookup"><span data-stu-id="7218f-419">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## <a name="testing-your-custom-control-in-the-designer"></a><span data-ttu-id="7218f-420">在设计器中测试自定义控件</span><span class="sxs-lookup"><span data-stu-id="7218f-420">Testing your Custom Control in the Designer</span></span>  
 <span data-ttu-id="7218f-421">此时，您可以构建`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="7218f-421">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="7218f-422">通过创建继承的控件来测试您的实现`MarqueeControl`类并在窗体上使用它。</span><span class="sxs-lookup"><span data-stu-id="7218f-422">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>  
  
#### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="7218f-423">若要创建自定义的 MarqueeControl 实现</span><span class="sxs-lookup"><span data-stu-id="7218f-423">To create a custom MarqueeControl implementation</span></span>  
  
1.  <span data-ttu-id="7218f-424">在 Windows 窗体设计器中打开 `DemoMarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-424">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="7218f-425">这将创建的实例`DemoMarqueeControl`类型并将其显示实例中`MarqueeControlRootDesigner`类型。</span><span class="sxs-lookup"><span data-stu-id="7218f-425">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>  
  
2.  <span data-ttu-id="7218f-426">在中**工具箱**，打开**MarqueeControlLibrary 组件**选项卡。你将看到`MarqueeBorder`和`MarqueeText`控件可供选择。</span><span class="sxs-lookup"><span data-stu-id="7218f-426">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>  
  
3.  <span data-ttu-id="7218f-427">实例拖`MarqueeBorder`控件拖动到`DemoMarqueeControl`设计图面。</span><span class="sxs-lookup"><span data-stu-id="7218f-427">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="7218f-428">停靠此`MarqueeBorder`到父控件的控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-428">Dock this `MarqueeBorder` control to the parent control.</span></span>  
  
4.  <span data-ttu-id="7218f-429">实例拖`MarqueeText`控件拖动到`DemoMarqueeControl`设计图面。</span><span class="sxs-lookup"><span data-stu-id="7218f-429">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>  
  
5.  <span data-ttu-id="7218f-430">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="7218f-430">Build the solution.</span></span>  
  
6.  <span data-ttu-id="7218f-431">右键单击`DemoMarqueeControl`并从快捷菜单选择**运行测试**选项来启动动画。</span><span class="sxs-lookup"><span data-stu-id="7218f-431">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="7218f-432">单击**停止测试**停止动画。</span><span class="sxs-lookup"><span data-stu-id="7218f-432">Click **Stop Test** to stop the animation.</span></span>  
  
7.  <span data-ttu-id="7218f-433">打开**Form1**在设计视图中。</span><span class="sxs-lookup"><span data-stu-id="7218f-433">Open **Form1** in Design view.</span></span>  
  
8.  <span data-ttu-id="7218f-434">放置两个<xref:System.Windows.Forms.Button>窗体控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-434">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="7218f-435">命名它们`startButton`和`stopButton`，并将更改<xref:System.Windows.Forms.Control.Text%2A>属性值复制到**启动**并**停止**分别。</span><span class="sxs-lookup"><span data-stu-id="7218f-435">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>  
  
9. <span data-ttu-id="7218f-436">实现<xref:System.Windows.Forms.Control.Click>两个事件处理程序<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-436">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>  
  
10. <span data-ttu-id="7218f-437">在中**工具箱**，打开**MarqueeControlTest 组件**选项卡。你将看到`DemoMarqueeControl`可供选择。</span><span class="sxs-lookup"><span data-stu-id="7218f-437">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>  
  
11. <span data-ttu-id="7218f-438">实例拖`DemoMarqueeControl`拖到**Form1**设计图面。</span><span class="sxs-lookup"><span data-stu-id="7218f-438">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>  
  
12. <span data-ttu-id="7218f-439">在中<xref:System.Windows.Forms.Control.Click>事件处理程序调用`Start`并`Stop`上的方法`DemoMarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-439">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>  
  
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
  
1.  <span data-ttu-id="7218f-440">设置`MarqueeControlTest`项目为启动项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="7218f-440">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="7218f-441">你将看到显示的窗体在`DemoMarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-441">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="7218f-442">单击**启动**按钮以启动动画。</span><span class="sxs-lookup"><span data-stu-id="7218f-442">Click the **Start** button to start the animation.</span></span> <span data-ttu-id="7218f-443">您应该看到灯光移动边框和闪烁的文本。</span><span class="sxs-lookup"><span data-stu-id="7218f-443">You should see the text flashing and the lights moving around the border.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7218f-444">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7218f-444">Next Steps</span></span>  
 <span data-ttu-id="7218f-445">`MarqueeControlLibrary`演示了一个简单的自定义控件和关联的设计器实现。</span><span class="sxs-lookup"><span data-stu-id="7218f-445">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="7218f-446">你可以多种方式来进行此示例更复杂：</span><span class="sxs-lookup"><span data-stu-id="7218f-446">You can make this sample more sophisticated in several ways:</span></span>  
  
-   <span data-ttu-id="7218f-447">更改的属性值`DemoMarqueeControl`在设计器中。</span><span class="sxs-lookup"><span data-stu-id="7218f-447">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="7218f-448">添加更多`MarqueBorder`控制并将其停靠在其父实例中以创建嵌套的效果。</span><span class="sxs-lookup"><span data-stu-id="7218f-448">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="7218f-449">使用不同的设置`UpdatePeriod`和 light 相关的属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-449">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>  
  
-   <span data-ttu-id="7218f-450">编写您自己的实现的`IMarqueeWidget`。</span><span class="sxs-lookup"><span data-stu-id="7218f-450">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="7218f-451">例如，可以包含多个映像创建闪烁的"neon 登录"或经过动画处理的登录。</span><span class="sxs-lookup"><span data-stu-id="7218f-451">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>  
  
-   <span data-ttu-id="7218f-452">进一步自定义设计时体验。</span><span class="sxs-lookup"><span data-stu-id="7218f-452">Further customize the design-time experience.</span></span> <span data-ttu-id="7218f-453">您可以尝试隐藏更多属性比<xref:System.Windows.Forms.Control.Enabled%2A>和<xref:System.Windows.Forms.Control.Visible%2A>，可以添加新属性。</span><span class="sxs-lookup"><span data-stu-id="7218f-453">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="7218f-454">添加新的设计器谓词来简化常见任务，例如停靠子控件。</span><span class="sxs-lookup"><span data-stu-id="7218f-454">Add new designer verbs to simplify common tasks like docking child controls.</span></span>  
  
-   <span data-ttu-id="7218f-455">许可证`MarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="7218f-455">License the `MarqueeControl`.</span></span> <span data-ttu-id="7218f-456">有关详细信息，请参阅[如何： 许可组件和控件](https://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)。</span><span class="sxs-lookup"><span data-stu-id="7218f-456">For more information, see [How to: License Components and Controls](https://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57).</span></span>  
  
-   <span data-ttu-id="7218f-457">控制如何序列化您的控件以及如何为其生成代码。</span><span class="sxs-lookup"><span data-stu-id="7218f-457">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="7218f-458">有关详细信息，请参阅[动态源代码生成和编译](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)。</span><span class="sxs-lookup"><span data-stu-id="7218f-458">For more information, see [Dynamic Source Code Generation and Compilation](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7218f-459">请参阅</span><span class="sxs-lookup"><span data-stu-id="7218f-459">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Design.ParentControlDesigner>  
 <xref:System.Windows.Forms.Design.DocumentDesigner>  
 <xref:System.ComponentModel.Design.IRootDesigner>  
 <xref:System.ComponentModel.Design.DesignerVerb>  
 <xref:System.Drawing.Design.UITypeEditor>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="7218f-460">如何：创建利用设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7218f-460">How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features</span></span>](https://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)  
 [<span data-ttu-id="7218f-461">扩展设计时支持</span><span class="sxs-lookup"><span data-stu-id="7218f-461">Extending Design-Time Support</span></span>](https://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="7218f-462">自定义设计器</span><span class="sxs-lookup"><span data-stu-id="7218f-462">Custom Designers</span></span>](https://msdn.microsoft.com/library/ca11988e-d38e-44d8-a05d-71362ae7844d)  
 [<span data-ttu-id="7218f-463">.NET 形状库： 示例设计器</span><span class="sxs-lookup"><span data-stu-id="7218f-463">.NET Shape Library: A Sample Designer</span></span>](http://windowsforms.net/articles/shapedesigner.aspx)
