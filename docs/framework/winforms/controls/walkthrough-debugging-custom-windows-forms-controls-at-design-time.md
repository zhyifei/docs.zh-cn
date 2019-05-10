---
title: 演练：在设计时调试自定义 Windows 窗体控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: a8f228d334785cd880b06dbeda8f96550471599a
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211551"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="e2a79-102">演练：在设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="e2a79-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="e2a79-103">时创建自定义控件，您通常会发现它需要调试其设计时行为。</span><span class="sxs-lookup"><span data-stu-id="e2a79-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="e2a79-104">这是如果自定义设计器创作自定义控件尤其如此。</span><span class="sxs-lookup"><span data-stu-id="e2a79-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="e2a79-105">有关详细信息，请参阅[演练：创建 Windows 窗体控件都使用了 Visual Studio 设计时功能](creating-a-wf-control-design-time-features.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a79-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="e2a79-106">您可以调试使用 Visual Studio 中，您自定义控件，就像就像调试任何其他.NET Framework 类。</span><span class="sxs-lookup"><span data-stu-id="e2a79-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="e2a79-107">不同之处是待调试正在运行自定义控件的代码的 Visual Studio 的单独实例</span><span class="sxs-lookup"><span data-stu-id="e2a79-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>

<span data-ttu-id="e2a79-108">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="e2a79-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="e2a79-109">创建用于承载自定义控件的 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="e2a79-109">Creating a Windows Forms project to host your custom control</span></span>

- <span data-ttu-id="e2a79-110">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="e2a79-110">Creating a control library project</span></span>

- <span data-ttu-id="e2a79-111">将属性添加到自定义控件</span><span class="sxs-lookup"><span data-stu-id="e2a79-111">Adding a property to your custom control</span></span>

- <span data-ttu-id="e2a79-112">将自定义控件添加到主机窗体</span><span class="sxs-lookup"><span data-stu-id="e2a79-112">Adding your custom control to the host form</span></span>

- <span data-ttu-id="e2a79-113">设置设计时调试项目</span><span class="sxs-lookup"><span data-stu-id="e2a79-113">Setting up the project for design-time debugging</span></span>

- <span data-ttu-id="e2a79-114">在设计时调试自定义控件</span><span class="sxs-lookup"><span data-stu-id="e2a79-114">Debugging your custom control at design time</span></span>

<span data-ttu-id="e2a79-115">完成后，必须了解调试自定义控件的设计时行为所需的任务。</span><span class="sxs-lookup"><span data-stu-id="e2a79-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="e2a79-116">创建项目</span><span class="sxs-lookup"><span data-stu-id="e2a79-116">Create the project</span></span>

<span data-ttu-id="e2a79-117">第一步是创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="e2a79-117">The first step is to create the application project.</span></span> <span data-ttu-id="e2a79-118">将使用此项目以生成承载自定义控件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2a79-118">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="e2a79-119">在 Visual Studio 中，创建一个名为"DebuggingExample"的 Windows 应用程序项目 (**文件** > **新建** > **项目** > **可视化C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**).</span><span class="sxs-lookup"><span data-stu-id="e2a79-119">In Visual Studio, create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="e2a79-120">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="e2a79-120">Create the control library project</span></span>

1. <span data-ttu-id="e2a79-121">添加**Windows 控件库**到解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2a79-121">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="e2a79-122">添加一个新**UserControl** DebugControlLibrary 项目项。</span><span class="sxs-lookup"><span data-stu-id="e2a79-122">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="e2a79-123">有关详细信息，请参阅[如何：添加新项目项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="e2a79-123">For details, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="e2a79-124">新的源文件基名称指定为"DebugControl"。</span><span class="sxs-lookup"><span data-stu-id="e2a79-124">Give the new source file a base name of "DebugControl".</span></span>

3. <span data-ttu-id="e2a79-125">使用**解决方案资源管理器**，通过删除代码文件的基名称中删除项目的默认控件"`UserControl1`"。</span><span class="sxs-lookup"><span data-stu-id="e2a79-125">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="e2a79-126">有关详细信息，请参阅[如何：移除、 删除和排除项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="e2a79-126">For details, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

4. <span data-ttu-id="e2a79-127">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2a79-127">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="e2a79-128">检查点</span><span class="sxs-lookup"><span data-stu-id="e2a79-128">Checkpoint</span></span>

<span data-ttu-id="e2a79-129">此时，你将能够查看自定义控件**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="e2a79-129">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="e2a79-130">若要检查您的进度，查找名为新选项卡**DebugControlLibrary 组件**并单击以选择它。</span><span class="sxs-lookup"><span data-stu-id="e2a79-130">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="e2a79-131">在打开时将看到控件列为**DebugControl**使用其旁边的默认图标。</span><span class="sxs-lookup"><span data-stu-id="e2a79-131">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="e2a79-132">将属性添加到自定义控件</span><span class="sxs-lookup"><span data-stu-id="e2a79-132">Add a property to your custom control</span></span>

<span data-ttu-id="e2a79-133">若要演示自定义控件的代码运行在设计时，将添加一个属性，并实现属性的代码中设置断点。</span><span class="sxs-lookup"><span data-stu-id="e2a79-133">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="e2a79-134">打开**DebugControl**中**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e2a79-134">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="e2a79-135">将以下代码添加到类定义：</span><span class="sxs-lookup"><span data-stu-id="e2a79-135">Add the following code to the class definition:</span></span>

    ```vb
    Private demoStringValue As String = Nothing
    <BrowsableAttribute(true)>
    Public Property DemoString() As String

        Get
            Return Me.demoStringValue
        End Get

        Set(ByVal value As String)
            Me.demoStringValue = value
        End Set

    End Property
    ```

    ```csharp
    private string demoStringValue = null;
    [Browsable(true)]
    public string DemoString
    {
        get
        {
            return this.demoStringValue;
        }
        set
        {
            demoStringValue = value;
        }
    }
    ```

2. <span data-ttu-id="e2a79-136">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2a79-136">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="e2a79-137">将自定义控件添加到主机窗体</span><span class="sxs-lookup"><span data-stu-id="e2a79-137">Add your custom control to the host form</span></span>

<span data-ttu-id="e2a79-138">若要调试自定义控件的设计时行为，将主机窗体上将自定义控件类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="e2a79-138">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="e2a79-139">在"DebuggingExample"项目中，打开在 Form1 **Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="e2a79-139">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="e2a79-140">在中**工具箱**，打开**DebugControlLibrary 组件**选项卡，将**DebugControl**拖到窗体的实例。</span><span class="sxs-lookup"><span data-stu-id="e2a79-140">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="e2a79-141">查找`DemoString`中的自定义属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="e2a79-141">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="e2a79-142">请注意，您可以更改其值，就像任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="e2a79-142">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="e2a79-143">此外请注意，当`DemoString`属性处于选中状态，该属性的描述字符串会显示在底部**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="e2a79-143">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="e2a79-144">设置项目以便进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="e2a79-144">Set up the project for design-time debugging</span></span>

<span data-ttu-id="e2a79-145">若要调试自定义控件的设计时行为，将调试正在运行自定义控件的代码的 Visual Studio 的单独实例。</span><span class="sxs-lookup"><span data-stu-id="e2a79-145">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="e2a79-146">右键单击**DebugControlLibrary**项目中**解决方案资源管理器**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="e2a79-146">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="e2a79-147">在中**DebugControlLibrary**属性表中，选择**调试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e2a79-147">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="e2a79-148">在中**启动操作**部分中，选择**启动外部程序**。</span><span class="sxs-lookup"><span data-stu-id="e2a79-148">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="e2a79-149">你将调试的单独实例的 Visual Studio 中，因此请单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以浏览 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="e2a79-149">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="e2a79-150">可执行文件的名称是**devenv.exe**，如果已安装到默认位置，其路径为 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe。</span><span class="sxs-lookup"><span data-stu-id="e2a79-150">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

3. <span data-ttu-id="e2a79-151">单击“确定”关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="e2a79-151">Click **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="e2a79-152">右键单击**DebugControlLibrary**项目，然后选择**设为启动项目**若要启用此调试配置。</span><span class="sxs-lookup"><span data-stu-id="e2a79-152">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="e2a79-153">在设计时调试自定义控件</span><span class="sxs-lookup"><span data-stu-id="e2a79-153">Debug your custom control at design time</span></span>

<span data-ttu-id="e2a79-154">现在已准备好调试自定义控件在设计模式下运行。</span><span class="sxs-lookup"><span data-stu-id="e2a79-154">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="e2a79-155">启动调试会话时，将创建 Visual Studio 的新实例，并且将以加载"DebuggingExample"解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2a79-155">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="e2a79-156">当你打开中的 Form1**窗体设计器**，将创建并将开始运行自定义控件的实例。</span><span class="sxs-lookup"><span data-stu-id="e2a79-156">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="e2a79-157">打开**DebugControl**中的源文件**代码编辑器**，将断点放在`Set`访问器的`DemoString`属性。</span><span class="sxs-lookup"><span data-stu-id="e2a79-157">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="e2a79-158">按 F5 启动调试会话。</span><span class="sxs-lookup"><span data-stu-id="e2a79-158">Press F5 to start the debugging session.</span></span> <span data-ttu-id="e2a79-159">请注意，创建 Visual Studio 的新实例。</span><span class="sxs-lookup"><span data-stu-id="e2a79-159">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="e2a79-160">你可以区分两种方法中的实例：</span><span class="sxs-lookup"><span data-stu-id="e2a79-160">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="e2a79-161">调试实例包含单词**运行**标题栏中</span><span class="sxs-lookup"><span data-stu-id="e2a79-161">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="e2a79-162">调试实例都有**启动**按钮及其**调试**禁用工具栏</span><span class="sxs-lookup"><span data-stu-id="e2a79-162">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

     <span data-ttu-id="e2a79-163">在调试实例中设置断点。</span><span class="sxs-lookup"><span data-stu-id="e2a79-163">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="e2a79-164">在 Visual Studio 的新实例中，打开"DebuggingExample"解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2a79-164">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="e2a79-165">您可以轻松地找到解决方案，通过选择**最近使用的项目**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="e2a79-165">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="e2a79-166">将列出"DebuggingExample.sln"解决方案文件，如最近使用的文件。</span><span class="sxs-lookup"><span data-stu-id="e2a79-166">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="e2a79-167">打开在 Form1**窗体设计器**，然后选择**DebugControl**控件。</span><span class="sxs-lookup"><span data-stu-id="e2a79-167">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="e2a79-168">更改 `DemoString` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="e2a79-168">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="e2a79-169">请注意，当提交更改时，Visual Studio 的调试实例获取焦点并且执行在断点处停止。</span><span class="sxs-lookup"><span data-stu-id="e2a79-169">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="e2a79-170">你可以单步执行属性访问器就像在任何其他代码一样。</span><span class="sxs-lookup"><span data-stu-id="e2a79-170">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="e2a79-171">在您完成与调试会话，请可以退出，请关闭 Visual Studio 的托管的实例，或单击**停止调试**调试实例中的按钮。</span><span class="sxs-lookup"><span data-stu-id="e2a79-171">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2a79-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e2a79-172">Next steps</span></span>

<span data-ttu-id="e2a79-173">现在，可以在设计时调试自定义控件，有许多可能的扩展与 Visual Studio IDE 的控件的交互。</span><span class="sxs-lookup"><span data-stu-id="e2a79-173">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="e2a79-174">可以使用<xref:System.ComponentModel.Component.DesignMode%2A>属性的<xref:System.ComponentModel.Component>类来编写代码，将仅在设计时执行。</span><span class="sxs-lookup"><span data-stu-id="e2a79-174">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="e2a79-175">有关详细信息，请参阅 <xref:System.ComponentModel.Component.DesignMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="e2a79-175">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="e2a79-176">有几个特性可应用于控件的属性，以处理与设计器的自定义控件的交互。</span><span class="sxs-lookup"><span data-stu-id="e2a79-176">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="e2a79-177">您可以找到这些属性在<xref:System.ComponentModel?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="e2a79-177">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="e2a79-178">自定义控件，可以编写自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="e2a79-178">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="e2a79-179">这样，您对使用由 Visual Studio 公开可扩展设计器基础结构的设计体验的完全控制。</span><span class="sxs-lookup"><span data-stu-id="e2a79-179">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="e2a79-180">有关详细信息，请参阅[演练：创建 Windows 窗体控件都使用了 Visual Studio 设计时功能](creating-a-wf-control-design-time-features.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a79-180">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2a79-181">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2a79-181">See also</span></span>

- [<span data-ttu-id="e2a79-182">演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="e2a79-182">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
- <span data-ttu-id="e2a79-183">[如何：访问设计时服务](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e2a79-183">[How to: Access Design-Time Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span></span>
- <span data-ttu-id="e2a79-184">[如何：在 Windows 窗体中访问设计时支持](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e2a79-184">[How to: Access Design-Time Support in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span></span>
