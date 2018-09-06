---
title: 控件和组件创作疑难解答
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
ms.openlocfilehash: caad6a76b52a970e133425c484602deb8801d252
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43798350"
---
# <a name="troubleshooting-control-and-component-authoring"></a><span data-ttu-id="0ce25-102">控件和组件创作疑难解答</span><span class="sxs-lookup"><span data-stu-id="0ce25-102">Troubleshooting Control and Component Authoring</span></span>
<span data-ttu-id="0ce25-103">本主题列出了开发组件和控件时遇到的常见问题。</span><span class="sxs-lookup"><span data-stu-id="0ce25-103">This topic lists the following common problems that arise when developing components and controls.</span></span> <span data-ttu-id="0ce25-104">有关详细信息，请参阅[使用组件编程](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)。</span><span class="sxs-lookup"><span data-stu-id="0ce25-104">For more information, see [Programming with Components](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
-   <span data-ttu-id="0ce25-105">无法将控件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="0ce25-105">Cannot Add Control to Toolbox</span></span>  
  
-   <span data-ttu-id="0ce25-106">无法调试 Windows 窗体用户控件或组件</span><span class="sxs-lookup"><span data-stu-id="0ce25-106">Cannot Debug the Windows Forms User Control or Component</span></span>  
  
-   <span data-ttu-id="0ce25-107">在继承的控件或组件中引发了两次事件</span><span class="sxs-lookup"><span data-stu-id="0ce25-107">Event Is Raised Twice in Inherited Control or Component</span></span>  
  
-   <span data-ttu-id="0ce25-108">设计时错误：“创建组件‘组件名称’失败”</span><span class="sxs-lookup"><span data-stu-id="0ce25-108">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>  
  
-   <span data-ttu-id="0ce25-109">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="0ce25-109">STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="0ce25-110">组件图标未出现在工具箱中</span><span class="sxs-lookup"><span data-stu-id="0ce25-110">Component Icon Does Not Appear in Toolbox</span></span>  
  
## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="0ce25-111">无法将控件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="0ce25-111">Cannot Add Control to Toolbox</span></span>  
 <span data-ttu-id="0ce25-112">如果要将在另一项目中创建的自定义控件或第三方控件添加到“工具箱”中，必须手动操作。</span><span class="sxs-lookup"><span data-stu-id="0ce25-112">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="0ce25-113">如果当前项目中包含控件或组件，它应自动显示在“工具箱”中。</span><span class="sxs-lookup"><span data-stu-id="0ce25-113">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="0ce25-114">有关详细信息，请参阅[演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce25-114">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
#### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="0ce25-115">将控件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="0ce25-115">To add a control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="0ce25-116">右键单击“工具箱”，并从快捷菜单中选择“选择项”。</span><span class="sxs-lookup"><span data-stu-id="0ce25-116">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>  
  
2.  <span data-ttu-id="0ce25-117">在“选择工具箱项”对话框中，添加组件：</span><span class="sxs-lookup"><span data-stu-id="0ce25-117">In the **Choose Toolbox Items** dialog box, add the component:</span></span>  
  
    -   <span data-ttu-id="0ce25-118">如果要添加 .NET Framework 组件或控件，请单击“.NET Framework 组件”选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ce25-118">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>  
  
         <span data-ttu-id="0ce25-119">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0ce25-119">– or –</span></span>  
  
    -   <span data-ttu-id="0ce25-120">如果要添加 COM 组件或 ActiveX 控件，请单击“COM 组件”选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ce25-120">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>  
  
3.  <span data-ttu-id="0ce25-121">如果对话框中列出了该控件，请务必将它选中，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="0ce25-121">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0ce25-122">该控件即会添加到“工具箱”中。</span><span class="sxs-lookup"><span data-stu-id="0ce25-122">The control is added to the **Toolbox**.</span></span>  
  
4.  <span data-ttu-id="0ce25-123">如果对话框中未列出该控件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ce25-123">If your control is not listed in the dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0ce25-124">单击“浏览”按钮。</span><span class="sxs-lookup"><span data-stu-id="0ce25-124">Click the **Browse** button.</span></span>  
  
    2.  <span data-ttu-id="0ce25-125">浏览到包含 .dll 文件（它包含控件）的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ce25-125">Browse to the folder that contains the .dll file that contains your control.</span></span>  
  
    3.  <span data-ttu-id="0ce25-126">选择 .dll 文件并单击“打开”。</span><span class="sxs-lookup"><span data-stu-id="0ce25-126">Select the .dll file and click **Open**.</span></span>  
  
         <span data-ttu-id="0ce25-127">控件即会出现在对话框中。</span><span class="sxs-lookup"><span data-stu-id="0ce25-127">Your control appears in the dialog box.</span></span>  
  
    4.  <span data-ttu-id="0ce25-128">确认选中该控件，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="0ce25-128">Confirm that your control is selected, and then click **OK**.</span></span>  
  
         <span data-ttu-id="0ce25-129">控件即会添加到“工具箱”中。</span><span class="sxs-lookup"><span data-stu-id="0ce25-129">Your control is added to the **Toolbox**.</span></span>  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="0ce25-130">无法调试 Windows 窗体用户控件或组件</span><span class="sxs-lookup"><span data-stu-id="0ce25-130">Cannot Debug the Windows Forms User Control or Component</span></span>  
 <span data-ttu-id="0ce25-131">如果控件派生自<xref:System.Windows.Forms.UserControl>类，您可以调试使用测试容器及其运行时行为。</span><span class="sxs-lookup"><span data-stu-id="0ce25-131">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="0ce25-132">有关详细信息，请参阅[如何：测试 UserControl 的运行时行为](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce25-132">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="0ce25-133">其他自定义控件和组件不是独立的项目。</span><span class="sxs-lookup"><span data-stu-id="0ce25-133">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="0ce25-134">它们必须由 Windows 窗体项目这样的应用程序承载。</span><span class="sxs-lookup"><span data-stu-id="0ce25-134">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="0ce25-135">若要调试控件或组件，必须将其添加到 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="0ce25-135">To debug a control or component, you must add it to a Windows Forms project.</span></span>  
  
#### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="0ce25-136">调试控件或组件</span><span class="sxs-lookup"><span data-stu-id="0ce25-136">To debug a control or component</span></span>  
  
1.  <span data-ttu-id="0ce25-137">在“生成”菜单中，单击“生成解决方案”来生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="0ce25-137">From the **Build** menu, click **Build Solution** to build your solution.</span></span>  
  
2.  <span data-ttu-id="0ce25-138">在“文件”菜单中，选择“添加”，然后选择“新建项目”，将测试项目添加到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="0ce25-138">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>  
  
3.  <span data-ttu-id="0ce25-139">在“添加新项目”对话框中选择“Windows 应用程序”作为项目类型。</span><span class="sxs-lookup"><span data-stu-id="0ce25-139">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>  
  
4.  <span data-ttu-id="0ce25-140">在“解决方案资源管理器”中，右键单击新项目的“引用”节点。</span><span class="sxs-lookup"><span data-stu-id="0ce25-140">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="0ce25-141">在快捷菜单上单击“添加引用”，为包含控件或组件的项目添加引用。</span><span class="sxs-lookup"><span data-stu-id="0ce25-141">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>  
  
5.  <span data-ttu-id="0ce25-142">在测试项目中创建控件或组件的实例。</span><span class="sxs-lookup"><span data-stu-id="0ce25-142">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="0ce25-143">如果组件在“工具箱”中，则可将其拖动到设计器图面，或者以编程方式创建实例，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="0ce25-143">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     <span data-ttu-id="0ce25-144">现在即可像平常一样调试控件或组件。</span><span class="sxs-lookup"><span data-stu-id="0ce25-144">You can now debug your control or component as usual.</span></span>  
  
 <span data-ttu-id="0ce25-145">有关调试的详细信息，请参阅[在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)和[演练：在设计时调试自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce25-145">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="0ce25-146">在继承的控件或组件中引发了两次事件</span><span class="sxs-lookup"><span data-stu-id="0ce25-146">Event Is Raised Twice in Inherited Control or Component</span></span>  
 <span data-ttu-id="0ce25-147">这可能是由于重复的 `Handles` 子句引起的。</span><span class="sxs-lookup"><span data-stu-id="0ce25-147">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="0ce25-148">有关详细信息，请参阅[有关 Visual Basic 中继承的事件处理程序的疑难解答](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce25-148">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="0ce25-149">设计时错误：“创建组件‘组件名称’失败”</span><span class="sxs-lookup"><span data-stu-id="0ce25-149">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>  
 <span data-ttu-id="0ce25-150">组件或控件必须提供一个不带参数的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="0ce25-150">Your component or control must provide a default constructor with no parameters.</span></span> <span data-ttu-id="0ce25-151">设计环境创建组件或控件的实例时，不会尝试为使用参数的构造函数重载提供任何参数。</span><span class="sxs-lookup"><span data-stu-id="0ce25-151">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>  
  
## <a name="stathreadattribute"></a><span data-ttu-id="0ce25-152">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="0ce25-152">STAThreadAttribute</span></span>  
 <span data-ttu-id="0ce25-153"><xref:System.STAThreadAttribute>通知公共语言运行时 (CLR) Windows 窗体使用单线程单元模型。</span><span class="sxs-lookup"><span data-stu-id="0ce25-153">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="0ce25-154">如果没有对 Windows 窗体应用程序的 `Main` 方法应用此特性，则可能会出现意外的行为。</span><span class="sxs-lookup"><span data-stu-id="0ce25-154">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="0ce25-155">例如，背景图像可能不会显示控件，例如<xref:System.Windows.Forms.ListView>。</span><span class="sxs-lookup"><span data-stu-id="0ce25-155">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="0ce25-156">某些控件也可能需要此属性才能正确地实现自动完成和拖放行为。</span><span class="sxs-lookup"><span data-stu-id="0ce25-156">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="0ce25-157">组件图标未出现在工具箱中</span><span class="sxs-lookup"><span data-stu-id="0ce25-157">Component Icon Does Not Appear in Toolbox</span></span>  
 <span data-ttu-id="0ce25-158">当你使用<xref:System.Drawing.ToolboxBitmapAttribute>将图标与自定义组件相关联，位图将不会出现在工具箱中自动生成的组件。</span><span class="sxs-lookup"><span data-stu-id="0ce25-158">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="0ce25-159">若要查看位图，请使用“选择工具箱项”对话框重载控件。</span><span class="sxs-lookup"><span data-stu-id="0ce25-159">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="0ce25-160">有关详细信息，请参阅[如何：为控件提供工具箱位图](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce25-160">For more information, see [How to: Provide a Toolbox Bitmap for a Control](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce25-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ce25-161">See Also</span></span>  
 [<span data-ttu-id="0ce25-162">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="0ce25-162">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="0ce25-163">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="0ce25-163">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [<span data-ttu-id="0ce25-164">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="0ce25-164">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 [<span data-ttu-id="0ce25-165">演练：设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="0ce25-165">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="0ce25-166">组件创作</span><span class="sxs-lookup"><span data-stu-id="0ce25-166">Component Authoring</span></span>](https://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 [<span data-ttu-id="0ce25-167">设计时开发故障排除</span><span class="sxs-lookup"><span data-stu-id="0ce25-167">Troubleshooting Design-Time Development</span></span>](https://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [<span data-ttu-id="0ce25-168">使用组件编程</span><span class="sxs-lookup"><span data-stu-id="0ce25-168">Programming with Components</span></span>](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)
