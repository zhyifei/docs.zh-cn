---
title: 演练：在 WPF 中承载 Windows 窗体复合控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 5868ee8c5b781d5af75349a5950f7e1e1680d74d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548907"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="fb9f4-102">演练：在 WPF 中承载 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="fb9f4-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="fb9f4-103"> 提供了用于创建应用程序的丰富环境。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-103"> provides a rich environment for creating applications.</span></span> <span data-ttu-id="fb9f4-104">但是，当你有大量的投资[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]它可以更有效地至少重用的代码中，在该代码的一部分你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序而不是从头开始重新编写。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="fb9f4-105">你有现有的 Windows 窗体控件时最常见的方案。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="fb9f4-106">在某些情况下，你甚至可能无法使用这些控件的源代码。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="fb9f4-107"> 提供一个简单的过程，此类中的控件承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-107"> provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="fb9f4-108">例如，你可以使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]大部分你编程，同时承载专用<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="fb9f4-109">本演练将指导你逐步承载 Windows 窗体复合控件来执行中的数据输入的应用程序[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="fb9f4-110">复合控件打包在一个 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="fb9f4-111">此常规步骤可扩展到更复杂的应用程序和控件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="fb9f4-112">本演练可在外观和功能几乎完全相同[演练： 承载 Windows 窗体中的 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="fb9f4-113">主要区别在于承载方案是相反的。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="fb9f4-114">本演练分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="fb9f4-115">第一个部分简要介绍 Windows 窗体复合控件的实现。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="fb9f4-116">第二个部分详细讨论如何托管中的复合控件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序，从该控件，接收事件，以及访问某些控件的属性。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="fb9f4-117">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-117">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="fb9f4-118">实现 Windows 窗体复合控件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-118">Implementing the Windows Forms composite control.</span></span>  
  
-   <span data-ttu-id="fb9f4-119">实现 WPF 主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="fb9f4-120">本演练的任务的完整代码清单，请参阅[承载 Windows 窗体复合控件在 WPF 示例](http://go.microsoft.com/fwlink/?LinkID=159999)。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fb9f4-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="fb9f4-121">Prerequisites</span></span>  
 <span data-ttu-id="fb9f4-122">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="fb9f4-123">。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-123">.</span></span>  
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="fb9f4-124">实现 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="fb9f4-124">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="fb9f4-125">在此示例中使用的 Windows 窗体复合控件是一个简单的数据输入窗体。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-125">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="fb9f4-126">此窗体需要用户名和地址，然后使用自定义事件将该信息返回到主机。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-126">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="fb9f4-127">下图显示呈现的控件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-127">The following illustration shows the rendered control.</span></span>  
  
 <span data-ttu-id="fb9f4-128">![简单的 Windows 窗体控件](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")</span><span class="sxs-lookup"><span data-stu-id="fb9f4-128">![Simple Windows Forms control](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")</span></span>  
<span data-ttu-id="fb9f4-129">Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="fb9f4-129">Windows Forms composite control</span></span>  
  
### <a name="creating-the-project"></a><span data-ttu-id="fb9f4-130">创建项目</span><span class="sxs-lookup"><span data-stu-id="fb9f4-130">Creating the Project</span></span>  
 <span data-ttu-id="fb9f4-131">启动项目：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-131">To start the project:</span></span>  
  
1.  <span data-ttu-id="fb9f4-132">启动[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]，并打开**新项目**对话框。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-132">Launch [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="fb9f4-133">在窗口类别中，选择**Windows 窗体控件库**模板。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-133">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3.  <span data-ttu-id="fb9f4-134">将新项目命名为 `MyControls`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-134">Name the new project `MyControls`.</span></span>  
  
4.  <span data-ttu-id="fb9f4-135">对于位置，指定将方便地命名的顶级文件夹，如`WpfHostingWindowsFormsControl`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-135">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="fb9f4-136">随后，将主机应用程序放在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-136">Later, you will put the host application in this folder.</span></span>  
  
5.  <span data-ttu-id="fb9f4-137">单击“确定”，创建项目。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-137">Click **OK** to create the project.</span></span> <span data-ttu-id="fb9f4-138">默认项目包含一个名为的单个控件`UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-138">The default project contains a single control named `UserControl1`.</span></span>  
  
6.  <span data-ttu-id="fb9f4-139">在解决方案资源管理器，重命名`UserControl1`到`MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-139">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="fb9f4-140">项目应具有对以下系统 DLL 的引用。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-140">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="fb9f4-141">如果默认不包含其中任何 DLL，则将它们添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-141">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
-   <span data-ttu-id="fb9f4-142">系统</span><span class="sxs-lookup"><span data-stu-id="fb9f4-142">System</span></span>  
  
-   <span data-ttu-id="fb9f4-143">System.Data</span><span class="sxs-lookup"><span data-stu-id="fb9f4-143">System.Data</span></span>  
  
-   <span data-ttu-id="fb9f4-144">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="fb9f4-144">System.Drawing</span></span>  
  
-   <span data-ttu-id="fb9f4-145">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="fb9f4-145">System.Windows.Forms</span></span>  
  
-   <span data-ttu-id="fb9f4-146">System.Xml</span><span class="sxs-lookup"><span data-stu-id="fb9f4-146">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="fb9f4-147">将控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="fb9f4-147">Adding Controls to the Form</span></span>  
 <span data-ttu-id="fb9f4-148">向窗体添加控件：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-148">To add controls to the form:</span></span>  
  
-   <span data-ttu-id="fb9f4-149">打开`MyControl1`设计器中。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-149">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="fb9f4-150">添加五个<xref:System.Windows.Forms.Label>控件和及其相应<xref:System.Windows.Forms.TextBox>控件、 大小和与上图中，在窗体上排列。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-150">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="fb9f4-151">在示例中，<xref:System.Windows.Forms.TextBox>控件命名为：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-151">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 <span data-ttu-id="fb9f4-152">添加两个<xref:System.Windows.Forms.Button>进行标记的控件**确定**和**取消**。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-152">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="fb9f4-153">在本示例中，按钮名称就是`btnOK`和`btnCancel`分别。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-153">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="fb9f4-154">实现支持代码</span><span class="sxs-lookup"><span data-stu-id="fb9f4-154">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="fb9f4-155">在代码视图中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-155">Open the form in code view.</span></span> <span data-ttu-id="fb9f4-156">控件通过引发自定义，将收集的数据返回其主机`OnButtonClick`事件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-156">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="fb9f4-157">数据包含在事件自变量对象中。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-157">The data is contained in the event argument object.</span></span> <span data-ttu-id="fb9f4-158">以下代码演示事件和委托声明。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-158">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="fb9f4-159">向 `MyControl1` 类添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-159">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 <span data-ttu-id="fb9f4-160">`MyControlEventArgs`类包含要返回到主机的信息。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-160">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>  
  
 <span data-ttu-id="fb9f4-161">将以下类添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-161">Add the following class to the form.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 <span data-ttu-id="fb9f4-162">当用户单击**确定**或**取消**按钮，<xref:System.Windows.Forms.Control.Click>事件处理程序创建`MyControlEventArgs`包含数据的对象，并引发`OnButtonClick`事件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-162">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="fb9f4-163">两个处理程序之间的唯一区别是事件自变量的`IsOK`属性。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-163">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="fb9f4-164">此属性使主机可以确定单击的按钮。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-164">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="fb9f4-165">设置为`true`为**确定**按钮，和`false`为**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-165">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="fb9f4-166">以下代码演示两个按钮处理程序。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-166">The following code shows the two button handlers.</span></span>  
  
 <span data-ttu-id="fb9f4-167">向 `MyControl1` 类添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-167">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="fb9f4-168">赋予程序集强名称并生成程序集</span><span class="sxs-lookup"><span data-stu-id="fb9f4-168">Giving the Assembly a Strong Name and Building the Assembly</span></span>  
 <span data-ttu-id="fb9f4-169">此程序集引用的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序中，它必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-169">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="fb9f4-170">若要创建强名称，请使用 Sn.exe 创建密钥文件，并将其添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-170">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>  
  
1.  <span data-ttu-id="fb9f4-171">打开一个 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-171">Open a [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] command prompt.</span></span> <span data-ttu-id="fb9f4-172">若要执行此操作，请单击**启动**菜单，然后再选择**所有 Programs/Microsoft Visual Studio 2010/Visual Studio 工具/Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-172">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="fb9f4-173">这将启动包含自定义环境变量的控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-173">This launches a console window with customized environment variables.</span></span>  
  
2.  <span data-ttu-id="fb9f4-174">在命令提示符下，使用`cd`命令可以转到你的项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-174">At the command prompt, use the `cd` command to go to your project folder.</span></span>  
  
3.  <span data-ttu-id="fb9f4-175">通过运行以下命令生成名为 MyControls.snk 的密钥文件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-175">Generate a key file named MyControls.snk by running the following command.</span></span>  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  <span data-ttu-id="fb9f4-176">若要在你的项目中包含的密钥文件，右键单击解决方案资源管理器中的项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-176">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="fb9f4-177">在项目设计器中，单击**签名**选项卡上，选择**对程序集签名**复选框，然后浏览到你的密钥文件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-177">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>  
  
5.  <span data-ttu-id="fb9f4-178">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-178">Build the solution.</span></span> <span data-ttu-id="fb9f4-179">生成将产生一个名为 MyControls.dll 的 DLL。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-179">The build will produce a DLL named MyControls.dll.</span></span>  
  
## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="fb9f4-180">实现 WPF 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="fb9f4-180">Implementing the WPF Host Application</span></span>  
 <span data-ttu-id="fb9f4-181">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]宿主应用程序使用<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件来承载`MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-181">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="fb9f4-182">该应用程序处理`OnButtonClick`事件，以接收来自控件的数据。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-182">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="fb9f4-183">它还具有的选项按钮，您可以更改某些控件的属性的集合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-183">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="fb9f4-184">下图显示已完成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-184">The following illustration shows the finished application.</span></span>  
  
 <span data-ttu-id="fb9f4-185">![控件嵌入在 WPF 页中](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")</span><span class="sxs-lookup"><span data-stu-id="fb9f4-185">![A control embedded in a WPF page](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")</span></span>  
<span data-ttu-id="fb9f4-186">显示嵌入在 WPF 应用程序中的控件的完整应用程序</span><span class="sxs-lookup"><span data-stu-id="fb9f4-186">The complete application, showing the control embedded in the WPF application</span></span>  
  
### <a name="creating-the-project"></a><span data-ttu-id="fb9f4-187">创建项目</span><span class="sxs-lookup"><span data-stu-id="fb9f4-187">Creating the Project</span></span>  
 <span data-ttu-id="fb9f4-188">启动项目：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-188">To start the project:</span></span>  
  
1.  <span data-ttu-id="fb9f4-189">打开[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]，然后选择**新项目**。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-189">Open [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], and select **New Project**.</span></span>  
  
2.  <span data-ttu-id="fb9f4-190">在窗口类别中，选择**WPF 应用程序**模板。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-190">In the Window category, select the **WPF Application** template.</span></span>
  
3.  <span data-ttu-id="fb9f4-191">将新项目命名为 `WpfHost`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-191">Name the new project `WpfHost`.</span></span>  
  
4.  <span data-ttu-id="fb9f4-192">对于位置，指定包含 MyControls 项目的同一顶层文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-192">For the location, specify the same top-level folder that contains the MyControls project.</span></span>  
  
5.  <span data-ttu-id="fb9f4-193">单击“确定”，创建项目。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-193">Click **OK** to create the project.</span></span>  
  
 <span data-ttu-id="fb9f4-194">你还需要将引用添加到包含 DLL`MyControl1`和其他程序集。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-194">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>  
  
1.  <span data-ttu-id="fb9f4-195">右键单击解决方案资源管理器中的项目名称并选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-195">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="fb9f4-196">单击**浏览**选项卡，然后浏览到包含 MyControls.dll 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-196">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="fb9f4-197">在本演练中，此文件夹位于 MyControls\bin\Debug。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-197">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="fb9f4-198">选择 MyControls.dll，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-198">Select MyControls.dll, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="fb9f4-199">添加到名为 WindowsFormsIntegration.dll 的 WindowsFormsIntegration 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-199">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
### <a name="implementing-the-basic-layout"></a><span data-ttu-id="fb9f4-200">实现基本布局</span><span class="sxs-lookup"><span data-stu-id="fb9f4-200">Implementing the Basic Layout</span></span>  
 <span data-ttu-id="fb9f4-201">[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] MainWindow.xaml 的主机应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-201">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="fb9f4-202">此文件包含[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]标记，定义布局，并承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-202">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="fb9f4-203">该应用程序分为三个区域：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-203">The application is divided into three regions:</span></span>  
  
-   <span data-ttu-id="fb9f4-204">**控件属性**面板中，其中包含一套可用于修改所承载控件的各种属性的选项按钮。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-204">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>  
  
-   <span data-ttu-id="fb9f4-205">**数据从控件**面板中，其中包含几个<xref:System.Windows.Controls.TextBlock>显示数据的元素返回从所承载的控件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-205">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>  
  
-   <span data-ttu-id="fb9f4-206">所承载控件本身。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-206">The hosted control itself.</span></span>  
  
 <span data-ttu-id="fb9f4-207">基本布局如下面的 XAML 中所示。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-207">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="fb9f4-208">需要的标记到主机`MyControl1`省略在此示例中，但稍后将作介绍。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-208">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>  
  
 <span data-ttu-id="fb9f4-209">将 MainWindow.xaml 中的 XAML 替换为以下内容。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-209">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="fb9f4-210">如果你使用的 Visual Basic，更改到类`x:Class="MainWindow"`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-210">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>  
  
 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 <span data-ttu-id="fb9f4-211">第一个<xref:System.Windows.Controls.StackPanel>元素包含多个的集<xref:System.Windows.Controls.RadioButton>使你能够修改各种托管控件的默认属性的控件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-211">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="fb9f4-212">后跟<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素，哪些主机`MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-212">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="fb9f4-213">最后一个<xref:System.Windows.Controls.StackPanel>元素包含若干<xref:System.Windows.Controls.TextBlock>显示由托管控件的数据的元素。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-213">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="fb9f4-214">元素的顺序和<xref:System.Windows.Controls.DockPanel.Dock%2A>和<xref:System.Windows.FrameworkElement.Height%2A>特性设置没有缺口或扭曲的嵌入到窗口托管的控件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-214">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>  
  
#### <a name="hosting-the-control"></a><span data-ttu-id="fb9f4-215">承载控件</span><span class="sxs-lookup"><span data-stu-id="fb9f4-215">Hosting the Control</span></span>  
 <span data-ttu-id="fb9f4-216">上面的 XAML 的以下编辑的版本侧重于所需的元素到主机`MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-216">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>  
  
 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 <span data-ttu-id="fb9f4-217">`xmlns`命名空间映射特性创建的引用`MyControls`包含托管的控件的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-217">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="fb9f4-218">此映射可用于表示`MyControl1`中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]作为`<mcl:MyControl1>`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-218">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>  
  
 <span data-ttu-id="fb9f4-219">XAML 中的两个元素处理承载：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-219">Two elements in the XAML handle the hosting:</span></span>  
  
-   <span data-ttu-id="fb9f4-220">`WindowsFormsHost` 表示<xref:System.Windows.Forms.Integration.WindowsFormsHost>让您可以承载 Windows 窗体控件中的元素[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-220">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  
  
-   <span data-ttu-id="fb9f4-221">`mcl:MyControl1`它表示`MyControl1`，添加到<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的子集合。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-221">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="fb9f4-222">因此，此 Windows 窗体控件呈现为属于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]窗口中，并且你可以与该控件从应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-222">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>  
  
### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="fb9f4-223">实现代码隐藏文件</span><span class="sxs-lookup"><span data-stu-id="fb9f4-223">Implementing the Code-Behind File</span></span>  
 <span data-ttu-id="fb9f4-224">代码隐藏文件，MainWindow.xaml.vb 或 MainWindow.xaml.cs，包含实现的功能与过程性代码[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]前面部分所述。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-224">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="fb9f4-225">主要任务有：</span><span class="sxs-lookup"><span data-stu-id="fb9f4-225">The primary tasks are:</span></span>  
  
-   <span data-ttu-id="fb9f4-226">附加到事件处理程序`MyControl1`的`OnButtonClick`事件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-226">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>  
  
-   <span data-ttu-id="fb9f4-227">修改的各种属性`MyControl1`，将根据如何设置的选项按钮的集合。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-227">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>  
  
-   <span data-ttu-id="fb9f4-228">显示控件收集的数据。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-228">Displaying the data collected by the control.</span></span>  
  
#### <a name="initializing-the-application"></a><span data-ttu-id="fb9f4-229">初始化应用程序</span><span class="sxs-lookup"><span data-stu-id="fb9f4-229">Initializing the Application</span></span>  
 <span data-ttu-id="fb9f4-230">中的事件处理程序窗口的包含初始化代码<xref:System.Windows.FrameworkElement.Loaded>事件，并将事件处理程序附加到控件的`OnButtonClick`事件。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-230">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>  
  
 <span data-ttu-id="fb9f4-231">在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，添加以下代码到`MainWindow`类。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-231">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 <span data-ttu-id="fb9f4-232">因为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]讨论以前添加`MyControl1`到<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的子元素集合，可以强制转换<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的<xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A>获取对引用`MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-232">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="fb9f4-233">然后可以使用该引用附加到事件处理程序`OnButtonClick`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-233">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>  
  
 <span data-ttu-id="fb9f4-234">除了提供对控件本身的引用<xref:System.Windows.Forms.Integration.WindowsFormsHost>公开多个控件的属性，可以从应用程序操作。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-234">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="fb9f4-235">初始化代码将这些值分配给私有全局变量，以供稍后在应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-235">The initialization code assigns those values to private global variables for later use in the application.</span></span>  
  
 <span data-ttu-id="fb9f4-236">以便你可以轻松地访问中的类型`MyControls`DLL，添加以下`Imports`或`using`到文件顶部的语句。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-236">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="fb9f4-237">处理 OnButtonClick 事件</span><span class="sxs-lookup"><span data-stu-id="fb9f4-237">Handling the OnButtonClick Event</span></span>  
 <span data-ttu-id="fb9f4-238">`MyControl1` 引发`OnButtonClick`事件在用户单击控件的按钮之一时。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-238">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>  
  
 <span data-ttu-id="fb9f4-239">向 `MainWindow` 类添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-239">Add the following code to the `MainWindow` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 <span data-ttu-id="fb9f4-240">中的文本框中的数据打包到`MyControlEventArgs`对象。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-240">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="fb9f4-241">如果用户单击**确定**按钮，事件处理程序中提取数据并在下方的面板中显示它`MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-241">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>  
  
#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="fb9f4-242">修改控件属性</span><span class="sxs-lookup"><span data-stu-id="fb9f4-242">Modifying the Control’s Properties</span></span>  
 <span data-ttu-id="fb9f4-243"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素公开多个托管的控件的默认属性。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-243">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="fb9f4-244">因此，可以更改空间外观，以更贴合应用程序的样式。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-244">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="fb9f4-245">位于左侧面板中的选项按钮组使用户能够修改多个颜色和字体属性。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-245">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="fb9f4-246">按钮的每个集具有的处理程序<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件，也不能检测到用户的选项按钮选择更改在控件上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-246">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>  
  
 <span data-ttu-id="fb9f4-247">向 `MainWindow` 类添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-247">Add the following code to the `MainWindow` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="fb9f4-248">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-248">Build and run the application.</span></span> <span data-ttu-id="fb9f4-249">Windows 窗体复合控件中添加一些文本，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-249">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="fb9f4-250">文本将显示在标签中。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-250">The text appears in the labels.</span></span> <span data-ttu-id="fb9f4-251">单击不同的单选按钮查看在控件上的效果。</span><span class="sxs-lookup"><span data-stu-id="fb9f4-251">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb9f4-252">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb9f4-252">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="fb9f4-253">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="fb9f4-253">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="fb9f4-254">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="fb9f4-254">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="fb9f4-255">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="fb9f4-255">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
