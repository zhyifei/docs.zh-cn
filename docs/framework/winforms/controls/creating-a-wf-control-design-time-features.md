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
ms.openlocfilehash: 733f22c122dd6acdad41371419375e55e977c016
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039930"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a><span data-ttu-id="792ce-102">演练：创建一个利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="792ce-102">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>

<span data-ttu-id="792ce-103">通过创作关联的自定义设计器, 可以增强自定义控件的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="792ce-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>

<span data-ttu-id="792ce-104">本演练演示如何为自定义控件创建自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="792ce-104">This walkthrough illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="792ce-105">您将实现一个`MarqueeControl`类型和一个名`MarqueeControlRootDesigner`为的关联设计器类。</span><span class="sxs-lookup"><span data-stu-id="792ce-105">You will implement a `MarqueeControl` type and an associated designer class, called `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="792ce-106">该`MarqueeControl`类型实现的显示类似于剧院天棚, 带有动画光源和闪烁文本。</span><span class="sxs-lookup"><span data-stu-id="792ce-106">The `MarqueeControl` type implements a display similar to a theater marquee, with animated lights and flashing text.</span></span>

<span data-ttu-id="792ce-107">此控件的设计器与设计环境交互, 以提供自定义的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="792ce-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="792ce-108">使用自定义设计器, 可以在许多组合`MarqueeControl`中使用动态光源和闪烁文本来组装自定义实现。</span><span class="sxs-lookup"><span data-stu-id="792ce-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="792ce-109">可以像任何其他 Windows 窗体控件一样使用窗体上的组合控件。</span><span class="sxs-lookup"><span data-stu-id="792ce-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>

<span data-ttu-id="792ce-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="792ce-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="792ce-111">创建项目</span><span class="sxs-lookup"><span data-stu-id="792ce-111">Creating the Project</span></span>

- <span data-ttu-id="792ce-112">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="792ce-112">Creating a Control Library Project</span></span>

- <span data-ttu-id="792ce-113">引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="792ce-113">Referencing the Custom Control Project</span></span>

- <span data-ttu-id="792ce-114">定义自定义控件及其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-114">Defining a Custom Control and Its Custom Designer</span></span>

- <span data-ttu-id="792ce-115">创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="792ce-115">Creating an Instance of Your Custom Control</span></span>

- <span data-ttu-id="792ce-116">设置项目以进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="792ce-116">Setting Up the Project for Design-Time Debugging</span></span>

- <span data-ttu-id="792ce-117">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="792ce-117">Implementing Your Custom Control</span></span>

- <span data-ttu-id="792ce-118">为自定义控件创建子控件</span><span class="sxs-lookup"><span data-stu-id="792ce-118">Creating a Child Control for Your Custom Control</span></span>

- <span data-ttu-id="792ce-119">创建 MarqueeBorder 子控件</span><span class="sxs-lookup"><span data-stu-id="792ce-119">Create the MarqueeBorder Child Control</span></span>

- <span data-ttu-id="792ce-120">创建用于隐藏和筛选属性的自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-120">Creating a Custom Designer to Shadow and Filter Properties</span></span>

- <span data-ttu-id="792ce-121">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="792ce-121">Handling Component Changes</span></span>

- <span data-ttu-id="792ce-122">将设计器谓词添加到自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-122">Adding Designer Verbs to your Custom Designer</span></span>

- <span data-ttu-id="792ce-123">创建自定义 UITypeEditor</span><span class="sxs-lookup"><span data-stu-id="792ce-123">Creating a Custom UITypeEditor</span></span>

- <span data-ttu-id="792ce-124">在设计器中测试自定义控件</span><span class="sxs-lookup"><span data-stu-id="792ce-124">Testing your Custom Control in the Designer</span></span>

<span data-ttu-id="792ce-125">完成后, 自定义控件将如下所示:</span><span class="sxs-lookup"><span data-stu-id="792ce-125">When you are finished, your custom control will look something like the following:</span></span>

![该应用显示了文本和 "开始" 和 "停止" 按钮的选框。](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

<span data-ttu-id="792ce-127">有关完整的代码列表, 请[参阅如何:创建利用设计时功能](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="792ce-127">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>


## <a name="prerequisites"></a><span data-ttu-id="792ce-128">系统必备</span><span class="sxs-lookup"><span data-stu-id="792ce-128">Prerequisites</span></span>

<span data-ttu-id="792ce-129">若要完成本演练, 你将需要 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="792ce-129">In order to complete this walkthrough, you'll need Visual Studio.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="792ce-130">创建项目</span><span class="sxs-lookup"><span data-stu-id="792ce-130">Creating the Project</span></span>

<span data-ttu-id="792ce-131">第一步是创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="792ce-131">The first step is to create the application project.</span></span> <span data-ttu-id="792ce-132">将使用此项目生成承载自定义控件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="792ce-132">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="792ce-133">打开 Visual Studio 并创建一个名为 "MarqueeControlTest" 的 Windows 窗体应用程序项目 (**文件** > **新** > **项目** > **视觉对象C#** 或**Visual Basic**  > **经典桌面** **Windows 窗体应用程序)。**  > </span><span class="sxs-lookup"><span data-stu-id="792ce-133">Open Visual Studio and create a Windows Forms Application project called "MarqueeControlTest" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="creating-a-control-library-project"></a><span data-ttu-id="792ce-134">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="792ce-134">Creating a Control Library Project</span></span>

<span data-ttu-id="792ce-135">下一步是创建控件库项目。</span><span class="sxs-lookup"><span data-stu-id="792ce-135">The next step is to create the control library project.</span></span> <span data-ttu-id="792ce-136">您将创建一个新的自定义控件及其相应的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="792ce-136">You will create a new custom control and its corresponding custom designer.</span></span>

### <a name="to-create-the-control-library-project"></a><span data-ttu-id="792ce-137">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="792ce-137">To create the control library project</span></span>

1. <span data-ttu-id="792ce-138">将 Windows 窗体控件库项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="792ce-138">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="792ce-139">将项目命名为 "MarqueeControlLibrary"。</span><span class="sxs-lookup"><span data-stu-id="792ce-139">Name the project "MarqueeControlLibrary."</span></span>

2. <span data-ttu-id="792ce-140">使用**解决方案资源管理器**, 通过删除名为 "UserControl1.cs" 或 "UserControl1" 的源文件来删除项目的默认控件, 具体取决于您选择的语言。</span><span class="sxs-lookup"><span data-stu-id="792ce-140">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span> <span data-ttu-id="792ce-141">有关详细信息，请参阅[如何：删除、删除和排除项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="792ce-141">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="792ce-142">向`MarqueeControlLibrary`项目中<xref:System.Windows.Forms.UserControl>添加新项。</span><span class="sxs-lookup"><span data-stu-id="792ce-142">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="792ce-143">为新的源文件命名为 "MarqueeControl" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="792ce-143">Give the new source file a base name of "MarqueeControl."</span></span>

4. <span data-ttu-id="792ce-144">使用**解决方案资源管理器**在`MarqueeControlLibrary`项目中创建一个新文件夹。</span><span class="sxs-lookup"><span data-stu-id="792ce-144">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="792ce-145">有关详细信息，请参阅[如何：添加新项目项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="792ce-145">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="792ce-146">将新文件夹命名为 "Design"。</span><span class="sxs-lookup"><span data-stu-id="792ce-146">Name the new folder "Design."</span></span>

5. <span data-ttu-id="792ce-147">右键单击**设计**文件夹并添加一个新类。</span><span class="sxs-lookup"><span data-stu-id="792ce-147">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="792ce-148">为源文件指定基名称 "MarqueeControlRootDesigner"。</span><span class="sxs-lookup"><span data-stu-id="792ce-148">Give the source file a base name of "MarqueeControlRootDesigner."</span></span>

6. <span data-ttu-id="792ce-149">你将需要使用来自 system.object 程序集的类型, 因此请将此引用添加到`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="792ce-149">You will need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="792ce-150">若要使用 System.web 程序集, 你的项目必须面向 .NET Framework 的完整版本, 而不是 .NET Framework 的客户端配置文件。</span><span class="sxs-lookup"><span data-stu-id="792ce-150">To use the System.Design assembly, your project must target the full version of the .NET Framework, not the .NET Framework Client Profile.</span></span> <span data-ttu-id="792ce-151">若要更改目标框架, 请[参阅如何:面向 .NET Framework 的某个版本](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)。</span><span class="sxs-lookup"><span data-stu-id="792ce-151">To change the target framework, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

## <a name="referencing-the-custom-control-project"></a><span data-ttu-id="792ce-152">引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="792ce-152">Referencing the Custom Control Project</span></span>

<span data-ttu-id="792ce-153">您将使用该`MarqueeControlTest`项目来测试自定义控件。</span><span class="sxs-lookup"><span data-stu-id="792ce-153">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="792ce-154">向`MarqueeControlLibrary`程序集添加项目引用时, 测试项目将会感知自定义控件。</span><span class="sxs-lookup"><span data-stu-id="792ce-154">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>

### <a name="to-reference-the-custom-control-project"></a><span data-ttu-id="792ce-155">引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="792ce-155">To reference the custom control project</span></span>

- <span data-ttu-id="792ce-156">在项目中, 添加`MarqueeControlLibrary`对程序集的项目引用。 `MarqueeControlTest`</span><span class="sxs-lookup"><span data-stu-id="792ce-156">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="792ce-157">请确保使用 "**添加引用**" 对话框中的 "**项目**" 选项卡, 而`MarqueeControlLibrary`不是直接引用程序集。</span><span class="sxs-lookup"><span data-stu-id="792ce-157">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>

## <a name="defining-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="792ce-158">定义自定义控件及其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-158">Defining a Custom Control and Its Custom Designer</span></span>
 <span data-ttu-id="792ce-159">自定义控件将派生<xref:System.Windows.Forms.UserControl>自类。</span><span class="sxs-lookup"><span data-stu-id="792ce-159">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="792ce-160">这允许控件包含其他控件, 并使控件具有大量默认功能。</span><span class="sxs-lookup"><span data-stu-id="792ce-160">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>

 <span data-ttu-id="792ce-161">自定义控件将具有关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="792ce-161">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="792ce-162">这允许您创建专为自定义控件定制的独特设计体验。</span><span class="sxs-lookup"><span data-stu-id="792ce-162">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>

 <span data-ttu-id="792ce-163">使用<xref:System.ComponentModel.DesignerAttribute>类将控件与其设计器相关联。</span><span class="sxs-lookup"><span data-stu-id="792ce-163">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="792ce-164">由于您正在开发自定义控件的整个设计时行为, 因此自定义设计器将实现该<xref:System.ComponentModel.Design.IRootDesigner>接口。</span><span class="sxs-lookup"><span data-stu-id="792ce-164">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>

### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="792ce-165">定义自定义控件及其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-165">To define a custom control and its custom designer</span></span>

1. <span data-ttu-id="792ce-166">在**代码编辑器**中打开源文件。`MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-166">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="792ce-167">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="792ce-167">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <span data-ttu-id="792ce-168">将添加<xref:System.ComponentModel.DesignerAttribute> `MarqueeControl`到类声明中。</span><span class="sxs-lookup"><span data-stu-id="792ce-168">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="792ce-169">这会将自定义控件与其设计器相关联。</span><span class="sxs-lookup"><span data-stu-id="792ce-169">This associates the custom control with its designer.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. <span data-ttu-id="792ce-170">在**代码编辑器**中打开源文件。`MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="792ce-170">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="792ce-171">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="792ce-171">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. <span data-ttu-id="792ce-172">更改的`MarqueeControlRootDesigner`声明以<xref:System.Windows.Forms.Design.DocumentDesigner>从类继承。</span><span class="sxs-lookup"><span data-stu-id="792ce-172">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="792ce-173">应用, 以指定与工具箱的设计器交互。 <xref:System.ComponentModel.ToolboxItemFilterAttribute></span><span class="sxs-lookup"><span data-stu-id="792ce-173">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>

     <span data-ttu-id="792ce-174">**注意**`MarqueeControlRootDesigner`类的定义已包含在名为 "MarqueeControlLibrary" 的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="792ce-174">**Note** The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called "MarqueeControlLibrary.Design."</span></span> <span data-ttu-id="792ce-175">此声明将设计器置于为设计相关类型保留的特殊命名空间中。</span><span class="sxs-lookup"><span data-stu-id="792ce-175">This declaration places the designer in a special namespace reserved for design-related types.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. <span data-ttu-id="792ce-176">定义`MarqueeControlRootDesigner`类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="792ce-176">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="792ce-177">在构造函数主体中插入语句。<xref:System.Diagnostics.Trace.WriteLine%2A></span><span class="sxs-lookup"><span data-stu-id="792ce-177">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="792ce-178">这对于调试而言很有用。</span><span class="sxs-lookup"><span data-stu-id="792ce-178">This will be useful for debugging purposes.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="creating-an-instance-of-your-custom-control"></a><span data-ttu-id="792ce-179">创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="792ce-179">Creating an Instance of Your Custom Control</span></span>
 <span data-ttu-id="792ce-180">若要观察控件的自定义设计时行为, 请将控件的一个实例放置在 project 中`MarqueeControlTest`的窗体上。</span><span class="sxs-lookup"><span data-stu-id="792ce-180">To observe the custom design-time behavior of your control, you will place an instance of your control on the form in `MarqueeControlTest` project.</span></span>

### <a name="to-create-an-instance-of-your-custom-control"></a><span data-ttu-id="792ce-181">创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="792ce-181">To create an instance of your custom control</span></span>

1. <span data-ttu-id="792ce-182">向`MarqueeControlTest`项目中<xref:System.Windows.Forms.UserControl>添加新项。</span><span class="sxs-lookup"><span data-stu-id="792ce-182">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="792ce-183">为新的源文件命名为 "DemoMarqueeControl" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="792ce-183">Give the new source file a base name of "DemoMarqueeControl."</span></span>

2. <span data-ttu-id="792ce-184">在**代码编辑器**中打开文件。`DemoMarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-184">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="792ce-185">在该文件的顶部, 导入`MarqueeControlLibrary`命名空间:</span><span class="sxs-lookup"><span data-stu-id="792ce-185">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>

```vb
Imports MarqueeControlLibrary
```

```csharp
using MarqueeControlLibrary;
```

1. <span data-ttu-id="792ce-186">更改的`DemoMarqueeControl`声明以`MarqueeControl`从类继承。</span><span class="sxs-lookup"><span data-stu-id="792ce-186">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>

2. <span data-ttu-id="792ce-187">生成项目。</span><span class="sxs-lookup"><span data-stu-id="792ce-187">Build the project.</span></span>

3. <span data-ttu-id="792ce-188">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="792ce-188">Open `Form1` in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="792ce-189">找到 "**工具箱**" 中的 " **MarqueeControlTest 组件**" 选项卡并将其打开。</span><span class="sxs-lookup"><span data-stu-id="792ce-189">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="792ce-190">将从 "工具箱" 拖到窗体上。 `DemoMarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-190">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="792ce-191">生成项目。</span><span class="sxs-lookup"><span data-stu-id="792ce-191">Build the project.</span></span>

## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="792ce-192">设置项目以进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="792ce-192">Setting Up the Project for Design-Time Debugging</span></span>

<span data-ttu-id="792ce-193">开发自定义设计时体验时, 必须调试控件和组件。</span><span class="sxs-lookup"><span data-stu-id="792ce-193">When you are developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="792ce-194">可以通过一种简单的方式将项目设置为允许在设计时进行调试。</span><span class="sxs-lookup"><span data-stu-id="792ce-194">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="792ce-195">有关详细信息，请参见[演练：在设计时](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)调试自定义 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="792ce-195">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="792ce-196">设置项目以进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="792ce-196">To set up the project for design-time debugging</span></span>

1. <span data-ttu-id="792ce-197">右键单击该项目`MarqueeControlLibrary` , 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="792ce-197">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>

2. <span data-ttu-id="792ce-198">在 "MarqueeControlLibrary 属性页" 对话框中, 选择 "**调试**" 页。</span><span class="sxs-lookup"><span data-stu-id="792ce-198">In the "MarqueeControlLibrary Property Pages" dialog box, select the **Debug** page.</span></span>

3. <span data-ttu-id="792ce-199">在 "**启动操作**" 部分中, 选择 "**启动外部程序**"。</span><span class="sxs-lookup"><span data-stu-id="792ce-199">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="792ce-200">你将调试单独的 visual studio 实例, 因此单击 "visual![](./media/visual-studio-ellipsis-button.png)studio" 属性窗口中的省略号按钮 (...), 浏览 visual studio IDE。</span><span class="sxs-lookup"><span data-stu-id="792ce-200">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="792ce-201">可执行文件的名称为 devenv, 如果你已安装到默认位置, 则该文件的路径为%programfiles%\Microsoft Visual Studio 9.0 \ Common7\IDE\devenv.exe。</span><span class="sxs-lookup"><span data-stu-id="792ce-201">The name of the executable file is devenv.exe, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

4. <span data-ttu-id="792ce-202">单击 "确定" 关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="792ce-202">Click OK to close the dialog box.</span></span>

5. <span data-ttu-id="792ce-203">右键单击该`MarqueeControlLibrary`项目并选择 "设为启动项目", 以启用此调试配置。</span><span class="sxs-lookup"><span data-stu-id="792ce-203">Right-click the `MarqueeControlLibrary` project and select "Set as StartUp Project" to enable this debugging configuration.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="792ce-204">检查点</span><span class="sxs-lookup"><span data-stu-id="792ce-204">Checkpoint</span></span>

<span data-ttu-id="792ce-205">你现在已准备好调试自定义控件的设计时行为。</span><span class="sxs-lookup"><span data-stu-id="792ce-205">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="792ce-206">确定正确设置了调试环境后, 将测试自定义控件和自定义设计器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="792ce-206">Once you have determined that the debugging environment is set up correctly, you will test the association between the custom control and the custom designer.</span></span>

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="792ce-207">测试调试环境和设计器关联</span><span class="sxs-lookup"><span data-stu-id="792ce-207">To test the debugging environment and the designer association</span></span>

1. <span data-ttu-id="792ce-208">在代码**编辑器**中打开<xref:System.Diagnostics.Trace.WriteLine%2A> 源文件,并在语句中放置一个断点。`MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="792ce-208">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>

2. <span data-ttu-id="792ce-209">按 F5 启动调试会话。</span><span class="sxs-lookup"><span data-stu-id="792ce-209">Press F5 to start the debugging session.</span></span> <span data-ttu-id="792ce-210">请注意, 将创建 Visual Studio 的新实例。</span><span class="sxs-lookup"><span data-stu-id="792ce-210">Note that a new instance of Visual Studio is created.</span></span>

3. <span data-ttu-id="792ce-211">在 Visual Studio 的新实例中, 打开 "MarqueeControlTest" 解决方案。</span><span class="sxs-lookup"><span data-stu-id="792ce-211">In the new instance of Visual Studio, open the "MarqueeControlTest" solution.</span></span> <span data-ttu-id="792ce-212">通过从 "**文件**" 菜单中选择 "**最近使用的项目**", 可以轻松地找到解决方案。</span><span class="sxs-lookup"><span data-stu-id="792ce-212">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="792ce-213">"MarqueeControlTest" 解决方案文件将作为最近使用过的文件列出。</span><span class="sxs-lookup"><span data-stu-id="792ce-213">The "MarqueeControlTest.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="792ce-214">`DemoMarqueeControl`在设计器中打开。</span><span class="sxs-lookup"><span data-stu-id="792ce-214">Open the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="792ce-215">请注意, Visual Studio 的调试实例获取焦点, 并在断点处停止执行。</span><span class="sxs-lookup"><span data-stu-id="792ce-215">Note that the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="792ce-216">按 F5 继续调试会话。</span><span class="sxs-lookup"><span data-stu-id="792ce-216">Press F5 to continue the debugging session.</span></span>

<span data-ttu-id="792ce-217">此时, 所有内容都已准备就绪, 可用于开发和调试自定义控件及其关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="792ce-217">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="792ce-218">本演练的其余部分将重点介绍实现控件和设计器功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="792ce-218">The remainder of this walkthrough will concentrate on the details of implementing features of the control and the designer.</span></span>

## <a name="implementing-your-custom-control"></a><span data-ttu-id="792ce-219">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="792ce-219">Implementing Your Custom Control</span></span>

<span data-ttu-id="792ce-220">`MarqueeControl` 只需<xref:System.Windows.Forms.UserControl>进行一些自定义。</span><span class="sxs-lookup"><span data-stu-id="792ce-220">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="792ce-221">它公开了两个`Start`方法:, 用于启动字幕动画和`Stop`, 这会停止动画。</span><span class="sxs-lookup"><span data-stu-id="792ce-221">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="792ce-222">`Start` `Stop` `StopMarquee`因为包含实现接口的子控件,`StartMarquee`并枚举每个子控件并分别对每个子控件调用和方法`IMarqueeWidget` `MarqueeControl`实现`IMarqueeWidget`的。</span><span class="sxs-lookup"><span data-stu-id="792ce-222">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>

<span data-ttu-id="792ce-223">`MarqueeBorder` `MarqueeControl`和<xref:System.Windows.Forms.Control.PerformLayout%2A> <xref:System.Windows.Forms.Control.OnLayout%2A>控件的外观依赖于布局, 因此重写此类型的子控件上的方法和调用。 `MarqueeText`</span><span class="sxs-lookup"><span data-stu-id="792ce-223">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>

<span data-ttu-id="792ce-224">这是`MarqueeControl`自定义的范围。</span><span class="sxs-lookup"><span data-stu-id="792ce-224">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="792ce-225">运行时功能`MarqueeBorder`由和`MarqueeText`控件实现, 设计时`MarqueeBorderDesigner`功能由和`MarqueeControlRootDesigner`类实现。</span><span class="sxs-lookup"><span data-stu-id="792ce-225">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>

### <a name="to-implement-your-custom-control"></a><span data-ttu-id="792ce-226">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="792ce-226">To implement your custom control</span></span>

1. <span data-ttu-id="792ce-227">在**代码编辑器**中打开源文件。`MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-227">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="792ce-228">`Start`实现和`Stop`方法。</span><span class="sxs-lookup"><span data-stu-id="792ce-228">Implement the `Start` and `Stop` methods.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <span data-ttu-id="792ce-229">重写 <xref:System.Windows.Forms.Control.OnLayout%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="792ce-229">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="creating-a-child-control-for-your-custom-control"></a><span data-ttu-id="792ce-230">为自定义控件创建子控件</span><span class="sxs-lookup"><span data-stu-id="792ce-230">Creating a Child Control for Your Custom Control</span></span>

<span data-ttu-id="792ce-231">将承载两种类型的子控件`MarqueeBorder` : 控件和`MarqueeText`控件。 `MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-231">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>

- <span data-ttu-id="792ce-232">`MarqueeBorder`：此控件围绕边缘绘制 "光源" 边框。</span><span class="sxs-lookup"><span data-stu-id="792ce-232">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="792ce-233">灯光按顺序闪烁, 使其看起来像是在边框上移动。</span><span class="sxs-lookup"><span data-stu-id="792ce-233">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="792ce-234">光源的闪烁速度由一个名`UpdatePeriod`为的属性控制。</span><span class="sxs-lookup"><span data-stu-id="792ce-234">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="792ce-235">其他几个自定义属性确定控件外观的其他方面。</span><span class="sxs-lookup"><span data-stu-id="792ce-235">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="792ce-236">两个称为`StartMarquee`和`StopMarquee`的方法控制动画的开始和停止时间。</span><span class="sxs-lookup"><span data-stu-id="792ce-236">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>

- <span data-ttu-id="792ce-237">`MarqueeText`：此控件绘制闪烁的字符串。</span><span class="sxs-lookup"><span data-stu-id="792ce-237">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="792ce-238">与控件一样, 文本闪烁的速度由`UpdatePeriod`属性控制。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="792ce-238">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="792ce-239">控件还具有`StopMarquee`与`StartMarquee` 控件`MarqueeBorder`共有的和方法。 `MarqueeText`</span><span class="sxs-lookup"><span data-stu-id="792ce-239">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>

<span data-ttu-id="792ce-240">在设计时, `MarqueeControlRootDesigner`可以将这两个控件类型添加到中的`MarqueeControl`任意组合。</span><span class="sxs-lookup"><span data-stu-id="792ce-240">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>

<span data-ttu-id="792ce-241">这两个控件的常见功能分解为一个名`IMarqueeWidget`为的接口。</span><span class="sxs-lookup"><span data-stu-id="792ce-241">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="792ce-242">这样, 就可以发现任何与选框相关的子控件, 并使它们特别对待。 `MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-242">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>

<span data-ttu-id="792ce-243">若要实现定期动画功能, 您将使用<xref:System.ComponentModel.BackgroundWorker>命名空间中<xref:System.ComponentModel?displayProperty=nameWithType>的对象。</span><span class="sxs-lookup"><span data-stu-id="792ce-243">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="792ce-244">可以使用<xref:System.Windows.Forms.Timer>对象, 但当存在许多`IMarqueeWidget`对象时, 单个 UI 线程可能无法跟上动画。</span><span class="sxs-lookup"><span data-stu-id="792ce-244">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>

### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="792ce-245">为自定义控件创建子控件</span><span class="sxs-lookup"><span data-stu-id="792ce-245">To create a child control for your custom control</span></span>

1. <span data-ttu-id="792ce-246">向`MarqueeControlLibrary`项目中添加一个新的类项。</span><span class="sxs-lookup"><span data-stu-id="792ce-246">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="792ce-247">为新的源文件命名为 "IMarqueeWidget" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="792ce-247">Give the new source file a base name of "IMarqueeWidget."</span></span>

2. <span data-ttu-id="792ce-248">在代码**编辑器**中打开`class` `interface`源文件, 并将声明从更改为: `IMarqueeWidget`</span><span class="sxs-lookup"><span data-stu-id="792ce-248">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. <span data-ttu-id="792ce-249">将以下代码添加到`IMarqueeWidget`接口, 以公开操作字幕动画的两个方法和属性:</span><span class="sxs-lookup"><span data-stu-id="792ce-249">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. <span data-ttu-id="792ce-250">向`MarqueeControlLibrary`项目中添加一个新的**自定义控件**项。</span><span class="sxs-lookup"><span data-stu-id="792ce-250">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="792ce-251">为新的源文件命名为 "MarqueeText" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="792ce-251">Give the new source file a base name of "MarqueeText."</span></span>

5. <span data-ttu-id="792ce-252">将组件从 " `MarqueeText`工具箱" 拖到控件上。 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="792ce-252">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="792ce-253">此组件允许`MarqueeText`控件以异步方式更新自身。</span><span class="sxs-lookup"><span data-stu-id="792ce-253">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>

6. <span data-ttu-id="792ce-254">在属性窗口<xref:System.ComponentModel.BackgroundWorker>中, 将组件的`WorkerReportsProgress`和<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="792ce-254">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="792ce-255">这些设置使<xref:System.ComponentModel.BackgroundWorker>组件可以定期<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>引发事件并取消异步更新。</span><span class="sxs-lookup"><span data-stu-id="792ce-255">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="792ce-256">有关详细信息, 请参阅[BackgroundWorker 组件](backgroundworker-component.md)。</span><span class="sxs-lookup"><span data-stu-id="792ce-256">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

7. <span data-ttu-id="792ce-257">在**代码编辑器**中打开源文件。`MarqueeText`</span><span class="sxs-lookup"><span data-stu-id="792ce-257">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="792ce-258">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="792ce-258">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. <span data-ttu-id="792ce-259">更改的`MarqueeText`声明以从和中<xref:System.Windows.Forms.Label>继承以实现`IMarqueeWidget`接口:</span><span class="sxs-lookup"><span data-stu-id="792ce-259">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. <span data-ttu-id="792ce-260">声明与公开的属性相对应的实例变量, 并在构造函数中对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="792ce-260">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="792ce-261">字段确定是否要以`LightColor`属性指定的颜色绘制文本。 `isLit`</span><span class="sxs-lookup"><span data-stu-id="792ce-261">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. <span data-ttu-id="792ce-262">实现 `IMarqueeWidget` 接口。</span><span class="sxs-lookup"><span data-stu-id="792ce-262">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="792ce-263">`StartMarquee`和方法`StopMarquee`调用组件的<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>和方法<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>来启动和停止动画。 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="792ce-263">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="792ce-264"><xref:System.ComponentModel.CategoryAttribute.Category%2A> 和<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>特性应用于属性,使其显示在名为"Marquee"属性窗口的自定义部分中。`UpdatePeriod`</span><span class="sxs-lookup"><span data-stu-id="792ce-264">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. <span data-ttu-id="792ce-265">实现属性访问器。</span><span class="sxs-lookup"><span data-stu-id="792ce-265">Implement the property accessors.</span></span> <span data-ttu-id="792ce-266">将向客户端公开两个属性`LightColor` : `DarkColor`和。</span><span class="sxs-lookup"><span data-stu-id="792ce-266">You will expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="792ce-267"><xref:System.ComponentModel.CategoryAttribute.Category%2A> 和<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>属性应用于这些属性, 因此属性显示在名为 "Marquee" 属性窗口的自定义部分中。</span><span class="sxs-lookup"><span data-stu-id="792ce-267">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. <span data-ttu-id="792ce-268">实现<xref:System.ComponentModel.BackgroundWorker> 组件和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件的处理程序。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="792ce-268">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="792ce-269">事件处理程序休眠`UpdatePeriod`指定的毫秒数, 并引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件, 直到代码通过调用<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>停止动画。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="792ce-269">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="792ce-270"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序在其亮状态和暗状态之间切换文本, 以显示闪烁的外观。</span><span class="sxs-lookup"><span data-stu-id="792ce-270">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. <span data-ttu-id="792ce-271">重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法以启用动画。</span><span class="sxs-lookup"><span data-stu-id="792ce-271">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. <span data-ttu-id="792ce-272">按 F6 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="792ce-272">Press F6 to build the solution.</span></span>

## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="792ce-273">创建 MarqueeBorder 子控件</span><span class="sxs-lookup"><span data-stu-id="792ce-273">Create the MarqueeBorder Child Control</span></span>

<span data-ttu-id="792ce-274">`MarqueeBorder` 控件`MarqueeText`比控件稍微复杂一些。</span><span class="sxs-lookup"><span data-stu-id="792ce-274">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="792ce-275">它具有更多属性, 并且<xref:System.Windows.Forms.Control.OnPaint%2A>方法中的动画更多。</span><span class="sxs-lookup"><span data-stu-id="792ce-275">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="792ce-276">原则上, 它非常类似`MarqueeText`于控件。</span><span class="sxs-lookup"><span data-stu-id="792ce-276">In principle, it is quite similar to the `MarqueeText` control.</span></span>

<span data-ttu-id="792ce-277">由于控件可以有子控件, 因此需要<xref:System.Windows.Forms.Control.Layout>知道事件。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="792ce-277">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>

### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="792ce-278">创建 MarqueeBorder 控件</span><span class="sxs-lookup"><span data-stu-id="792ce-278">To create the MarqueeBorder control</span></span>

1. <span data-ttu-id="792ce-279">向`MarqueeControlLibrary`项目中添加一个新的**自定义控件**项。</span><span class="sxs-lookup"><span data-stu-id="792ce-279">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="792ce-280">为新的源文件命名为 "MarqueeBorder" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="792ce-280">Give the new source file a base name of "MarqueeBorder."</span></span>

2. <span data-ttu-id="792ce-281">将组件从 " `MarqueeBorder`工具箱" 拖到控件上。 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="792ce-281">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="792ce-282">此组件允许`MarqueeBorder`控件以异步方式更新自身。</span><span class="sxs-lookup"><span data-stu-id="792ce-282">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>

3. <span data-ttu-id="792ce-283">在属性窗口<xref:System.ComponentModel.BackgroundWorker>中, 将组件的`WorkerReportsProgress`和<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="792ce-283">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="792ce-284">这些设置使<xref:System.ComponentModel.BackgroundWorker>组件可以定期<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>引发事件并取消异步更新。</span><span class="sxs-lookup"><span data-stu-id="792ce-284">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="792ce-285">有关详细信息, 请参阅[BackgroundWorker 组件](backgroundworker-component.md)。</span><span class="sxs-lookup"><span data-stu-id="792ce-285">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

4. <span data-ttu-id="792ce-286">在属性窗口中, 单击 "事件" 按钮。</span><span class="sxs-lookup"><span data-stu-id="792ce-286">In the Properties window, click the Events button.</span></span> <span data-ttu-id="792ce-287">为<xref:System.ComponentModel.BackgroundWorker.DoWork> 和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件附加处理程序。</span><span class="sxs-lookup"><span data-stu-id="792ce-287">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

5. <span data-ttu-id="792ce-288">在**代码编辑器**中打开源文件。`MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="792ce-288">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="792ce-289">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="792ce-289">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. <span data-ttu-id="792ce-290">更改的`MarqueeBorder`声明以从和中<xref:System.Windows.Forms.Panel>继承以实现`IMarqueeWidget`接口。</span><span class="sxs-lookup"><span data-stu-id="792ce-290">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. <span data-ttu-id="792ce-291">声明两个枚举, 用于`MarqueeBorder`管理控件的状态`MarqueeSpinDirection`:, 确定灯光`MarqueeLightShape`围绕边框的 "旋转" 方向, 确定光源的形状 (方形或圆形)。</span><span class="sxs-lookup"><span data-stu-id="792ce-291">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="792ce-292">将这些声明放在`MarqueeBorder`类声明之前。</span><span class="sxs-lookup"><span data-stu-id="792ce-292">Place these declarations before the `MarqueeBorder` class declaration.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. <span data-ttu-id="792ce-293">声明与公开的属性相对应的实例变量, 并在构造函数中对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="792ce-293">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. <span data-ttu-id="792ce-294">实现 `IMarqueeWidget` 接口。</span><span class="sxs-lookup"><span data-stu-id="792ce-294">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="792ce-295">`StartMarquee`和方法`StopMarquee`调用组件的<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>和方法<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>来启动和停止动画。 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="792ce-295">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="792ce-296">由于控件可以包含子控件, 因此该`StartMarquee`方法将枚举所有子控件, `StartMarquee`并调用实现`IMarqueeWidget`的这些子控件。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="792ce-296">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="792ce-297">`StopMarquee`方法具有类似的实现。</span><span class="sxs-lookup"><span data-stu-id="792ce-297">The `StopMarquee` method has a similar implementation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. <span data-ttu-id="792ce-298">实现属性访问器。</span><span class="sxs-lookup"><span data-stu-id="792ce-298">Implement the property accessors.</span></span> <span data-ttu-id="792ce-299">`MarqueeBorder`控件具有几个用于控制其外观的属性。</span><span class="sxs-lookup"><span data-stu-id="792ce-299">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. <span data-ttu-id="792ce-300">实现<xref:System.ComponentModel.BackgroundWorker> 组件和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件的处理程序。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="792ce-300">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="792ce-301">事件处理程序休眠`UpdatePeriod`指定的毫秒数, 并引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件, 直到代码通过调用<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>停止动画。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="792ce-301">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="792ce-302">该<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序会递增 "基本" 光源的位置, 从该光源确定另一个光源的亮/暗状态, 并<xref:System.Windows.Forms.Control.Refresh%2A>调用方法来使控件重绘自身。</span><span class="sxs-lookup"><span data-stu-id="792ce-302">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. <span data-ttu-id="792ce-303">实现帮助器方法`IsLit`和。 `DrawLight`</span><span class="sxs-lookup"><span data-stu-id="792ce-303">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>

    <span data-ttu-id="792ce-304">`IsLit`方法确定指定位置的光线颜色。</span><span class="sxs-lookup"><span data-stu-id="792ce-304">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="792ce-305">"亮" 的灯光以`LightColor`属性给定的颜色进行绘制, 而 "深色" 的光源则以`DarkColor`属性给定的颜色进行绘制。</span><span class="sxs-lookup"><span data-stu-id="792ce-305">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>

    <span data-ttu-id="792ce-306">`DrawLight`方法使用适当的颜色、形状和位置绘制光。</span><span class="sxs-lookup"><span data-stu-id="792ce-306">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <span data-ttu-id="792ce-307">重写<xref:System.Windows.Forms.Control.OnPaint%2A>和方法。 <xref:System.Windows.Forms.Control.OnLayout%2A></span><span class="sxs-lookup"><span data-stu-id="792ce-307">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>

    <span data-ttu-id="792ce-308">方法沿`MarqueeBorder`控件边缘绘制灯光。 <xref:System.Windows.Forms.Control.OnPaint%2A></span><span class="sxs-lookup"><span data-stu-id="792ce-308">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>

    <span data-ttu-id="792ce-309">由于方法依赖于`MarqueeBorder`控件的尺寸, 因此每当布局发生更改时都需要调用该方法。 <xref:System.Windows.Forms.Control.OnPaint%2A></span><span class="sxs-lookup"><span data-stu-id="792ce-309">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="792ce-310">若要实现此目的<xref:System.Windows.Forms.Control.OnLayout%2A> , 请<xref:System.Windows.Forms.Control.Refresh%2A>重写并调用。</span><span class="sxs-lookup"><span data-stu-id="792ce-310">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="792ce-311">创建用于隐藏和筛选属性的自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-311">Creating a Custom Designer to Shadow and Filter Properties</span></span>

<span data-ttu-id="792ce-312">`MarqueeControlRootDesigner`类提供根设计器的实现。</span><span class="sxs-lookup"><span data-stu-id="792ce-312">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="792ce-313">除了在上`MarqueeControl`运行的此设计器外, 还需要一个专门`MarqueeBorder`与控件关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="792ce-313">In addition to this designer, which operates on the `MarqueeControl`, you will need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="792ce-314">此设计器提供适用于自定义根设计器的上下文的自定义行为。</span><span class="sxs-lookup"><span data-stu-id="792ce-314">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>

<span data-ttu-id="792ce-315">具体而言, `MarqueeBorderDesigner`将 "隐藏" 并筛选`MarqueeBorder`控件上的某些属性, 更改与设计环境的交互。</span><span class="sxs-lookup"><span data-stu-id="792ce-315">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>

<span data-ttu-id="792ce-316">截获对组件的属性访问器的调用称为 "隐藏"。</span><span class="sxs-lookup"><span data-stu-id="792ce-316">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="792ce-317">它允许设计器跟踪用户设置的值, 还可以选择将该值传递给所设计的组件。</span><span class="sxs-lookup"><span data-stu-id="792ce-317">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>

<span data-ttu-id="792ce-318">在<xref:System.Windows.Forms.Control.Visible%2A>此示例中, 和<xref:System.Windows.Forms.Control.Enabled%2A>属性`MarqueeBorderDesigner`将由隐藏`MarqueeBorder` , 这会阻止用户在设计时使控件不可见或处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="792ce-318">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>

<span data-ttu-id="792ce-319">设计器还可以添加和移除属性。</span><span class="sxs-lookup"><span data-stu-id="792ce-319">Designers can also add and remove properties.</span></span> <span data-ttu-id="792ce-320">在此示例中, <xref:System.Windows.Forms.Control.Padding%2A>将在设计时删除属性, `MarqueeBorder`因为控件以编程方式基于`LightSize`属性指定的灯光大小设置填充。</span><span class="sxs-lookup"><span data-stu-id="792ce-320">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>

<span data-ttu-id="792ce-321">的基类`MarqueeBorderDesigner`为<xref:System.ComponentModel.Design.ComponentDesigner>, 它具有可在设计时更改控件所公开的特性、属性和事件的方法:</span><span class="sxs-lookup"><span data-stu-id="792ce-321">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

<span data-ttu-id="792ce-322">使用这些方法更改组件的公共接口时, 必须遵循以下规则:</span><span class="sxs-lookup"><span data-stu-id="792ce-322">When changing the public interface of a component using these methods, you must follow these rules:</span></span>

- <span data-ttu-id="792ce-323">仅在`PreFilter`方法中添加或删除项</span><span class="sxs-lookup"><span data-stu-id="792ce-323">Add or remove items in the `PreFilter` methods only</span></span>

- <span data-ttu-id="792ce-324">仅修改方法中的`PostFilter`现有项</span><span class="sxs-lookup"><span data-stu-id="792ce-324">Modify existing items in the `PostFilter` methods only</span></span>

- <span data-ttu-id="792ce-325">始终在`PreFilter`方法中首先调用基实现</span><span class="sxs-lookup"><span data-stu-id="792ce-325">Always call the base implementation first in the `PreFilter` methods</span></span>

- <span data-ttu-id="792ce-326">始终在`PostFilter`方法中最后调用基本实现</span><span class="sxs-lookup"><span data-stu-id="792ce-326">Always call the base implementation last in the `PostFilter` methods</span></span>

<span data-ttu-id="792ce-327">遵循这些规则可确保设计时环境中的所有设计器都具有设计中所有组件的一致视图。</span><span class="sxs-lookup"><span data-stu-id="792ce-327">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>

<span data-ttu-id="792ce-328"><xref:System.ComponentModel.Design.ComponentDesigner>类提供字典, 用于管理隐藏属性的值, 从而使您不必创建特定的实例变量。</span><span class="sxs-lookup"><span data-stu-id="792ce-328">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="792ce-329">创建用于隐藏和筛选属性的自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-329">To create a custom designer to shadow and filter properties</span></span>

1. <span data-ttu-id="792ce-330">右键单击**设计**文件夹并添加一个新类。</span><span class="sxs-lookup"><span data-stu-id="792ce-330">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="792ce-331">为源文件指定基名称 "MarqueeBorderDesigner"。</span><span class="sxs-lookup"><span data-stu-id="792ce-331">Give the source file a base name of "MarqueeBorderDesigner."</span></span>

2. <span data-ttu-id="792ce-332">在**代码编辑器**中打开源文件。`MarqueeBorderDesigner`</span><span class="sxs-lookup"><span data-stu-id="792ce-332">Open the `MarqueeBorderDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="792ce-333">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="792ce-333">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. <span data-ttu-id="792ce-334">更改的`MarqueeBorderDesigner`声明以从<xref:System.Windows.Forms.Design.ParentControlDesigner>继承。</span><span class="sxs-lookup"><span data-stu-id="792ce-334">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>

    <span data-ttu-id="792ce-335">由于控件可以包含子控件, `MarqueeBorderDesigner`因此继承自<xref:System.Windows.Forms.Design.ParentControlDesigner>, 后者处理父子交互。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="792ce-335">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. <span data-ttu-id="792ce-336">重写的<xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>基实现。</span><span class="sxs-lookup"><span data-stu-id="792ce-336">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <span data-ttu-id="792ce-337">实现 <xref:System.Windows.Forms.Control.Enabled%2A> 和 <xref:System.Windows.Forms.Control.Visible%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="792ce-337">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="792ce-338">这些实现将隐藏控件的属性。</span><span class="sxs-lookup"><span data-stu-id="792ce-338">These implementations shadow the control's properties.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handling-component-changes"></a><span data-ttu-id="792ce-339">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="792ce-339">Handling Component Changes</span></span>
 <span data-ttu-id="792ce-340">类为你`MarqueeControl`的实例提供自定义的设计时体验。 `MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="792ce-340">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="792ce-341">大多数设计时功能都是从<xref:System.Windows.Forms.Design.DocumentDesigner>类继承的; 你的代码将实现两个特定的自定义: 处理组件更改和添加设计器谓词。</span><span class="sxs-lookup"><span data-stu-id="792ce-341">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class; your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>

 <span data-ttu-id="792ce-342">当用户设计其`MarqueeControl`实例时, 你的根设计器将跟踪`MarqueeControl`及其子控件的更改。</span><span class="sxs-lookup"><span data-stu-id="792ce-342">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="792ce-343">设计时环境提供了一种方便的服务<xref:System.ComponentModel.Design.IComponentChangeService>, 用于跟踪对组件状态的更改。</span><span class="sxs-lookup"><span data-stu-id="792ce-343">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>

 <span data-ttu-id="792ce-344">通过使用<xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>方法查询环境来获取对此服务的引用。</span><span class="sxs-lookup"><span data-stu-id="792ce-344">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="792ce-345">如果查询成功, 设计器可以为<xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged>事件附加处理程序, 并执行在设计时保持一致状态所需的任何任务。</span><span class="sxs-lookup"><span data-stu-id="792ce-345">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>

 <span data-ttu-id="792ce-346">对于`MarqueeControlRootDesigner`类, 您将对包含的`MarqueeControl`每个`IMarqueeWidget`对象<xref:System.Windows.Forms.Control.Refresh%2A>调用方法。</span><span class="sxs-lookup"><span data-stu-id="792ce-346">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="792ce-347">这会使`IMarqueeWidget`对象在其父级的<xref:System.Windows.Forms.Control.Size%2A>属性 (如属性) 发生更改时正确重绘自身。</span><span class="sxs-lookup"><span data-stu-id="792ce-347">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>

### <a name="to-handle-component-changes"></a><span data-ttu-id="792ce-348">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="792ce-348">To handle component changes</span></span>

1. <span data-ttu-id="792ce-349">在代码**编辑器**中打开<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 源文件,并重写方法。`MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="792ce-349">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="792ce-350">调用的基实现<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> , 并查询。 <xref:System.ComponentModel.Design.IComponentChangeService></span><span class="sxs-lookup"><span data-stu-id="792ce-350">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <span data-ttu-id="792ce-351"><xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>实现事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="792ce-351">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="792ce-352">测试发送组件的类型, 如果它是`IMarqueeWidget`, 则调用其<xref:System.Windows.Forms.Control.Refresh%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="792ce-352">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="adding-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="792ce-353">将设计器谓词添加到自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-353">Adding Designer Verbs to your Custom Designer</span></span>

<span data-ttu-id="792ce-354">设计器谓词是链接到事件处理程序的菜单命令。</span><span class="sxs-lookup"><span data-stu-id="792ce-354">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="792ce-355">设计器谓词在设计时添加到组件的快捷菜单中。</span><span class="sxs-lookup"><span data-stu-id="792ce-355">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="792ce-356">有关详细信息，请参阅 <xref:System.ComponentModel.Design.DesignerVerb> 。</span><span class="sxs-lookup"><span data-stu-id="792ce-356">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>

<span data-ttu-id="792ce-357">你将向设计器添加两个设计器谓词:**运行测试**和**停止测试**。</span><span class="sxs-lookup"><span data-stu-id="792ce-357">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="792ce-358">这些谓词允许您`MarqueeControl`在设计时查看的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="792ce-358">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="792ce-359">这些谓词将添加到`MarqueeControlRootDesigner`。</span><span class="sxs-lookup"><span data-stu-id="792ce-359">These verbs will be added to the `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="792ce-360">调用 "**运行测试**" 时, verb 事件处理程序将对`StartMarquee`调用方法。 `MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-360">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="792ce-361">调用**停止测试**时, verb 事件处理程序将对调用`StopMarquee`方法。 `MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-361">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="792ce-362">`StartMarquee`和`IMarqueeWidget` `IMarqueeWidget`方法的实现在实现的包含控件上调用这些方法, 因此任何包含的控件也将参与测试。 `StopMarquee`</span><span class="sxs-lookup"><span data-stu-id="792ce-362">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>

### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="792ce-363">将设计器谓词添加到自定义设计器</span><span class="sxs-lookup"><span data-stu-id="792ce-363">To add designer verbs to your custom designers</span></span>

1. <span data-ttu-id="792ce-364">在类中, 添加名为`OnVerbRunTest`和`OnVerbStopTest`的事件处理程序。 `MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="792ce-364">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. <span data-ttu-id="792ce-365">将这些事件处理程序连接到相应的设计器谓词。</span><span class="sxs-lookup"><span data-stu-id="792ce-365">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="792ce-366">`MarqueeControlRootDesigner`<xref:System.ComponentModel.Design.DesignerVerbCollection>从其基类继承。</span><span class="sxs-lookup"><span data-stu-id="792ce-366">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="792ce-367">您将创建两个<xref:System.ComponentModel.Design.DesignerVerb>新的<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>对象, 并在方法中将它们添加到此集合中。</span><span class="sxs-lookup"><span data-stu-id="792ce-367">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="creating-a-custom-uitypeeditor"></a><span data-ttu-id="792ce-368">创建自定义 UITypeEditor</span><span class="sxs-lookup"><span data-stu-id="792ce-368">Creating a Custom UITypeEditor</span></span>

<span data-ttu-id="792ce-369">为用户创建自定义设计时体验时, 通常需要创建与属性窗口的自定义交互。</span><span class="sxs-lookup"><span data-stu-id="792ce-369">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="792ce-370">可以通过创建<xref:System.Drawing.Design.UITypeEditor>来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="792ce-370">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span> <span data-ttu-id="792ce-371">有关详细信息，请参阅[如何：创建 UI 类型编辑器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="792ce-371">For more information, see [How to: Create a UI Type Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120)).</span></span>

<span data-ttu-id="792ce-372">`MarqueeBorder`控件公开属性窗口中的多个属性。</span><span class="sxs-lookup"><span data-stu-id="792ce-372">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="792ce-373">其中两个属性, `MarqueeSpinDirection` `MarqueeLightShape`由枚举表示。</span><span class="sxs-lookup"><span data-stu-id="792ce-373">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="792ce-374">为了说明 UI 类型编辑器的用法, 该`MarqueeLightShape`属性将具有关联<xref:System.Drawing.Design.UITypeEditor>的类。</span><span class="sxs-lookup"><span data-stu-id="792ce-374">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>

### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="792ce-375">创建自定义 UI 类型编辑器</span><span class="sxs-lookup"><span data-stu-id="792ce-375">To create a custom UI type editor</span></span>

1. <span data-ttu-id="792ce-376">在**代码编辑器**中打开源文件。`MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="792ce-376">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>

2. <span data-ttu-id="792ce-377">在`MarqueeBorder`类的定义中, 声明一个派生自`LightShapeEditor` <xref:System.Drawing.Design.UITypeEditor>的类。</span><span class="sxs-lookup"><span data-stu-id="792ce-377">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <span data-ttu-id="792ce-378">声明一个<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>名`editorService`为的实例变量。</span><span class="sxs-lookup"><span data-stu-id="792ce-378">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <span data-ttu-id="792ce-379">重写 <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="792ce-379">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="792ce-380">此实现返回<xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, 它指示设计环境如何`LightShapeEditor`显示。</span><span class="sxs-lookup"><span data-stu-id="792ce-380">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <span data-ttu-id="792ce-381">重写 <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="792ce-381">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="792ce-382">此实现查询<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>对象的设计环境。</span><span class="sxs-lookup"><span data-stu-id="792ce-382">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="792ce-383">如果成功, 它将创建`LightShapeSelectionControl`一个。</span><span class="sxs-lookup"><span data-stu-id="792ce-383">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="792ce-384">调用方法来`LightShapeEditor`启动。 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A></span><span class="sxs-lookup"><span data-stu-id="792ce-384">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="792ce-385">此调用的返回值将返回到设计环境。</span><span class="sxs-lookup"><span data-stu-id="792ce-385">The return value from this invocation is returned to the design environment.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="792ce-386">为自定义 UITypeEditor 创建视图控件</span><span class="sxs-lookup"><span data-stu-id="792ce-386">Creating a View Control for your Custom UITypeEditor</span></span>

1. <span data-ttu-id="792ce-387">属性支持两种类型的光源形状: `Square`和`Circle`。 `MarqueeLightShape`</span><span class="sxs-lookup"><span data-stu-id="792ce-387">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="792ce-388">您将创建一个仅用于以图形方式在属性窗口中显示这些值的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="792ce-388">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="792ce-389">此自定义控件将由<xref:System.Drawing.Design.UITypeEditor>用于与属性窗口进行交互。</span><span class="sxs-lookup"><span data-stu-id="792ce-389">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="792ce-390">为自定义 UI 类型编辑器创建视图控件</span><span class="sxs-lookup"><span data-stu-id="792ce-390">To create a view control for your custom UI type editor</span></span>

1. <span data-ttu-id="792ce-391">向`MarqueeControlLibrary`项目中<xref:System.Windows.Forms.UserControl>添加新项。</span><span class="sxs-lookup"><span data-stu-id="792ce-391">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="792ce-392">为新的源文件命名为 "LightShapeSelectionControl" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="792ce-392">Give the new source file a base name of "LightShapeSelectionControl."</span></span>

2. <span data-ttu-id="792ce-393">将两<xref:System.Windows.Forms.Panel>个控件从 `LightShapeSelectionControl`工具箱拖到上。</span><span class="sxs-lookup"><span data-stu-id="792ce-393">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="792ce-394">将它们`squarePanel`命名`circlePanel`为和。</span><span class="sxs-lookup"><span data-stu-id="792ce-394">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="792ce-395">并排排列它们。</span><span class="sxs-lookup"><span data-stu-id="792ce-395">Arrange them side by side.</span></span> <span data-ttu-id="792ce-396">将这<xref:System.Windows.Forms.Control.Size%2A>两个<xref:System.Windows.Forms.Panel>控件的属性设置为 (60, 60)。</span><span class="sxs-lookup"><span data-stu-id="792ce-396">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to (60, 60).</span></span> <span data-ttu-id="792ce-397">将`squarePanel`控件<xref:System.Windows.Forms.Control.Location%2A>的属性设置为 (8, 10)。</span><span class="sxs-lookup"><span data-stu-id="792ce-397">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to (8, 10).</span></span> <span data-ttu-id="792ce-398">将`circlePanel`控件<xref:System.Windows.Forms.Control.Location%2A>的属性设置为 (80, 10)。</span><span class="sxs-lookup"><span data-stu-id="792ce-398">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to (80, 10).</span></span> <span data-ttu-id="792ce-399">最后, 将的<xref:System.Windows.Forms.Control.Size%2A> `LightShapeSelectionControl`属性设置为 (150, 80)。</span><span class="sxs-lookup"><span data-stu-id="792ce-399">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to (150, 80).</span></span>

3. <span data-ttu-id="792ce-400">在**代码编辑器**中打开源文件。`LightShapeSelectionControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-400">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="792ce-401">在该文件的顶部, 导入<xref:System.Windows.Forms.Design?displayProperty=nameWithType>命名空间:</span><span class="sxs-lookup"><span data-stu-id="792ce-401">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>

```vb
Imports System.Windows.Forms.Design
```

```csharp
using System.Windows.Forms.Design;
```

1. <span data-ttu-id="792ce-402">为<xref:System.Windows.Forms.Control.Click>和控件`circlePanel`实现事件处理程序。 `squarePanel`</span><span class="sxs-lookup"><span data-stu-id="792ce-402">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="792ce-403">这些方法调用<xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A>以结束自定义<xref:System.Drawing.Design.UITypeEditor>编辑会话。</span><span class="sxs-lookup"><span data-stu-id="792ce-403">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

2. <span data-ttu-id="792ce-404">声明一个<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>名`editorService`为的实例变量。</span><span class="sxs-lookup"><span data-stu-id="792ce-404">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

```vb
Private editorService As IWindowsFormsEditorService
```

```csharp
private IWindowsFormsEditorService editorService;
```

1. <span data-ttu-id="792ce-405">声明一个`MarqueeLightShape`名`lightShapeValue`为的实例变量。</span><span class="sxs-lookup"><span data-stu-id="792ce-405">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

2. <span data-ttu-id="792ce-406">`squarePanel` <xref:System.Windows.Forms.Control.Click> `circlePanel`在构造函数中, <xref:System.Windows.Forms.Control.Click>将事件处理程序附加到和控件的事件。 `LightShapeSelectionControl`</span><span class="sxs-lookup"><span data-stu-id="792ce-406">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="792ce-407">另外, 定义将设计环境中的`MarqueeLightShape`值分配`lightShapeValue`给字段的构造函数重载。</span><span class="sxs-lookup"><span data-stu-id="792ce-407">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

3. <span data-ttu-id="792ce-408">在方法中, <xref:System.Windows.Forms.Control.Click>分离事件处理程序。 <xref:System.ComponentModel.Component.Dispose%2A></span><span class="sxs-lookup"><span data-stu-id="792ce-408">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

4. <span data-ttu-id="792ce-409">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="792ce-409">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="792ce-410">打开 LightShapeSelectionControl.Designer.cs 或 LightShapeSelectionControl 文件, 并删除该<xref:System.ComponentModel.Component.Dispose%2A>方法的默认定义。</span><span class="sxs-lookup"><span data-stu-id="792ce-410">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>

5. <span data-ttu-id="792ce-411">实现 `LightShape` 属性。</span><span class="sxs-lookup"><span data-stu-id="792ce-411">Implement the `LightShape` property.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

6. <span data-ttu-id="792ce-412">重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="792ce-412">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="792ce-413">此实现将绘制实心正方形和圆圈。</span><span class="sxs-lookup"><span data-stu-id="792ce-413">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="792ce-414">它还将通过在一个形状周围绘制边框来突出显示选定的值。</span><span class="sxs-lookup"><span data-stu-id="792ce-414">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="testing-your-custom-control-in-the-designer"></a><span data-ttu-id="792ce-415">在设计器中测试自定义控件</span><span class="sxs-lookup"><span data-stu-id="792ce-415">Testing your Custom Control in the Designer</span></span>

<span data-ttu-id="792ce-416">此时, 您可以生成`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="792ce-416">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="792ce-417">通过创建从`MarqueeControl`类继承的控件并在窗体上使用它来测试您的实现。</span><span class="sxs-lookup"><span data-stu-id="792ce-417">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>

### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="792ce-418">创建自定义 MarqueeControl 实现</span><span class="sxs-lookup"><span data-stu-id="792ce-418">To create a custom MarqueeControl implementation</span></span>

1. <span data-ttu-id="792ce-419">在 Windows 窗体设计器中打开 `DemoMarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="792ce-419">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="792ce-420">这会创建`DemoMarqueeControl`类型的实例, 并将其显示在`MarqueeControlRootDesigner`类型的实例中。</span><span class="sxs-lookup"><span data-stu-id="792ce-420">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>

2. <span data-ttu-id="792ce-421">在 "**工具箱**" 中, 打开 " **MarqueeControlLibrary 组件**" 选项卡。你将看到`MarqueeBorder`和`MarqueeText`控件可供选择。</span><span class="sxs-lookup"><span data-stu-id="792ce-421">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>

3. <span data-ttu-id="792ce-422">将`MarqueeBorder`控件的一个实例拖`DemoMarqueeControl`到设计图面上。</span><span class="sxs-lookup"><span data-stu-id="792ce-422">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="792ce-423">将此`MarqueeBorder`控件停靠到父控件。</span><span class="sxs-lookup"><span data-stu-id="792ce-423">Dock this `MarqueeBorder` control to the parent control.</span></span>

4. <span data-ttu-id="792ce-424">将`MarqueeText`控件的一个实例拖`DemoMarqueeControl`到设计图面上。</span><span class="sxs-lookup"><span data-stu-id="792ce-424">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>

5. <span data-ttu-id="792ce-425">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="792ce-425">Build the solution.</span></span>

6. <span data-ttu-id="792ce-426">右键单击`DemoMarqueeControl` , 然后从快捷菜单中选择 "**运行测试**" 选项以启动动画。</span><span class="sxs-lookup"><span data-stu-id="792ce-426">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="792ce-427">单击 "**停止测试**" 以停止动画。</span><span class="sxs-lookup"><span data-stu-id="792ce-427">Click **Stop Test** to stop the animation.</span></span>

7. <span data-ttu-id="792ce-428">在设计视图中打开“Form1”。</span><span class="sxs-lookup"><span data-stu-id="792ce-428">Open **Form1** in Design view.</span></span>

8. <span data-ttu-id="792ce-429">将两<xref:System.Windows.Forms.Button>个控件置于窗体上。</span><span class="sxs-lookup"><span data-stu-id="792ce-429">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="792ce-430">将它们`startButton`命名`stopButton`为和, 并<xref:System.Windows.Forms.Control.Text%2A>分别将属性值更改为 "**启动**" 和 "**停止**"。</span><span class="sxs-lookup"><span data-stu-id="792ce-430">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>

9. <span data-ttu-id="792ce-431">为<xref:System.Windows.Forms.Control.Click>这两个<xref:System.Windows.Forms.Button>控件实现事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="792ce-431">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>

10. <span data-ttu-id="792ce-432">在 "**工具箱**" 中, 打开 " **MarqueeControlTest 组件**" 选项卡。你将看到`DemoMarqueeControl`可供选择。</span><span class="sxs-lookup"><span data-stu-id="792ce-432">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>

11. <span data-ttu-id="792ce-433">将的`DemoMarqueeControl`一个实例拖到**Form1**设计图面上。</span><span class="sxs-lookup"><span data-stu-id="792ce-433">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>

12. <span data-ttu-id="792ce-434">在事件处理程序中, 调用`Start`上`Stop` `DemoMarqueeControl`的和方法。 <xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="792ce-434">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>

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

1. <span data-ttu-id="792ce-435">`MarqueeControlTest`将项目设置为 "启动项目" 并运行该项目。</span><span class="sxs-lookup"><span data-stu-id="792ce-435">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="792ce-436">你将看到显示`DemoMarqueeControl`的窗体。</span><span class="sxs-lookup"><span data-stu-id="792ce-436">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="792ce-437">单击 "**启动**" 按钮以启动动画。</span><span class="sxs-lookup"><span data-stu-id="792ce-437">Click the **Start** button to start the animation.</span></span> <span data-ttu-id="792ce-438">应会看到文本闪烁, 而灯光在边框上移动。</span><span class="sxs-lookup"><span data-stu-id="792ce-438">You should see the text flashing and the lights moving around the border.</span></span>

## <a name="next-steps"></a><span data-ttu-id="792ce-439">后续步骤</span><span class="sxs-lookup"><span data-stu-id="792ce-439">Next Steps</span></span>

<span data-ttu-id="792ce-440">`MarqueeControlLibrary`演示自定义控件和关联设计器的简单实现。</span><span class="sxs-lookup"><span data-stu-id="792ce-440">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="792ce-441">可以通过多种方式使此示例更加复杂:</span><span class="sxs-lookup"><span data-stu-id="792ce-441">You can make this sample more sophisticated in several ways:</span></span>

- <span data-ttu-id="792ce-442">在设计器中更改的`DemoMarqueeControl`属性值。</span><span class="sxs-lookup"><span data-stu-id="792ce-442">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="792ce-443">添加更`MarqueBorder`多控件并将它们停靠在其父实例中以创建嵌套效果。</span><span class="sxs-lookup"><span data-stu-id="792ce-443">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="792ce-444">试验的`UpdatePeriod`不同设置以及与光源相关的属性。</span><span class="sxs-lookup"><span data-stu-id="792ce-444">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>

- <span data-ttu-id="792ce-445">创作自己的`IMarqueeWidget`实现。</span><span class="sxs-lookup"><span data-stu-id="792ce-445">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="792ce-446">例如, 可以创建一个闪烁的 "霓虹灯号" 或包含多个图像的动画符号。</span><span class="sxs-lookup"><span data-stu-id="792ce-446">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>

- <span data-ttu-id="792ce-447">进一步自定义设计时体验。</span><span class="sxs-lookup"><span data-stu-id="792ce-447">Further customize the design-time experience.</span></span> <span data-ttu-id="792ce-448">您可以尝试隐藏比<xref:System.Windows.Forms.Control.Enabled%2A>和<xref:System.Windows.Forms.Control.Visible%2A>更多的属性, 并且可以添加新属性。</span><span class="sxs-lookup"><span data-stu-id="792ce-448">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="792ce-449">添加新的设计器谓词以简化诸如停靠子控件等常见任务。</span><span class="sxs-lookup"><span data-stu-id="792ce-449">Add new designer verbs to simplify common tasks like docking child controls.</span></span>

- <span data-ttu-id="792ce-450">`MarqueeControl`许可。</span><span class="sxs-lookup"><span data-stu-id="792ce-450">License the `MarqueeControl`.</span></span> <span data-ttu-id="792ce-451">有关详细信息，请参阅[如何：许可证组件和控件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="792ce-451">For more information, see [How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120)).</span></span>

- <span data-ttu-id="792ce-452">控制如何序列化控件, 以及如何为控件生成代码。</span><span class="sxs-lookup"><span data-stu-id="792ce-452">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="792ce-453">有关详细信息, 请参阅[动态源代码生成和编译](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)。</span><span class="sxs-lookup"><span data-stu-id="792ce-453">For more information, see [Dynamic Source Code Generation and Compilation](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="792ce-454">请参阅</span><span class="sxs-lookup"><span data-stu-id="792ce-454">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
- <span data-ttu-id="792ce-455">[如何：创建利用设计时功能的 Windows 窗体控件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="792ce-455">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>
- <span data-ttu-id="792ce-456">[扩展设计时支持](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="792ce-456">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- <span data-ttu-id="792ce-457">[自定义设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="792ce-457">[Custom Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))</span></span>
