---
title: 在 WPF 中承载 ActiveX 控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 4ca40c0f6e62fd413e7f305649c5c01ddc152b2a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794137"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="3f940-102">演练：在 WPF 中承载 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="3f940-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="3f940-103">若要实现与浏览器的更好交互，可以在基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中使用 Microsoft ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="3f940-103">To enable improved interaction with browsers, you can use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="3f940-104">本演练演示如何将 Microsoft Windows Media Player 作为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上的控件进行承载。</span><span class="sxs-lookup"><span data-stu-id="3f940-104">This walkthrough demonstrates how you can host the Microsoft Windows Media Player as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="3f940-105">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="3f940-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="3f940-106">创建项目。</span><span class="sxs-lookup"><span data-stu-id="3f940-106">Creating the project.</span></span>

- <span data-ttu-id="3f940-107">创建 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="3f940-107">Creating the ActiveX control.</span></span>

- <span data-ttu-id="3f940-108">在 WPF 页上承载 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="3f940-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="3f940-109">完成本演练后，你将了解如何在基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中使用 Microsoft ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="3f940-109">When you have completed this walkthrough, you will understand how to use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f940-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="3f940-110">Prerequisites</span></span>
 <span data-ttu-id="3f940-111">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="3f940-111">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="3f940-112">Microsoft Windows Media Player 安装在安装了 Visual Studio 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="3f940-112">Microsoft Windows Media Player installed on the computer where Visual Studio is installed.</span></span>

- <span data-ttu-id="3f940-113">Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="3f940-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="3f940-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="3f940-114">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="3f940-115">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="3f940-115">To create and set up the project</span></span>

1. <span data-ttu-id="3f940-116">创建一个名为 `HostingAxInWpf`的 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="3f940-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="3f940-117">将 Windows 窗体控件库项目添加到解决方案，并将项目命名为 `WmpAxLib`。</span><span class="sxs-lookup"><span data-stu-id="3f940-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="3f940-118">在 WmpAxLib 项目中，添加对 Windows Media Player 程序集的引用，该程序集名为 wmp .dll。</span><span class="sxs-lookup"><span data-stu-id="3f940-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="3f940-119">打开**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="3f940-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="3f940-120">右键单击 "**工具箱**"，然后单击 "**选择项**"。</span><span class="sxs-lookup"><span data-stu-id="3f940-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="3f940-121">单击 " **COM 组件**" 选项卡，选择**Windows Media Player**控件，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="3f940-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="3f940-122">将 Windows Media Player 控件添加到 "**工具箱**"。</span><span class="sxs-lookup"><span data-stu-id="3f940-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="3f940-123">在解决方案资源管理器中，右键单击**UserControl1**文件，然后单击 "**重命名**"。</span><span class="sxs-lookup"><span data-stu-id="3f940-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="3f940-124">根据语言，将名称更改为 `WmpAxControl.vb` 或 `WmpAxControl.cs`。</span><span class="sxs-lookup"><span data-stu-id="3f940-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="3f940-125">如果系统提示您重命名所有引用，请单击 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="3f940-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="3f940-126">创建 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="3f940-126">Creating the ActiveX Control</span></span>
<span data-ttu-id="3f940-127">当将控件添加到设计图面时，Visual Studio 会自动为 Microsoft ActiveX 控件生成一个 <xref:System.Windows.Forms.AxHost> 包装器类。</span><span class="sxs-lookup"><span data-stu-id="3f940-127">Visual Studio automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a Microsoft ActiveX control when the control is added to a design surface.</span></span> <span data-ttu-id="3f940-128">下面的过程创建一个名为 AxInterop. WMPLib 的托管程序集。</span><span class="sxs-lookup"><span data-stu-id="3f940-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

### <a name="to-create-the-activex-control"></a><span data-ttu-id="3f940-129">创建 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="3f940-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="3f940-130">在 Windows 窗体设计器中打开 WmpAxControl 或 WmpAxControl.cs。</span><span class="sxs-lookup"><span data-stu-id="3f940-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="3f940-131">从 "**工具箱**" 中，将 "Windows Media Player" 控件添加到设计图面。</span><span class="sxs-lookup"><span data-stu-id="3f940-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="3f940-132">在属性窗口中，将 Windows Media Player 控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 "<xref:System.Windows.Forms.DockStyle.Fill>"。</span><span class="sxs-lookup"><span data-stu-id="3f940-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="3f940-133">生成 WmpAxLib 控件库项目。</span><span class="sxs-lookup"><span data-stu-id="3f940-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="3f940-134">在 WPF 页上承载 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="3f940-134">Hosting the ActiveX Control on a WPF Page</span></span>

### <a name="to-host-the-activex-control"></a><span data-ttu-id="3f940-135">承载 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="3f940-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="3f940-136">在 HostingAxInWpf 项目中，添加对生成的 ActiveX 互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="3f940-136">In the HostingAxInWpf project, add a reference to the generated ActiveX interoperability assembly.</span></span>

     <span data-ttu-id="3f940-137">此程序集命名为 AxInterop，并在导入 Windows Media Player 控件时添加到 WmpAxLib 项目的 Debug 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3f940-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="3f940-138">添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。</span><span class="sxs-lookup"><span data-stu-id="3f940-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="3f940-139">添加对 Windows 窗体程序集的引用，该程序集名为 System.object。</span><span class="sxs-lookup"><span data-stu-id="3f940-139">Add a reference to the Windows Forms assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="3f940-140">在 WPF 设计器中打开 Mainwindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="3f940-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="3f940-141">将 <xref:System.Windows.Controls.Grid> 元素命名为 `grid1`。</span><span class="sxs-lookup"><span data-stu-id="3f940-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="3f940-142">在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 元素。</span><span class="sxs-lookup"><span data-stu-id="3f940-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="3f940-143">在属性窗口中，单击 "**事件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3f940-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="3f940-144">双击 "<xref:System.Windows.FrameworkElement.Loaded>" 事件。</span><span class="sxs-lookup"><span data-stu-id="3f940-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="3f940-145">插入以下代码来处理 <xref:System.Windows.FrameworkElement.Loaded> 事件。</span><span class="sxs-lookup"><span data-stu-id="3f940-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="3f940-146">此代码将创建 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的实例，并将 `AxWindowsMediaPlayer` 控件的一个实例添加为其子级。</span><span class="sxs-lookup"><span data-stu-id="3f940-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="3f940-147">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f940-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f940-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f940-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="3f940-149">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="3f940-149">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="3f940-150">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="3f940-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="3f940-151">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="3f940-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
