---
title: "演练：设计时调试自定义 Windows 窗体控件"
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fd38f6246d44bd24753d9c86a5b0b08819d3db7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="36b06-102">演练：设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="36b06-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="36b06-103">当你创建自定义控件时，你通常会发现它需调试其设计时行为。</span><span class="sxs-lookup"><span data-stu-id="36b06-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="36b06-104">这是如果自定义设计器创作的自定义控件尤其如此。</span><span class="sxs-lookup"><span data-stu-id="36b06-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="36b06-105">有关详细信息，请参阅[演练： 创建 Windows 窗体控件，采用利用的 Visual Studio 设计时功能](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)。</span><span class="sxs-lookup"><span data-stu-id="36b06-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="36b06-106">正如你将调试任何其他.NET Framework 类，你可以调试使用 Visual Studio 中，你自定义控件。</span><span class="sxs-lookup"><span data-stu-id="36b06-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="36b06-107">区别是，你将调试正在运行自定义控件的代码的 Visual Studio 的单独实例</span><span class="sxs-lookup"><span data-stu-id="36b06-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="36b06-108">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="36b06-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="36b06-109">创建用于承载自定义控件的 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="36b06-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="36b06-110">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="36b06-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="36b06-111">将属性添加到自定义控件</span><span class="sxs-lookup"><span data-stu-id="36b06-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="36b06-112">将自定义控件添加到宿主窗体</span><span class="sxs-lookup"><span data-stu-id="36b06-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="36b06-113">设置项目以便进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="36b06-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="36b06-114">在设计时调试自定义控件</span><span class="sxs-lookup"><span data-stu-id="36b06-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="36b06-115">完成后，你将会了解的调试自定义控件的设计时行为所需的任务。</span><span class="sxs-lookup"><span data-stu-id="36b06-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36b06-116">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="36b06-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="36b06-117">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="36b06-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="36b06-118">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="36b06-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="36b06-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="36b06-119">Creating the Project</span></span>  
 <span data-ttu-id="36b06-120">第一步是创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="36b06-120">The first step is to create the application project.</span></span> <span data-ttu-id="36b06-121">此项目将用于生成承载自定义控件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="36b06-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="36b06-122">要创建项目</span><span class="sxs-lookup"><span data-stu-id="36b06-122">To create the project</span></span>  
  
-   <span data-ttu-id="36b06-123">创建一个名为"DebuggingExample"的 Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="36b06-123">Create a Windows Application project called "DebuggingExample".</span></span> <span data-ttu-id="36b06-124">有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="36b06-124">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="36b06-125">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="36b06-125">Creating a Control Library Project</span></span>  
 <span data-ttu-id="36b06-126">下一步是创建控件库项目并设置自定义控件。</span><span class="sxs-lookup"><span data-stu-id="36b06-126">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="36b06-127">若要创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="36b06-127">To create the control library project</span></span>  
  
1.  <span data-ttu-id="36b06-128">添加**Windows 控件库**到解决方案的项目。</span><span class="sxs-lookup"><span data-stu-id="36b06-128">Add a **Windows Control Library** project to the solution.</span></span>  
  
2.  <span data-ttu-id="36b06-129">添加新**UserControl**到 DebugControlLibrary 项目项。</span><span class="sxs-lookup"><span data-stu-id="36b06-129">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="36b06-130">有关详细信息，请参阅[NIB： 如何： 添加新项目项](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)。</span><span class="sxs-lookup"><span data-stu-id="36b06-130">For details, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="36b06-131">为新的源文件提供一个"DebugControl"的基本名称。</span><span class="sxs-lookup"><span data-stu-id="36b06-131">Give the new source file a base name of "DebugControl".</span></span>  
  
3.  <span data-ttu-id="36b06-132">使用**解决方案资源管理器**，通过删除具有的基名称的代码文件中删除项目的默认控件"`UserControl1`"。</span><span class="sxs-lookup"><span data-stu-id="36b06-132">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="36b06-133">有关详细信息，请参阅[NIB： 如何： 删除、 删除和排除项](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)。</span><span class="sxs-lookup"><span data-stu-id="36b06-133">For details, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
4.  <span data-ttu-id="36b06-134">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="36b06-134">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="36b06-135">检查点</span><span class="sxs-lookup"><span data-stu-id="36b06-135">Checkpoint</span></span>  
 <span data-ttu-id="36b06-136">此时，你将能够看到自定义控件中的**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="36b06-136">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="36b06-137">若要检查你的进度</span><span class="sxs-lookup"><span data-stu-id="36b06-137">To check your progress</span></span>  
  
-   <span data-ttu-id="36b06-138">查找名为新选项卡**DebugControlLibrary 组件**单击以将其选中。</span><span class="sxs-lookup"><span data-stu-id="36b06-138">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="36b06-139">当它打开后时，你将看到列为控件**DebugControl**与它旁边的默认图标。</span><span class="sxs-lookup"><span data-stu-id="36b06-139">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="36b06-140">将属性添加到自定义控件</span><span class="sxs-lookup"><span data-stu-id="36b06-140">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="36b06-141">为了演示自定义控件的代码运行设计时，将添加属性，并实现属性的代码中设置断点。</span><span class="sxs-lookup"><span data-stu-id="36b06-141">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="36b06-142">若要将属性添加到自定义控件</span><span class="sxs-lookup"><span data-stu-id="36b06-142">To add a property to your custom control</span></span>  
  
1.  <span data-ttu-id="36b06-143">打开**DebugControl**中**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="36b06-143">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="36b06-144">将以下代码添加到类定义：</span><span class="sxs-lookup"><span data-stu-id="36b06-144">Add the following code to the class definition:</span></span>  
  
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
  
2.  <span data-ttu-id="36b06-145">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="36b06-145">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="36b06-146">将自定义控件添加到宿主窗体</span><span class="sxs-lookup"><span data-stu-id="36b06-146">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="36b06-147">若要调试你的自定义控件的设计时行为，将在主机窗体上将自定义控件类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="36b06-147">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="36b06-148">若要将自定义控件添加到宿主窗体</span><span class="sxs-lookup"><span data-stu-id="36b06-148">To add your custom control to the host form</span></span>  
  
1.  <span data-ttu-id="36b06-149">在"DebuggingExample"项目中，打开中的 form1 **Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="36b06-149">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="36b06-150">在**工具箱**，打开**DebugControlLibrary 组件**选项卡，将**DebugControl**拖到窗体的实例。</span><span class="sxs-lookup"><span data-stu-id="36b06-150">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3.  <span data-ttu-id="36b06-151">查找`DemoString`中的自定义属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="36b06-151">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="36b06-152">请注意，你可以更改其值，就像任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="36b06-152">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="36b06-153">另请注意，当`DemoString`选择属性后，该属性的描述字符串会显示在底部**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="36b06-153">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="36b06-154">设置项目以便进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="36b06-154">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="36b06-155">若要调试自定义控件的设计时行为，你将调试正在运行自定义控件的代码的 Visual Studio 的单独实例。</span><span class="sxs-lookup"><span data-stu-id="36b06-155">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="36b06-156">若要设置项目以便进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="36b06-156">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="36b06-157">右键单击**DebugControlLibrary**项目中**解决方案资源管理器**和选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="36b06-157">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="36b06-158">在**DebugControlLibrary**属性表中，选择**调试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="36b06-158">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="36b06-159">在**启动操作**部分中，选择**启动外部程序**。</span><span class="sxs-lookup"><span data-stu-id="36b06-159">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="36b06-160">你将调试的单独实例的 Visual Studio 中，因此单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以浏览 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="36b06-160">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="36b06-161">可执行文件的名称是**devenv.exe**，如果你已安装到默认位置，其路径为 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe。</span><span class="sxs-lookup"><span data-stu-id="36b06-161">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3.  <span data-ttu-id="36b06-162">单击“确定”关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="36b06-162">Click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="36b06-163">右键单击**DebugControlLibrary**项目，然后选择**设为启动项目**为启用此调试配置。</span><span class="sxs-lookup"><span data-stu-id="36b06-163">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="36b06-164">在设计时调试自定义控件</span><span class="sxs-lookup"><span data-stu-id="36b06-164">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="36b06-165">现在你已准备好调试自定义控件，因为它在设计模式下运行。</span><span class="sxs-lookup"><span data-stu-id="36b06-165">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="36b06-166">当你启动调试会话时，将创建 Visual Studio 的新实例，并将使用它以加载"DebuggingExample"解决方案。</span><span class="sxs-lookup"><span data-stu-id="36b06-166">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="36b06-167">当你打开中的 form1**窗体设计器**，自定义控件的实例将创建并将开始运行。</span><span class="sxs-lookup"><span data-stu-id="36b06-167">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="36b06-168">若要在设计时调试自定义控件</span><span class="sxs-lookup"><span data-stu-id="36b06-168">To debug your custom control at design time</span></span>  
  
1.  <span data-ttu-id="36b06-169">打开**DebugControl**中的源文件**代码编辑器**并将断点放置在`Set`的访问器`DemoString`属性。</span><span class="sxs-lookup"><span data-stu-id="36b06-169">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2.  <span data-ttu-id="36b06-170">按 F5 启动调试会话。</span><span class="sxs-lookup"><span data-stu-id="36b06-170">Press F5 to start the debugging session.</span></span> <span data-ttu-id="36b06-171">请注意，创建 Visual Studio 的新实例。</span><span class="sxs-lookup"><span data-stu-id="36b06-171">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="36b06-172">你可区分两种方式的实例：</span><span class="sxs-lookup"><span data-stu-id="36b06-172">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="36b06-173">调试实例都有单词**运行**其标题栏中</span><span class="sxs-lookup"><span data-stu-id="36b06-173">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="36b06-174">调试实例具有**启动**按钮上其**调试**禁用工具栏</span><span class="sxs-lookup"><span data-stu-id="36b06-174">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="36b06-175">调试实例中设置断点。</span><span class="sxs-lookup"><span data-stu-id="36b06-175">Your breakpoint is set in the debugging instance.</span></span>  
  
3.  <span data-ttu-id="36b06-176">在 Visual Studio 的新实例中，打开的"DebuggingExample"解决方案。</span><span class="sxs-lookup"><span data-stu-id="36b06-176">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="36b06-177">你可以轻松地找到解决方案，通过选择**最近项目**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="36b06-177">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="36b06-178">将列出"DebuggingExample.sln"解决方案文件，如最近使用的文件。</span><span class="sxs-lookup"><span data-stu-id="36b06-178">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="36b06-179">打开中的 form1**窗体设计器**和选择**DebugControl**控件。</span><span class="sxs-lookup"><span data-stu-id="36b06-179">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5.  <span data-ttu-id="36b06-180">更改的值`DemoString`属性。</span><span class="sxs-lookup"><span data-stu-id="36b06-180">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="36b06-181">请注意，在提交更改时，Visual Studio 的调试实例获取焦点并且执行在断点处停止。</span><span class="sxs-lookup"><span data-stu-id="36b06-181">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="36b06-182">你可以单步执行属性访问器就像你将任何其他代码。</span><span class="sxs-lookup"><span data-stu-id="36b06-182">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6.  <span data-ttu-id="36b06-183">在完成时与你的调试会话，可以退出解除 Visual Studio 的托管的实例，或单击**停止调试**调试实例中的按钮。</span><span class="sxs-lookup"><span data-stu-id="36b06-183">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="36b06-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="36b06-184">Next Steps</span></span>  
 <span data-ttu-id="36b06-185">现在，你可以在设计时调试自定义控件，有许多可能的展开与 Visual Studio IDE 的控件的交互。</span><span class="sxs-lookup"><span data-stu-id="36b06-185">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="36b06-186">你可以使用<xref:System.ComponentModel.Component.DesignMode%2A>属性<xref:System.ComponentModel.Component>将仅执行在设计时编写代码的类。</span><span class="sxs-lookup"><span data-stu-id="36b06-186">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="36b06-187">有关详细信息，请参阅<xref:System.ComponentModel.Component.DesignMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="36b06-187">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="36b06-188">有几个属性可应用于控件的属性，以处理与设计器的自定义控件的交互。</span><span class="sxs-lookup"><span data-stu-id="36b06-188">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="36b06-189">你可以找到这些属性中的<xref:System.ComponentModel?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="36b06-189">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="36b06-190">对于自定义控件，可以编写自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="36b06-190">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="36b06-191">这使你可以使用由 Visual Studio 公开的可扩展设计器基础结构的设计体验的完全控制。</span><span class="sxs-lookup"><span data-stu-id="36b06-191">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="36b06-192">有关详细信息，请参阅[演练： 创建 Windows 窗体控件，采用利用的 Visual Studio 设计时功能](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)。</span><span class="sxs-lookup"><span data-stu-id="36b06-192">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b06-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="36b06-193">See Also</span></span>  
 [<span data-ttu-id="36b06-194">演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="36b06-194">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [<span data-ttu-id="36b06-195">如何： 访问设计时服务</span><span class="sxs-lookup"><span data-stu-id="36b06-195">How to: Access Design-Time Services</span></span>](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [<span data-ttu-id="36b06-196">如何： 访问 Windows 窗体中的设计时支持</span><span class="sxs-lookup"><span data-stu-id="36b06-196">How to: Access Design-Time Support in Windows Forms</span></span>](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
