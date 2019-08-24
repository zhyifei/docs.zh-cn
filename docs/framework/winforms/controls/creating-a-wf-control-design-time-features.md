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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b72c449ab68c9bb2ceea6f8ee78abe6771b9a8bd
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016013"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a><span data-ttu-id="ab802-102">演练：创建利用设计时功能的控件</span><span class="sxs-lookup"><span data-stu-id="ab802-102">Walkthrough: Create a control that takes advantage of design-time features</span></span>

<span data-ttu-id="ab802-103">通过创作关联的自定义设计器, 可以增强自定义控件的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="ab802-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>

<span data-ttu-id="ab802-104">本文说明如何为自定义控件创建自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="ab802-104">This article illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="ab802-105">您将实现一个`MarqueeControl`名`MarqueeControlRootDesigner`为的类型和一个关联的设计器类。</span><span class="sxs-lookup"><span data-stu-id="ab802-105">You'll implement a `MarqueeControl` type and an associated designer class called `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="ab802-106">该`MarqueeControl`类型实现的显示类似于具有动画光和闪烁文本的剧院字幕。</span><span class="sxs-lookup"><span data-stu-id="ab802-106">The `MarqueeControl` type implements a display similar to a theater marquee with animated lights and flashing text.</span></span>

<span data-ttu-id="ab802-107">此控件的设计器与设计环境交互, 以提供自定义的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="ab802-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="ab802-108">使用自定义设计器, 可以在许多组合`MarqueeControl`中使用动态光源和闪烁文本来组装自定义实现。</span><span class="sxs-lookup"><span data-stu-id="ab802-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="ab802-109">可以像任何其他 Windows 窗体控件一样使用窗体上的组合控件。</span><span class="sxs-lookup"><span data-stu-id="ab802-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>

<span data-ttu-id="ab802-110">完成本演练后, 自定义控件将如下所示:</span><span class="sxs-lookup"><span data-stu-id="ab802-110">When you're finished with this walkthrough, your custom control will look something like the following:</span></span>

![该应用显示了文本和 "开始" 和 "停止" 按钮的选框。](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

<span data-ttu-id="ab802-112">有关完整的代码列表, 请[参阅如何:创建利用设计时功能](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ab802-112">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ab802-113">系统必备</span><span class="sxs-lookup"><span data-stu-id="ab802-113">Prerequisites</span></span>

<span data-ttu-id="ab802-114">若要完成本演练, 你将需要 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="ab802-114">In order to complete this walkthrough, you'll need Visual Studio.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ab802-115">创建项目</span><span class="sxs-lookup"><span data-stu-id="ab802-115">Create the project</span></span>

<span data-ttu-id="ab802-116">第一步是创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="ab802-116">The first step is to create the application project.</span></span> <span data-ttu-id="ab802-117">将使用此项目生成承载自定义控件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ab802-117">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="ab802-118">在 Visual Studio 中, 创建一个新的 Windows 窗体应用程序项目, 并将其命名为**MarqueeControlTest**。</span><span class="sxs-lookup"><span data-stu-id="ab802-118">In Visual Studio, create a new Windows Forms Application project, and name it **MarqueeControlTest**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="ab802-119">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="ab802-119">Create the control library project</span></span>

1. <span data-ttu-id="ab802-120">将 Windows 窗体控件库项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="ab802-120">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="ab802-121">将项目命名为**MarqueeControlLibrary**。</span><span class="sxs-lookup"><span data-stu-id="ab802-121">Name the project **MarqueeControlLibrary**.</span></span>

2. <span data-ttu-id="ab802-122">使用**解决方案资源管理器**, 通过删除名为 "UserControl1.cs" 或 "UserControl1" 的源文件来删除项目的默认控件, 具体取决于您选择的语言。</span><span class="sxs-lookup"><span data-stu-id="ab802-122">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

3. <span data-ttu-id="ab802-123">向`MarqueeControlLibrary`项目中<xref:System.Windows.Forms.UserControl>添加新项。</span><span class="sxs-lookup"><span data-stu-id="ab802-123">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ab802-124">为新的源文件指定基名称**MarqueeControl**。</span><span class="sxs-lookup"><span data-stu-id="ab802-124">Give the new source file a base name of **MarqueeControl**.</span></span>

4. <span data-ttu-id="ab802-125">使用**解决方案资源管理器**在`MarqueeControlLibrary`项目中创建一个新文件夹。</span><span class="sxs-lookup"><span data-stu-id="ab802-125">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span>

5. <span data-ttu-id="ab802-126">右键单击**设计**文件夹并添加一个新类。</span><span class="sxs-lookup"><span data-stu-id="ab802-126">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="ab802-127">将其命名为**MarqueeControlRootDesigner**。</span><span class="sxs-lookup"><span data-stu-id="ab802-127">Name it **MarqueeControlRootDesigner**.</span></span>

6. <span data-ttu-id="ab802-128">需要使用来自 system.object 程序集的类型, 因此请将此引用添加到`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="ab802-128">You'll need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>

## <a name="reference-the-custom-control-project"></a><span data-ttu-id="ab802-129">引用自定义控件项目</span><span class="sxs-lookup"><span data-stu-id="ab802-129">Reference the Custom Control Project</span></span>

<span data-ttu-id="ab802-130">您将使用该`MarqueeControlTest`项目来测试自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ab802-130">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="ab802-131">向`MarqueeControlLibrary`程序集添加项目引用时, 测试项目将会感知自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ab802-131">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>

<span data-ttu-id="ab802-132">在项目中, 添加`MarqueeControlLibrary`对程序集的项目引用。 `MarqueeControlTest`</span><span class="sxs-lookup"><span data-stu-id="ab802-132">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="ab802-133">请确保使用 "**添加引用**" 对话框中的 "**项目**" 选项卡, 而`MarqueeControlLibrary`不是直接引用程序集。</span><span class="sxs-lookup"><span data-stu-id="ab802-133">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>

## <a name="define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="ab802-134">定义自定义控件及其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="ab802-134">Define a Custom Control and Its Custom Designer</span></span>

<span data-ttu-id="ab802-135">自定义控件将派生<xref:System.Windows.Forms.UserControl>自类。</span><span class="sxs-lookup"><span data-stu-id="ab802-135">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="ab802-136">这允许控件包含其他控件, 并使控件具有大量默认功能。</span><span class="sxs-lookup"><span data-stu-id="ab802-136">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>

<span data-ttu-id="ab802-137">自定义控件将具有关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="ab802-137">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="ab802-138">这允许您创建专为自定义控件定制的独特设计体验。</span><span class="sxs-lookup"><span data-stu-id="ab802-138">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>

<span data-ttu-id="ab802-139">使用<xref:System.ComponentModel.DesignerAttribute>类将控件与其设计器相关联。</span><span class="sxs-lookup"><span data-stu-id="ab802-139">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="ab802-140">由于您正在开发自定义控件的整个设计时行为, 因此自定义设计器将实现该<xref:System.ComponentModel.Design.IRootDesigner>接口。</span><span class="sxs-lookup"><span data-stu-id="ab802-140">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>

### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="ab802-141">定义自定义控件及其自定义设计器</span><span class="sxs-lookup"><span data-stu-id="ab802-141">To define a custom control and its custom designer</span></span>

1. <span data-ttu-id="ab802-142">在**代码编辑器**中打开源文件。`MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-142">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="ab802-143">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="ab802-143">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <span data-ttu-id="ab802-144">将添加<xref:System.ComponentModel.DesignerAttribute> `MarqueeControl`到类声明中。</span><span class="sxs-lookup"><span data-stu-id="ab802-144">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="ab802-145">这会将自定义控件与其设计器相关联。</span><span class="sxs-lookup"><span data-stu-id="ab802-145">This associates the custom control with its designer.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. <span data-ttu-id="ab802-146">在**代码编辑器**中打开源文件。`MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="ab802-146">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="ab802-147">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="ab802-147">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. <span data-ttu-id="ab802-148">更改的`MarqueeControlRootDesigner`声明以<xref:System.Windows.Forms.Design.DocumentDesigner>从类继承。</span><span class="sxs-lookup"><span data-stu-id="ab802-148">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="ab802-149">应用, 以指定与工具箱的设计器交互。 <xref:System.ComponentModel.ToolboxItemFilterAttribute></span><span class="sxs-lookup"><span data-stu-id="ab802-149">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ab802-150">`MarqueeControlRootDesigner`类的定义已包含在名为 MarqueeControlLibrary 的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="ab802-150">The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called MarqueeControlLibrary.Design.</span></span> <span data-ttu-id="ab802-151">此声明将设计器置于为设计相关类型保留的特殊命名空间中。</span><span class="sxs-lookup"><span data-stu-id="ab802-151">This declaration places the designer in a special namespace reserved for design-related types.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. <span data-ttu-id="ab802-152">定义`MarqueeControlRootDesigner`类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="ab802-152">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="ab802-153">在构造函数主体中插入语句。<xref:System.Diagnostics.Trace.WriteLine%2A></span><span class="sxs-lookup"><span data-stu-id="ab802-153">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="ab802-154">这对于调试很有用。</span><span class="sxs-lookup"><span data-stu-id="ab802-154">This will be useful for debugging.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a><span data-ttu-id="ab802-155">创建自定义控件的实例</span><span class="sxs-lookup"><span data-stu-id="ab802-155">Create an instance of your custom control</span></span>

1. <span data-ttu-id="ab802-156">向`MarqueeControlTest`项目中<xref:System.Windows.Forms.UserControl>添加新项。</span><span class="sxs-lookup"><span data-stu-id="ab802-156">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="ab802-157">为新的源文件指定基名称**DemoMarqueeControl**。</span><span class="sxs-lookup"><span data-stu-id="ab802-157">Give the new source file a base name of **DemoMarqueeControl**.</span></span>

2. <span data-ttu-id="ab802-158">在**代码编辑器**中打开文件。`DemoMarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-158">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="ab802-159">在该文件的顶部, 导入`MarqueeControlLibrary`命名空间:</span><span class="sxs-lookup"><span data-stu-id="ab802-159">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. <span data-ttu-id="ab802-160">更改的`DemoMarqueeControl`声明以`MarqueeControl`从类继承。</span><span class="sxs-lookup"><span data-stu-id="ab802-160">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>

4. <span data-ttu-id="ab802-161">生成项目。</span><span class="sxs-lookup"><span data-stu-id="ab802-161">Build the project.</span></span>

5. <span data-ttu-id="ab802-162">在 Windows 窗体设计器中打开 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="ab802-162">Open Form1 in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="ab802-163">找到 "**工具箱**" 中的 " **MarqueeControlTest 组件**" 选项卡并将其打开。</span><span class="sxs-lookup"><span data-stu-id="ab802-163">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="ab802-164">将从 "工具箱" 拖到窗体上。 `DemoMarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-164">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>

7. <span data-ttu-id="ab802-165">生成项目。</span><span class="sxs-lookup"><span data-stu-id="ab802-165">Build the project.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="ab802-166">设置项目以进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="ab802-166">Set Up the Project for Design-Time Debugging</span></span>

<span data-ttu-id="ab802-167">开发自定义设计时体验时, 必须调试控件和组件。</span><span class="sxs-lookup"><span data-stu-id="ab802-167">When you're developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="ab802-168">可以通过一种简单的方式将项目设置为允许在设计时进行调试。</span><span class="sxs-lookup"><span data-stu-id="ab802-168">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="ab802-169">有关详细信息，请参见[演练：在设计时](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)调试自定义 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ab802-169">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

1. <span data-ttu-id="ab802-170">右键单击该项目`MarqueeControlLibrary` , 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="ab802-170">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>

2. <span data-ttu-id="ab802-171">在 " **MarqueeControlLibrary 属性页**" 对话框中, 选择 "**调试**" 页。</span><span class="sxs-lookup"><span data-stu-id="ab802-171">In the **MarqueeControlLibrary Property Pages** dialog box, select the **Debug** page.</span></span>

3. <span data-ttu-id="ab802-172">在 "**启动操作**" 部分中, 选择 "**启动外部程序**"。</span><span class="sxs-lookup"><span data-stu-id="ab802-172">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="ab802-173">你将调试单独的 visual studio 实例, 因此单击!["visual studio](./media/visual-studio-ellipsis-button.png)属性窗口中的省略号按钮 (...), 浏览 visual studio IDE。</span><span class="sxs-lookup"><span data-stu-id="ab802-173">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="ab802-174">可执行文件的名称为 devenv, 如果安装到默认位置, 其路径为 *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<edition > \Common7\IDE\devenv.exe*。</span><span class="sxs-lookup"><span data-stu-id="ab802-174">The name of the executable file is devenv.exe, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE\devenv.exe*.</span></span>

4. <span data-ttu-id="ab802-175">选择“确定”关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="ab802-175">Select **OK** to close the dialog box.</span></span>

5. <span data-ttu-id="ab802-176">右键单击 "MarqueeControlLibrary" 项目, 然后选择 "**设为启动项目**" 来启用此调试配置。</span><span class="sxs-lookup"><span data-stu-id="ab802-176">Right-click the MarqueeControlLibrary project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="ab802-177">检查点</span><span class="sxs-lookup"><span data-stu-id="ab802-177">Checkpoint</span></span>

<span data-ttu-id="ab802-178">你现在已准备好调试自定义控件的设计时行为。</span><span class="sxs-lookup"><span data-stu-id="ab802-178">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="ab802-179">确定正确设置了调试环境后, 可以测试自定义控件和自定义设计器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="ab802-179">Once you've determined that the debugging environment is set up correctly, you'll test the association between the custom control and the custom designer.</span></span>

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="ab802-180">测试调试环境和设计器关联</span><span class="sxs-lookup"><span data-stu-id="ab802-180">To test the debugging environment and the designer association</span></span>

1. <span data-ttu-id="ab802-181">在**代码编辑器**中打开 MarqueeControlRootDesigner 源文件, 并在<xref:System.Diagnostics.Trace.WriteLine%2A>语句中放置一个断点。</span><span class="sxs-lookup"><span data-stu-id="ab802-181">Open the MarqueeControlRootDesigner source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>

2. <span data-ttu-id="ab802-182">按**F5**启动调试会话。</span><span class="sxs-lookup"><span data-stu-id="ab802-182">Press **F5** to start the debugging session.</span></span>

   <span data-ttu-id="ab802-183">创建 Visual Studio 的新实例。</span><span class="sxs-lookup"><span data-stu-id="ab802-183">A new instance of Visual Studio is created.</span></span>

3. <span data-ttu-id="ab802-184">在 Visual Studio 的新实例中, 打开 MarqueeControlTest 解决方案。</span><span class="sxs-lookup"><span data-stu-id="ab802-184">In the new instance of Visual Studio, open the MarqueeControlTest solution.</span></span> <span data-ttu-id="ab802-185">通过从 "**文件**" 菜单中选择 "**最近使用的项目**", 可以轻松地找到解决方案。</span><span class="sxs-lookup"><span data-stu-id="ab802-185">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="ab802-186">MarqueeControlTest 解决方案文件将作为最近使用过的文件列出。</span><span class="sxs-lookup"><span data-stu-id="ab802-186">The MarqueeControlTest.sln solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="ab802-187">`DemoMarqueeControl`在设计器中打开。</span><span class="sxs-lookup"><span data-stu-id="ab802-187">Open the `DemoMarqueeControl` in the designer.</span></span>

   <span data-ttu-id="ab802-188">Visual Studio 的调试实例获取焦点, 并在断点处停止执行。</span><span class="sxs-lookup"><span data-stu-id="ab802-188">The debugging instance of Visual Studio obtains focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="ab802-189">按**F5**继续调试会话。</span><span class="sxs-lookup"><span data-stu-id="ab802-189">Press **F5** to continue the debugging session.</span></span>

<span data-ttu-id="ab802-190">此时, 所有内容都已准备就绪, 可用于开发和调试自定义控件及其关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="ab802-190">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="ab802-191">本文的其余部分重点介绍了实现控件和设计器功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ab802-191">The remainder of this article concentrates on the details of implementing features of the control and the designer.</span></span>

## <a name="implement-the-custom-control"></a><span data-ttu-id="ab802-192">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="ab802-192">Implement the Custom Control</span></span>

<span data-ttu-id="ab802-193">`MarqueeControl` 只需<xref:System.Windows.Forms.UserControl>进行一些自定义。</span><span class="sxs-lookup"><span data-stu-id="ab802-193">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="ab802-194">它公开了两个`Start`方法:, 用于启动字幕动画和`Stop`, 这会停止动画。</span><span class="sxs-lookup"><span data-stu-id="ab802-194">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="ab802-195">`Start` `Stop` `StopMarquee`因为包含实现接口的子控件,`StartMarquee`并枚举每个子控件并分别对每个子控件调用和方法`IMarqueeWidget` `MarqueeControl`实现`IMarqueeWidget`的。</span><span class="sxs-lookup"><span data-stu-id="ab802-195">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>

<span data-ttu-id="ab802-196">`MarqueeBorder` `MarqueeControl`和<xref:System.Windows.Forms.Control.PerformLayout%2A> <xref:System.Windows.Forms.Control.OnLayout%2A>控件的外观依赖于布局, 因此重写此类型的子控件上的方法和调用。 `MarqueeText`</span><span class="sxs-lookup"><span data-stu-id="ab802-196">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>

<span data-ttu-id="ab802-197">这是`MarqueeControl`自定义的范围。</span><span class="sxs-lookup"><span data-stu-id="ab802-197">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="ab802-198">运行时功能`MarqueeBorder`由和`MarqueeText`控件实现, 设计时`MarqueeBorderDesigner`功能由和`MarqueeControlRootDesigner`类实现。</span><span class="sxs-lookup"><span data-stu-id="ab802-198">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>

### <a name="to-implement-your-custom-control"></a><span data-ttu-id="ab802-199">实现自定义控件</span><span class="sxs-lookup"><span data-stu-id="ab802-199">To implement your custom control</span></span>

1. <span data-ttu-id="ab802-200">在**代码编辑器**中打开源文件。`MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-200">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="ab802-201">`Start`实现和`Stop`方法。</span><span class="sxs-lookup"><span data-stu-id="ab802-201">Implement the `Start` and `Stop` methods.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <span data-ttu-id="ab802-202">重写 <xref:System.Windows.Forms.Control.OnLayout%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ab802-202">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a><span data-ttu-id="ab802-203">为自定义控件创建子控件</span><span class="sxs-lookup"><span data-stu-id="ab802-203">Create a Child Control for Your Custom Control</span></span>

<span data-ttu-id="ab802-204">将承载两种类型的子控件`MarqueeBorder` : 控件和`MarqueeText`控件。 `MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-204">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>

- <span data-ttu-id="ab802-205">`MarqueeBorder`：此控件围绕边缘绘制 "光源" 边框。</span><span class="sxs-lookup"><span data-stu-id="ab802-205">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="ab802-206">灯光按顺序闪烁, 使其看起来像是在边框上移动。</span><span class="sxs-lookup"><span data-stu-id="ab802-206">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="ab802-207">光源的闪烁速度由一个名`UpdatePeriod`为的属性控制。</span><span class="sxs-lookup"><span data-stu-id="ab802-207">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="ab802-208">其他几个自定义属性确定控件外观的其他方面。</span><span class="sxs-lookup"><span data-stu-id="ab802-208">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="ab802-209">两个称为`StartMarquee`和`StopMarquee`的方法控制动画的开始和停止时间。</span><span class="sxs-lookup"><span data-stu-id="ab802-209">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>

- <span data-ttu-id="ab802-210">`MarqueeText`：此控件绘制闪烁的字符串。</span><span class="sxs-lookup"><span data-stu-id="ab802-210">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="ab802-211">与控件一样, 文本闪烁的速度由`UpdatePeriod`属性控制。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="ab802-211">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="ab802-212">控件还具有`StopMarquee`与`StartMarquee` 控件`MarqueeBorder`共有的和方法。 `MarqueeText`</span><span class="sxs-lookup"><span data-stu-id="ab802-212">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>

<span data-ttu-id="ab802-213">在设计时, `MarqueeControlRootDesigner`可以将这两个控件类型添加到中的`MarqueeControl`任意组合。</span><span class="sxs-lookup"><span data-stu-id="ab802-213">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>

<span data-ttu-id="ab802-214">这两个控件的常见功能分解为一个名`IMarqueeWidget`为的接口。</span><span class="sxs-lookup"><span data-stu-id="ab802-214">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="ab802-215">这样, 就可以发现任何与选框相关的子控件, 并使它们特别对待。 `MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-215">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>

<span data-ttu-id="ab802-216">若要实现定期动画功能, 您将使用<xref:System.ComponentModel.BackgroundWorker>命名空间中<xref:System.ComponentModel?displayProperty=nameWithType>的对象。</span><span class="sxs-lookup"><span data-stu-id="ab802-216">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="ab802-217">可以使用<xref:System.Windows.Forms.Timer>对象, 但当存在许多`IMarqueeWidget`对象时, 单个 UI 线程可能无法跟上动画。</span><span class="sxs-lookup"><span data-stu-id="ab802-217">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>

### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="ab802-218">为自定义控件创建子控件</span><span class="sxs-lookup"><span data-stu-id="ab802-218">To create a child control for your custom control</span></span>

1. <span data-ttu-id="ab802-219">向`MarqueeControlLibrary`项目中添加一个新的类项。</span><span class="sxs-lookup"><span data-stu-id="ab802-219">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ab802-220">为新的源文件命名为 "IMarqueeWidget" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="ab802-220">Give the new source file a base name of "IMarqueeWidget."</span></span>

2. <span data-ttu-id="ab802-221">在代码**编辑器**中打开`class` `interface`源文件, 并将声明从更改为: `IMarqueeWidget`</span><span class="sxs-lookup"><span data-stu-id="ab802-221">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. <span data-ttu-id="ab802-222">将以下代码添加到`IMarqueeWidget`接口, 以公开操作字幕动画的两个方法和属性:</span><span class="sxs-lookup"><span data-stu-id="ab802-222">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. <span data-ttu-id="ab802-223">向`MarqueeControlLibrary`项目中添加一个新的**自定义控件**项。</span><span class="sxs-lookup"><span data-stu-id="ab802-223">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ab802-224">为新的源文件命名为 "MarqueeText" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="ab802-224">Give the new source file a base name of "MarqueeText."</span></span>

5. <span data-ttu-id="ab802-225">将组件从 " `MarqueeText`工具箱" 拖到控件上。 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="ab802-225">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="ab802-226">此组件允许`MarqueeText`控件以异步方式更新自身。</span><span class="sxs-lookup"><span data-stu-id="ab802-226">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>

6. <span data-ttu-id="ab802-227">在 "**属性**" 窗口中, <xref:System.ComponentModel.BackgroundWorker>将组件`WorkerReportsProgress`的<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>和属性设置为 " **true**"。</span><span class="sxs-lookup"><span data-stu-id="ab802-227">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to **true**.</span></span> <span data-ttu-id="ab802-228">这些设置使<xref:System.ComponentModel.BackgroundWorker>组件可以定期<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>引发事件并取消异步更新。</span><span class="sxs-lookup"><span data-stu-id="ab802-228">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span>

   <span data-ttu-id="ab802-229">有关详细信息, 请参阅[BackgroundWorker 组件](backgroundworker-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ab802-229">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

7. <span data-ttu-id="ab802-230">在**代码编辑器**中打开源文件。`MarqueeText`</span><span class="sxs-lookup"><span data-stu-id="ab802-230">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="ab802-231">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="ab802-231">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. <span data-ttu-id="ab802-232">更改的`MarqueeText`声明以从和中<xref:System.Windows.Forms.Label>继承以实现`IMarqueeWidget`接口:</span><span class="sxs-lookup"><span data-stu-id="ab802-232">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. <span data-ttu-id="ab802-233">声明与公开的属性相对应的实例变量, 并在构造函数中对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="ab802-233">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="ab802-234">字段确定是否要以`LightColor`属性指定的颜色绘制文本。 `isLit`</span><span class="sxs-lookup"><span data-stu-id="ab802-234">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. <span data-ttu-id="ab802-235">实现 `IMarqueeWidget` 接口。</span><span class="sxs-lookup"><span data-stu-id="ab802-235">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="ab802-236">`StartMarquee`和方法`StopMarquee`调用组件的<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>和方法<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>来启动和停止动画。 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="ab802-236">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="ab802-237"><xref:System.ComponentModel.CategoryAttribute.Category%2A> 和<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>特性应用于属性,使其显示在名为"Marquee"属性窗口的自定义部分中。`UpdatePeriod`</span><span class="sxs-lookup"><span data-stu-id="ab802-237">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. <span data-ttu-id="ab802-238">实现属性访问器。</span><span class="sxs-lookup"><span data-stu-id="ab802-238">Implement the property accessors.</span></span> <span data-ttu-id="ab802-239">将向客户端公开两个属性`LightColor` : `DarkColor`和。</span><span class="sxs-lookup"><span data-stu-id="ab802-239">You'll expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="ab802-240"><xref:System.ComponentModel.CategoryAttribute.Category%2A> 和<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>属性应用于这些属性, 因此属性显示在名为 "Marquee" 属性窗口的自定义部分中。</span><span class="sxs-lookup"><span data-stu-id="ab802-240">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. <span data-ttu-id="ab802-241">实现<xref:System.ComponentModel.BackgroundWorker> 组件和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件的处理程序。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="ab802-241">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="ab802-242">事件处理程序休眠`UpdatePeriod`指定的毫秒数, 并引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件, 直到代码通过调用<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>停止动画。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="ab802-242">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="ab802-243"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序在其亮状态和暗状态之间切换文本, 以显示闪烁的外观。</span><span class="sxs-lookup"><span data-stu-id="ab802-243">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. <span data-ttu-id="ab802-244">重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法以启用动画。</span><span class="sxs-lookup"><span data-stu-id="ab802-244">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. <span data-ttu-id="ab802-245">按**F6**生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="ab802-245">Press **F6** to build the solution.</span></span>

## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="ab802-246">创建 MarqueeBorder 子控件</span><span class="sxs-lookup"><span data-stu-id="ab802-246">Create the MarqueeBorder Child Control</span></span>

<span data-ttu-id="ab802-247">`MarqueeBorder` 控件`MarqueeText`比控件稍微复杂一些。</span><span class="sxs-lookup"><span data-stu-id="ab802-247">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="ab802-248">它具有更多属性, 并且<xref:System.Windows.Forms.Control.OnPaint%2A>方法中的动画更多。</span><span class="sxs-lookup"><span data-stu-id="ab802-248">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="ab802-249">原则上, 它非常类似`MarqueeText`于控件。</span><span class="sxs-lookup"><span data-stu-id="ab802-249">In principle, it is quite similar to the `MarqueeText` control.</span></span>

<span data-ttu-id="ab802-250">由于控件可以有子控件, 因此需要<xref:System.Windows.Forms.Control.Layout>知道事件。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="ab802-250">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>

### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="ab802-251">创建 MarqueeBorder 控件</span><span class="sxs-lookup"><span data-stu-id="ab802-251">To create the MarqueeBorder control</span></span>

1. <span data-ttu-id="ab802-252">向`MarqueeControlLibrary`项目中添加一个新的**自定义控件**项。</span><span class="sxs-lookup"><span data-stu-id="ab802-252">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ab802-253">为新的源文件命名为 "MarqueeBorder" 的基名称。</span><span class="sxs-lookup"><span data-stu-id="ab802-253">Give the new source file a base name of "MarqueeBorder."</span></span>

2. <span data-ttu-id="ab802-254">将组件从 " `MarqueeBorder`工具箱" 拖到控件上。 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="ab802-254">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="ab802-255">此组件允许`MarqueeBorder`控件以异步方式更新自身。</span><span class="sxs-lookup"><span data-stu-id="ab802-255">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>

3. <span data-ttu-id="ab802-256">在 "**属性**" 窗口中, <xref:System.ComponentModel.BackgroundWorker>将组件`WorkerReportsProgress`的<xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>和属性设置为 " **true**"。</span><span class="sxs-lookup"><span data-stu-id="ab802-256">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to **true**.</span></span> <span data-ttu-id="ab802-257">这些设置使<xref:System.ComponentModel.BackgroundWorker>组件可以定期<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>引发事件并取消异步更新。</span><span class="sxs-lookup"><span data-stu-id="ab802-257">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="ab802-258">有关详细信息, 请参阅[BackgroundWorker 组件](backgroundworker-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ab802-258">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

4. <span data-ttu-id="ab802-259">在 "**属性**" 窗口中, 选择 "**事件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ab802-259">In the **Properties** window, select the **Events** button.</span></span> <span data-ttu-id="ab802-260">为<xref:System.ComponentModel.BackgroundWorker.DoWork> 和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件附加处理程序。</span><span class="sxs-lookup"><span data-stu-id="ab802-260">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

5. <span data-ttu-id="ab802-261">在**代码编辑器**中打开源文件。`MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="ab802-261">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="ab802-262">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="ab802-262">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. <span data-ttu-id="ab802-263">更改的`MarqueeBorder`声明以从和中<xref:System.Windows.Forms.Panel>继承以实现`IMarqueeWidget`接口。</span><span class="sxs-lookup"><span data-stu-id="ab802-263">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. <span data-ttu-id="ab802-264">声明两个枚举, 用于`MarqueeBorder`管理控件的状态`MarqueeSpinDirection`:, 确定灯光`MarqueeLightShape`围绕边框的 "旋转" 方向, 确定光源的形状 (方形或圆形)。</span><span class="sxs-lookup"><span data-stu-id="ab802-264">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="ab802-265">将这些声明放在`MarqueeBorder`类声明之前。</span><span class="sxs-lookup"><span data-stu-id="ab802-265">Place these declarations before the `MarqueeBorder` class declaration.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. <span data-ttu-id="ab802-266">声明与公开的属性相对应的实例变量, 并在构造函数中对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="ab802-266">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. <span data-ttu-id="ab802-267">实现 `IMarqueeWidget` 接口。</span><span class="sxs-lookup"><span data-stu-id="ab802-267">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="ab802-268">`StartMarquee`和方法`StopMarquee`调用组件的<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>和方法<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>来启动和停止动画。 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="ab802-268">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="ab802-269">由于控件可以包含子控件, 因此该`StartMarquee`方法将枚举所有子控件, `StartMarquee`并调用实现`IMarqueeWidget`的这些子控件。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="ab802-269">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="ab802-270">`StopMarquee`方法具有类似的实现。</span><span class="sxs-lookup"><span data-stu-id="ab802-270">The `StopMarquee` method has a similar implementation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. <span data-ttu-id="ab802-271">实现属性访问器。</span><span class="sxs-lookup"><span data-stu-id="ab802-271">Implement the property accessors.</span></span> <span data-ttu-id="ab802-272">`MarqueeBorder`控件具有几个用于控制其外观的属性。</span><span class="sxs-lookup"><span data-stu-id="ab802-272">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. <span data-ttu-id="ab802-273">实现<xref:System.ComponentModel.BackgroundWorker> 组件和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件的处理程序。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="ab802-273">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="ab802-274">事件处理程序休眠`UpdatePeriod`指定的毫秒数, 并引发<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件, 直到代码通过调用<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>停止动画。 <xref:System.ComponentModel.BackgroundWorker.DoWork></span><span class="sxs-lookup"><span data-stu-id="ab802-274">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="ab802-275">该<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件处理程序会递增 "基本" 光源的位置, 从该光源确定另一个光源的亮/暗状态, 并<xref:System.Windows.Forms.Control.Refresh%2A>调用方法来使控件重绘自身。</span><span class="sxs-lookup"><span data-stu-id="ab802-275">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. <span data-ttu-id="ab802-276">实现帮助器方法`IsLit`和。 `DrawLight`</span><span class="sxs-lookup"><span data-stu-id="ab802-276">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>

    <span data-ttu-id="ab802-277">`IsLit`方法确定指定位置的光线颜色。</span><span class="sxs-lookup"><span data-stu-id="ab802-277">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="ab802-278">"亮" 的灯光以`LightColor`属性给定的颜色进行绘制, 而 "深色" 的光源则以`DarkColor`属性给定的颜色进行绘制。</span><span class="sxs-lookup"><span data-stu-id="ab802-278">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>

    <span data-ttu-id="ab802-279">`DrawLight`方法使用适当的颜色、形状和位置绘制光。</span><span class="sxs-lookup"><span data-stu-id="ab802-279">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <span data-ttu-id="ab802-280">重写<xref:System.Windows.Forms.Control.OnPaint%2A>和方法。 <xref:System.Windows.Forms.Control.OnLayout%2A></span><span class="sxs-lookup"><span data-stu-id="ab802-280">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>

    <span data-ttu-id="ab802-281">方法沿`MarqueeBorder`控件边缘绘制灯光。 <xref:System.Windows.Forms.Control.OnPaint%2A></span><span class="sxs-lookup"><span data-stu-id="ab802-281">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>

    <span data-ttu-id="ab802-282">由于方法依赖于`MarqueeBorder`控件的尺寸, 因此每当布局发生更改时都需要调用该方法。 <xref:System.Windows.Forms.Control.OnPaint%2A></span><span class="sxs-lookup"><span data-stu-id="ab802-282">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="ab802-283">若要实现此目的<xref:System.Windows.Forms.Control.OnLayout%2A> , 请<xref:System.Windows.Forms.Control.Refresh%2A>重写并调用。</span><span class="sxs-lookup"><span data-stu-id="ab802-283">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="ab802-284">创建自定义设计器以隐藏和筛选属性</span><span class="sxs-lookup"><span data-stu-id="ab802-284">Create a Custom Designer to Shadow and Filter Properties</span></span>

<span data-ttu-id="ab802-285">`MarqueeControlRootDesigner`类提供根设计器的实现。</span><span class="sxs-lookup"><span data-stu-id="ab802-285">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="ab802-286">除了在上`MarqueeControl`运行的此设计器外, 还需要一个专门`MarqueeBorder`与控件关联的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="ab802-286">In addition to this designer, which operates on the `MarqueeControl`, you'll need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="ab802-287">此设计器提供适用于自定义根设计器的上下文的自定义行为。</span><span class="sxs-lookup"><span data-stu-id="ab802-287">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>

<span data-ttu-id="ab802-288">具体而言, `MarqueeBorderDesigner`将 "隐藏" 并筛选`MarqueeBorder`控件上的某些属性, 更改与设计环境的交互。</span><span class="sxs-lookup"><span data-stu-id="ab802-288">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>

<span data-ttu-id="ab802-289">截获对组件的属性访问器的调用称为 "隐藏"。</span><span class="sxs-lookup"><span data-stu-id="ab802-289">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="ab802-290">它允许设计器跟踪用户设置的值, 还可以选择将该值传递给所设计的组件。</span><span class="sxs-lookup"><span data-stu-id="ab802-290">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>

<span data-ttu-id="ab802-291">在<xref:System.Windows.Forms.Control.Visible%2A>此示例中, 和<xref:System.Windows.Forms.Control.Enabled%2A>属性`MarqueeBorderDesigner`将由隐藏`MarqueeBorder` , 这会阻止用户在设计时使控件不可见或处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="ab802-291">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>

<span data-ttu-id="ab802-292">设计器还可以添加和移除属性。</span><span class="sxs-lookup"><span data-stu-id="ab802-292">Designers can also add and remove properties.</span></span> <span data-ttu-id="ab802-293">在此示例中, <xref:System.Windows.Forms.Control.Padding%2A>将在设计时删除属性, `MarqueeBorder`因为控件以编程方式基于`LightSize`属性指定的灯光大小设置填充。</span><span class="sxs-lookup"><span data-stu-id="ab802-293">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>

<span data-ttu-id="ab802-294">的基类`MarqueeBorderDesigner`为<xref:System.ComponentModel.Design.ComponentDesigner>, 它具有可在设计时更改控件所公开的特性、属性和事件的方法:</span><span class="sxs-lookup"><span data-stu-id="ab802-294">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

<span data-ttu-id="ab802-295">使用这些方法更改组件的公共接口时, 请遵循以下规则:</span><span class="sxs-lookup"><span data-stu-id="ab802-295">When changing the public interface of a component using these methods, follow these rules:</span></span>

- <span data-ttu-id="ab802-296">仅在`PreFilter`方法中添加或删除项</span><span class="sxs-lookup"><span data-stu-id="ab802-296">Add or remove items in the `PreFilter` methods only</span></span>

- <span data-ttu-id="ab802-297">仅修改方法中的`PostFilter`现有项</span><span class="sxs-lookup"><span data-stu-id="ab802-297">Modify existing items in the `PostFilter` methods only</span></span>

- <span data-ttu-id="ab802-298">始终在`PreFilter`方法中首先调用基实现</span><span class="sxs-lookup"><span data-stu-id="ab802-298">Always call the base implementation first in the `PreFilter` methods</span></span>

- <span data-ttu-id="ab802-299">始终在`PostFilter`方法中最后调用基本实现</span><span class="sxs-lookup"><span data-stu-id="ab802-299">Always call the base implementation last in the `PostFilter` methods</span></span>

<span data-ttu-id="ab802-300">遵循这些规则可确保设计时环境中的所有设计器都具有设计中所有组件的一致视图。</span><span class="sxs-lookup"><span data-stu-id="ab802-300">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>

<span data-ttu-id="ab802-301"><xref:System.ComponentModel.Design.ComponentDesigner>类提供字典, 用于管理隐藏属性的值, 从而使您不必创建特定的实例变量。</span><span class="sxs-lookup"><span data-stu-id="ab802-301">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="ab802-302">创建用于隐藏和筛选属性的自定义设计器</span><span class="sxs-lookup"><span data-stu-id="ab802-302">To create a custom designer to shadow and filter properties</span></span>

1. <span data-ttu-id="ab802-303">右键单击**设计**文件夹并添加一个新类。</span><span class="sxs-lookup"><span data-stu-id="ab802-303">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="ab802-304">为源文件指定基名称**MarqueeBorderDesigner**。</span><span class="sxs-lookup"><span data-stu-id="ab802-304">Give the source file a base name of **MarqueeBorderDesigner**.</span></span>

2. <span data-ttu-id="ab802-305">在**代码编辑器**中打开 MarqueeBorderDesigner 源文件。</span><span class="sxs-lookup"><span data-stu-id="ab802-305">Open the MarqueeBorderDesigner source file in the **Code Editor**.</span></span> <span data-ttu-id="ab802-306">在该文件的顶部, 导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="ab802-306">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. <span data-ttu-id="ab802-307">更改的`MarqueeBorderDesigner`声明以从<xref:System.Windows.Forms.Design.ParentControlDesigner>继承。</span><span class="sxs-lookup"><span data-stu-id="ab802-307">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>

    <span data-ttu-id="ab802-308">由于控件可以包含子控件, `MarqueeBorderDesigner`因此继承自<xref:System.Windows.Forms.Design.ParentControlDesigner>, 后者处理父子交互。 `MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="ab802-308">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. <span data-ttu-id="ab802-309">重写的<xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>基实现。</span><span class="sxs-lookup"><span data-stu-id="ab802-309">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <span data-ttu-id="ab802-310">实现 <xref:System.Windows.Forms.Control.Enabled%2A> 和 <xref:System.Windows.Forms.Control.Visible%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="ab802-310">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="ab802-311">这些实现将隐藏控件的属性。</span><span class="sxs-lookup"><span data-stu-id="ab802-311">These implementations shadow the control's properties.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a><span data-ttu-id="ab802-312">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="ab802-312">Handle Component Changes</span></span>

<span data-ttu-id="ab802-313">类为你`MarqueeControl`的实例提供自定义的设计时体验。 `MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="ab802-313">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="ab802-314">大多数设计时功能都是从<xref:System.Windows.Forms.Design.DocumentDesigner>类继承的。</span><span class="sxs-lookup"><span data-stu-id="ab802-314">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="ab802-315">你的代码将实现两个特定的自定义: 处理组件更改和添加设计器谓词。</span><span class="sxs-lookup"><span data-stu-id="ab802-315">Your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>

<span data-ttu-id="ab802-316">当用户设计其`MarqueeControl`实例时, 你的根设计器将跟踪`MarqueeControl`及其子控件的更改。</span><span class="sxs-lookup"><span data-stu-id="ab802-316">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="ab802-317">设计时环境提供了一种方便的服务<xref:System.ComponentModel.Design.IComponentChangeService>, 用于跟踪对组件状态的更改。</span><span class="sxs-lookup"><span data-stu-id="ab802-317">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>

<span data-ttu-id="ab802-318">通过使用<xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>方法查询环境来获取对此服务的引用。</span><span class="sxs-lookup"><span data-stu-id="ab802-318">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="ab802-319">如果查询成功, 设计器可以为<xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged>事件附加处理程序, 并执行在设计时保持一致状态所需的任何任务。</span><span class="sxs-lookup"><span data-stu-id="ab802-319">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>

<span data-ttu-id="ab802-320">对于`MarqueeControlRootDesigner`类, 您将对包含的`MarqueeControl`每个`IMarqueeWidget`对象<xref:System.Windows.Forms.Control.Refresh%2A>调用方法。</span><span class="sxs-lookup"><span data-stu-id="ab802-320">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="ab802-321">这会使`IMarqueeWidget`对象在其父级的<xref:System.Windows.Forms.Control.Size%2A>属性 (如属性) 发生更改时正确重绘自身。</span><span class="sxs-lookup"><span data-stu-id="ab802-321">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>

### <a name="to-handle-component-changes"></a><span data-ttu-id="ab802-322">处理组件更改</span><span class="sxs-lookup"><span data-stu-id="ab802-322">To handle component changes</span></span>

1. <span data-ttu-id="ab802-323">在代码**编辑器**中打开<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 源文件,并重写方法。`MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="ab802-323">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="ab802-324">调用的基实现<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> , 并查询。 <xref:System.ComponentModel.Design.IComponentChangeService></span><span class="sxs-lookup"><span data-stu-id="ab802-324">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <span data-ttu-id="ab802-325"><xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>实现事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ab802-325">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="ab802-326">测试发送组件的类型, 如果它是`IMarqueeWidget`, 则调用其<xref:System.Windows.Forms.Control.Refresh%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ab802-326">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="ab802-327">将设计器谓词添加到自定义设计器</span><span class="sxs-lookup"><span data-stu-id="ab802-327">Add Designer Verbs to your Custom Designer</span></span>

<span data-ttu-id="ab802-328">设计器谓词是链接到事件处理程序的菜单命令。</span><span class="sxs-lookup"><span data-stu-id="ab802-328">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="ab802-329">设计器谓词在设计时添加到组件的快捷菜单中。</span><span class="sxs-lookup"><span data-stu-id="ab802-329">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="ab802-330">有关详细信息，请参阅 <xref:System.ComponentModel.Design.DesignerVerb> 。</span><span class="sxs-lookup"><span data-stu-id="ab802-330">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>

<span data-ttu-id="ab802-331">你将向设计器添加两个设计器谓词:**运行测试**和**停止测试**。</span><span class="sxs-lookup"><span data-stu-id="ab802-331">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="ab802-332">这些谓词允许您`MarqueeControl`在设计时查看的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="ab802-332">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="ab802-333">这些谓词将添加到`MarqueeControlRootDesigner`。</span><span class="sxs-lookup"><span data-stu-id="ab802-333">These verbs will be added to `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="ab802-334">调用 "**运行测试**" 时, verb 事件处理程序将对`StartMarquee`调用方法。 `MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-334">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="ab802-335">调用**停止测试**时, verb 事件处理程序将对调用`StopMarquee`方法。 `MarqueeControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-335">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="ab802-336">`StartMarquee`和`IMarqueeWidget` `IMarqueeWidget`方法的实现在实现的包含控件上调用这些方法, 因此任何包含的控件也将参与测试。 `StopMarquee`</span><span class="sxs-lookup"><span data-stu-id="ab802-336">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>

### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="ab802-337">将设计器谓词添加到自定义设计器</span><span class="sxs-lookup"><span data-stu-id="ab802-337">To add designer verbs to your custom designers</span></span>

1. <span data-ttu-id="ab802-338">在类中, 添加名为`OnVerbRunTest`和`OnVerbStopTest`的事件处理程序。 `MarqueeControlRootDesigner`</span><span class="sxs-lookup"><span data-stu-id="ab802-338">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. <span data-ttu-id="ab802-339">将这些事件处理程序连接到相应的设计器谓词。</span><span class="sxs-lookup"><span data-stu-id="ab802-339">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="ab802-340">`MarqueeControlRootDesigner`<xref:System.ComponentModel.Design.DesignerVerbCollection>从其基类继承。</span><span class="sxs-lookup"><span data-stu-id="ab802-340">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="ab802-341">您将创建两个<xref:System.ComponentModel.Design.DesignerVerb>新的<xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>对象, 并在方法中将它们添加到此集合中。</span><span class="sxs-lookup"><span data-stu-id="ab802-341">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a><span data-ttu-id="ab802-342">创建自定义 UITypeEditor</span><span class="sxs-lookup"><span data-stu-id="ab802-342">Create a Custom UITypeEditor</span></span>

<span data-ttu-id="ab802-343">为用户创建自定义设计时体验时, 通常需要创建与属性窗口的自定义交互。</span><span class="sxs-lookup"><span data-stu-id="ab802-343">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="ab802-344">可以通过创建<xref:System.Drawing.Design.UITypeEditor>来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="ab802-344">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span>

<span data-ttu-id="ab802-345">`MarqueeBorder`控件公开属性窗口中的多个属性。</span><span class="sxs-lookup"><span data-stu-id="ab802-345">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="ab802-346">其中两个属性, `MarqueeSpinDirection` `MarqueeLightShape`由枚举表示。</span><span class="sxs-lookup"><span data-stu-id="ab802-346">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="ab802-347">为了说明 UI 类型编辑器的用法, 该`MarqueeLightShape`属性将具有关联<xref:System.Drawing.Design.UITypeEditor>的类。</span><span class="sxs-lookup"><span data-stu-id="ab802-347">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>

### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="ab802-348">创建自定义 UI 类型编辑器</span><span class="sxs-lookup"><span data-stu-id="ab802-348">To create a custom UI type editor</span></span>

1. <span data-ttu-id="ab802-349">在**代码编辑器**中打开源文件。`MarqueeBorder`</span><span class="sxs-lookup"><span data-stu-id="ab802-349">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>

2. <span data-ttu-id="ab802-350">在`MarqueeBorder`类的定义中, 声明一个派生自`LightShapeEditor` <xref:System.Drawing.Design.UITypeEditor>的类。</span><span class="sxs-lookup"><span data-stu-id="ab802-350">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <span data-ttu-id="ab802-351">声明一个<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>名`editorService`为的实例变量。</span><span class="sxs-lookup"><span data-stu-id="ab802-351">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <span data-ttu-id="ab802-352">重写 <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ab802-352">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="ab802-353">此实现返回<xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, 它指示设计环境如何`LightShapeEditor`显示。</span><span class="sxs-lookup"><span data-stu-id="ab802-353">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <span data-ttu-id="ab802-354">重写 <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ab802-354">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="ab802-355">此实现查询<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>对象的设计环境。</span><span class="sxs-lookup"><span data-stu-id="ab802-355">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="ab802-356">如果成功, 它将创建`LightShapeSelectionControl`一个。</span><span class="sxs-lookup"><span data-stu-id="ab802-356">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="ab802-357">调用方法来`LightShapeEditor`启动。 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A></span><span class="sxs-lookup"><span data-stu-id="ab802-357">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="ab802-358">此调用的返回值将返回到设计环境。</span><span class="sxs-lookup"><span data-stu-id="ab802-358">The return value from this invocation is returned to the design environment.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="ab802-359">为自定义 UITypeEditor 创建视图控件</span><span class="sxs-lookup"><span data-stu-id="ab802-359">Create a View Control for your Custom UITypeEditor</span></span>

<span data-ttu-id="ab802-360">属性支持两种类型的光源形状: `Square`和`Circle`。 `MarqueeLightShape`</span><span class="sxs-lookup"><span data-stu-id="ab802-360">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="ab802-361">您将创建一个仅用于以图形方式在属性窗口中显示这些值的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ab802-361">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="ab802-362">此自定义控件将由<xref:System.Drawing.Design.UITypeEditor>用于与属性窗口进行交互。</span><span class="sxs-lookup"><span data-stu-id="ab802-362">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="ab802-363">为自定义 UI 类型编辑器创建视图控件</span><span class="sxs-lookup"><span data-stu-id="ab802-363">To create a view control for your custom UI type editor</span></span>

1. <span data-ttu-id="ab802-364">向`MarqueeControlLibrary`项目中<xref:System.Windows.Forms.UserControl>添加新项。</span><span class="sxs-lookup"><span data-stu-id="ab802-364">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ab802-365">为新的源文件指定基名称**LightShapeSelectionControl**。</span><span class="sxs-lookup"><span data-stu-id="ab802-365">Give the new source file a base name of **LightShapeSelectionControl**.</span></span>

2. <span data-ttu-id="ab802-366">将两<xref:System.Windows.Forms.Panel>个控件从 `LightShapeSelectionControl`工具箱拖到上。</span><span class="sxs-lookup"><span data-stu-id="ab802-366">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="ab802-367">将它们`squarePanel`命名`circlePanel`为和。</span><span class="sxs-lookup"><span data-stu-id="ab802-367">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="ab802-368">并排排列它们。</span><span class="sxs-lookup"><span data-stu-id="ab802-368">Arrange them side by side.</span></span> <span data-ttu-id="ab802-369">将这<xref:System.Windows.Forms.Control.Size%2A>两个<xref:System.Windows.Forms.Panel>控件的属性设置为 **(60, 60)** 。</span><span class="sxs-lookup"><span data-stu-id="ab802-369">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to **(60, 60)**.</span></span> <span data-ttu-id="ab802-370">将`squarePanel`控件<xref:System.Windows.Forms.Control.Location%2A>的属性设置为 **(8, 10)** 。</span><span class="sxs-lookup"><span data-stu-id="ab802-370">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to **(8, 10)**.</span></span> <span data-ttu-id="ab802-371">将`circlePanel`控件<xref:System.Windows.Forms.Control.Location%2A>的属性设置为 **(80, 10)** 。</span><span class="sxs-lookup"><span data-stu-id="ab802-371">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to **(80, 10)**.</span></span> <span data-ttu-id="ab802-372">最后, 将的<xref:System.Windows.Forms.Control.Size%2A> `LightShapeSelectionControl`属性设置为 **(150, 80)** 。</span><span class="sxs-lookup"><span data-stu-id="ab802-372">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to **(150, 80)**.</span></span>

3. <span data-ttu-id="ab802-373">在**代码编辑器**中打开源文件。`LightShapeSelectionControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-373">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="ab802-374">在该文件的顶部, 导入<xref:System.Windows.Forms.Design?displayProperty=nameWithType>命名空间:</span><span class="sxs-lookup"><span data-stu-id="ab802-374">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. <span data-ttu-id="ab802-375">为<xref:System.Windows.Forms.Control.Click>和控件`circlePanel`实现事件处理程序。 `squarePanel`</span><span class="sxs-lookup"><span data-stu-id="ab802-375">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="ab802-376">这些方法调用<xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A>以结束自定义<xref:System.Drawing.Design.UITypeEditor>编辑会话。</span><span class="sxs-lookup"><span data-stu-id="ab802-376">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. <span data-ttu-id="ab802-377">声明一个<xref:System.Windows.Forms.Design.IWindowsFormsEditorService>名`editorService`为的实例变量。</span><span class="sxs-lookup"><span data-stu-id="ab802-377">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. <span data-ttu-id="ab802-378">声明一个`MarqueeLightShape`名`lightShapeValue`为的实例变量。</span><span class="sxs-lookup"><span data-stu-id="ab802-378">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. <span data-ttu-id="ab802-379">`squarePanel` <xref:System.Windows.Forms.Control.Click> `circlePanel`在构造函数中, <xref:System.Windows.Forms.Control.Click>将事件处理程序附加到和控件的事件。 `LightShapeSelectionControl`</span><span class="sxs-lookup"><span data-stu-id="ab802-379">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="ab802-380">另外, 定义将设计环境中的`MarqueeLightShape`值分配`lightShapeValue`给字段的构造函数重载。</span><span class="sxs-lookup"><span data-stu-id="ab802-380">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. <span data-ttu-id="ab802-381">在方法中, <xref:System.Windows.Forms.Control.Click>分离事件处理程序。 <xref:System.ComponentModel.Component.Dispose%2A></span><span class="sxs-lookup"><span data-stu-id="ab802-381">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. <span data-ttu-id="ab802-382">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="ab802-382">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="ab802-383">打开 LightShapeSelectionControl.Designer.cs 或 LightShapeSelectionControl 文件, 并删除该<xref:System.ComponentModel.Component.Dispose%2A>方法的默认定义。</span><span class="sxs-lookup"><span data-stu-id="ab802-383">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>

10. <span data-ttu-id="ab802-384">实现 `LightShape` 属性。</span><span class="sxs-lookup"><span data-stu-id="ab802-384">Implement the `LightShape` property.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. <span data-ttu-id="ab802-385">重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ab802-385">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ab802-386">此实现将绘制实心正方形和圆圈。</span><span class="sxs-lookup"><span data-stu-id="ab802-386">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="ab802-387">它还将通过在一个形状周围绘制边框来突出显示选定的值。</span><span class="sxs-lookup"><span data-stu-id="ab802-387">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a><span data-ttu-id="ab802-388">在设计器中测试自定义控件</span><span class="sxs-lookup"><span data-stu-id="ab802-388">Test your Custom Control in the Designer</span></span>

<span data-ttu-id="ab802-389">此时, 您可以生成`MarqueeControlLibrary`项目。</span><span class="sxs-lookup"><span data-stu-id="ab802-389">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="ab802-390">通过创建从`MarqueeControl`类继承的控件并在窗体上使用它来测试您的实现。</span><span class="sxs-lookup"><span data-stu-id="ab802-390">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>

### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="ab802-391">创建自定义 MarqueeControl 实现</span><span class="sxs-lookup"><span data-stu-id="ab802-391">To create a custom MarqueeControl implementation</span></span>

1. <span data-ttu-id="ab802-392">在 Windows 窗体设计器中打开 `DemoMarqueeControl`。</span><span class="sxs-lookup"><span data-stu-id="ab802-392">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="ab802-393">这会创建`DemoMarqueeControl`类型的实例, 并将其显示在`MarqueeControlRootDesigner`类型的实例中。</span><span class="sxs-lookup"><span data-stu-id="ab802-393">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>

2. <span data-ttu-id="ab802-394">在 "**工具箱**" 中, 打开 " **MarqueeControlLibrary 组件**" 选项卡。你将看到`MarqueeBorder`和`MarqueeText`控件可供选择。</span><span class="sxs-lookup"><span data-stu-id="ab802-394">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>

3. <span data-ttu-id="ab802-395">将`MarqueeBorder`控件的一个实例拖`DemoMarqueeControl`到设计图面上。</span><span class="sxs-lookup"><span data-stu-id="ab802-395">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="ab802-396">将此`MarqueeBorder`控件停靠到父控件。</span><span class="sxs-lookup"><span data-stu-id="ab802-396">Dock this `MarqueeBorder` control to the parent control.</span></span>

4. <span data-ttu-id="ab802-397">将`MarqueeText`控件的一个实例拖`DemoMarqueeControl`到设计图面上。</span><span class="sxs-lookup"><span data-stu-id="ab802-397">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>

5. <span data-ttu-id="ab802-398">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="ab802-398">Build the solution.</span></span>

6. <span data-ttu-id="ab802-399">右键单击`DemoMarqueeControl` , 然后从快捷菜单中选择 "**运行测试**" 选项以启动动画。</span><span class="sxs-lookup"><span data-stu-id="ab802-399">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="ab802-400">单击 "**停止测试**" 以停止动画。</span><span class="sxs-lookup"><span data-stu-id="ab802-400">Click **Stop Test** to stop the animation.</span></span>

7. <span data-ttu-id="ab802-401">在设计视图中打开“Form1”。</span><span class="sxs-lookup"><span data-stu-id="ab802-401">Open **Form1** in Design view.</span></span>

8. <span data-ttu-id="ab802-402">将两<xref:System.Windows.Forms.Button>个控件置于窗体上。</span><span class="sxs-lookup"><span data-stu-id="ab802-402">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="ab802-403">将它们`startButton`命名`stopButton`为和, 并<xref:System.Windows.Forms.Control.Text%2A>分别将属性值更改为 "**启动**" 和 "**停止**"。</span><span class="sxs-lookup"><span data-stu-id="ab802-403">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>

9. <span data-ttu-id="ab802-404">为<xref:System.Windows.Forms.Control.Click>这两个<xref:System.Windows.Forms.Button>控件实现事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ab802-404">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>

10. <span data-ttu-id="ab802-405">在 "**工具箱**" 中, 打开 " **MarqueeControlTest 组件**" 选项卡。你将看到`DemoMarqueeControl`可供选择。</span><span class="sxs-lookup"><span data-stu-id="ab802-405">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>

11. <span data-ttu-id="ab802-406">将的`DemoMarqueeControl`一个实例拖到**Form1**设计图面上。</span><span class="sxs-lookup"><span data-stu-id="ab802-406">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>

12. <span data-ttu-id="ab802-407">在事件处理程序中, 调用`Start`上`Stop` `DemoMarqueeControl`的和方法。 <xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="ab802-407">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>

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

13. <span data-ttu-id="ab802-408">`MarqueeControlTest`将项目设置为 "启动项目" 并运行该项目。</span><span class="sxs-lookup"><span data-stu-id="ab802-408">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="ab802-409">你将看到显示`DemoMarqueeControl`的窗体。</span><span class="sxs-lookup"><span data-stu-id="ab802-409">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="ab802-410">选择 "**启动**" 按钮以启动动画。</span><span class="sxs-lookup"><span data-stu-id="ab802-410">Select the **Start** button to start the animation.</span></span> <span data-ttu-id="ab802-411">应会看到文本闪烁, 而灯光在边框上移动。</span><span class="sxs-lookup"><span data-stu-id="ab802-411">You should see the text flashing and the lights moving around the border.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ab802-412">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ab802-412">Next steps</span></span>

<span data-ttu-id="ab802-413">`MarqueeControlLibrary`演示自定义控件和关联设计器的简单实现。</span><span class="sxs-lookup"><span data-stu-id="ab802-413">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="ab802-414">可以通过多种方式使此示例更加复杂:</span><span class="sxs-lookup"><span data-stu-id="ab802-414">You can make this sample more sophisticated in several ways:</span></span>

- <span data-ttu-id="ab802-415">在设计器中更改的`DemoMarqueeControl`属性值。</span><span class="sxs-lookup"><span data-stu-id="ab802-415">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="ab802-416">添加更`MarqueBorder`多控件并将它们停靠在其父实例中以创建嵌套效果。</span><span class="sxs-lookup"><span data-stu-id="ab802-416">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="ab802-417">试验的`UpdatePeriod`不同设置以及与光源相关的属性。</span><span class="sxs-lookup"><span data-stu-id="ab802-417">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>

- <span data-ttu-id="ab802-418">创作自己的`IMarqueeWidget`实现。</span><span class="sxs-lookup"><span data-stu-id="ab802-418">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="ab802-419">例如, 可以创建一个闪烁的 "霓虹灯号" 或包含多个图像的动画符号。</span><span class="sxs-lookup"><span data-stu-id="ab802-419">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>

- <span data-ttu-id="ab802-420">进一步自定义设计时体验。</span><span class="sxs-lookup"><span data-stu-id="ab802-420">Further customize the design-time experience.</span></span> <span data-ttu-id="ab802-421">您可以尝试隐藏比<xref:System.Windows.Forms.Control.Enabled%2A>和<xref:System.Windows.Forms.Control.Visible%2A>更多的属性, 并且可以添加新属性。</span><span class="sxs-lookup"><span data-stu-id="ab802-421">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="ab802-422">添加新的设计器谓词以简化诸如停靠子控件等常见任务。</span><span class="sxs-lookup"><span data-stu-id="ab802-422">Add new designer verbs to simplify common tasks like docking child controls.</span></span>

- <span data-ttu-id="ab802-423">`MarqueeControl`许可。</span><span class="sxs-lookup"><span data-stu-id="ab802-423">License the `MarqueeControl`.</span></span>

- <span data-ttu-id="ab802-424">控制如何序列化控件, 以及如何为控件生成代码。</span><span class="sxs-lookup"><span data-stu-id="ab802-424">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="ab802-425">有关详细信息, 请参阅[动态源代码生成和编译](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)。</span><span class="sxs-lookup"><span data-stu-id="ab802-425">For more information, see [Dynamic Source Code Generation and Compilation](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab802-426">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab802-426">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
