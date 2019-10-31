---
title: 演练：在 WPF 中承载 ActiveX 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 8679181d720d9550cf60034a7cf1809b79198e83
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197896"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="28e66-102">演练：在 WPF 中承载 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="28e66-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="28e66-103">若要实现与浏览器的更好交互，可以在基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中使用 Microsoft ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="28e66-103">To enable improved interaction with browsers, you can use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="28e66-104">本演练演示如何将 Microsoft Windows Media Player 作为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上的控件进行承载。</span><span class="sxs-lookup"><span data-stu-id="28e66-104">This walkthrough demonstrates how you can host the Microsoft Windows Media Player as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="28e66-105">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="28e66-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="28e66-106">创建项目。</span><span class="sxs-lookup"><span data-stu-id="28e66-106">Creating the project.</span></span>

- <span data-ttu-id="28e66-107">创建 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="28e66-107">Creating the ActiveX control.</span></span>

- <span data-ttu-id="28e66-108">在 WPF 页上承载 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="28e66-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="28e66-109">完成本演练后，你将了解如何在基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中使用 Microsoft ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="28e66-109">When you have completed this walkthrough, you will understand how to use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28e66-110">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="28e66-110">Prerequisites</span></span>
 <span data-ttu-id="28e66-111">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="28e66-111">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="28e66-112">Microsoft Windows Media Player 安装在安装了 Visual Studio 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="28e66-112">Microsoft Windows Media Player installed on the computer where Visual Studio is installed.</span></span>

- <span data-ttu-id="28e66-113">Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="28e66-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="28e66-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="28e66-114">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="28e66-115">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="28e66-115">To create and set up the project</span></span>

1. <span data-ttu-id="28e66-116">创建一个名为 `HostingAxInWpf`的 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="28e66-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="28e66-117">将 Windows 窗体控件库项目添加到解决方案，并将项目命名为 `WmpAxLib`。</span><span class="sxs-lookup"><span data-stu-id="28e66-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="28e66-118">在 WmpAxLib 项目中，添加对 Windows Media Player 程序集的引用，该程序集名为 wmp .dll。</span><span class="sxs-lookup"><span data-stu-id="28e66-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="28e66-119">打开**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="28e66-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="28e66-120">右键单击 "**工具箱**"，然后单击 "**选择项**"。</span><span class="sxs-lookup"><span data-stu-id="28e66-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="28e66-121">单击 " **COM 组件**" 选项卡，选择**Windows Media Player**控件，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="28e66-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="28e66-122">将 Windows Media Player 控件添加到 "**工具箱**"。</span><span class="sxs-lookup"><span data-stu-id="28e66-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="28e66-123">在解决方案资源管理器中，右键单击**UserControl1**文件，然后单击 "**重命名**"。</span><span class="sxs-lookup"><span data-stu-id="28e66-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="28e66-124">根据语言，将名称更改为 `WmpAxControl.vb` 或 `WmpAxControl.cs`。</span><span class="sxs-lookup"><span data-stu-id="28e66-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="28e66-125">如果系统提示您重命名所有引用，请单击 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="28e66-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="28e66-126">创建 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="28e66-126">Creating the ActiveX Control</span></span>
<span data-ttu-id="28e66-127">当将控件添加到设计图面时，Visual Studio 会自动为 Microsoft ActiveX 控件生成一个 <xref:System.Windows.Forms.AxHost> 包装器类。</span><span class="sxs-lookup"><span data-stu-id="28e66-127">Visual Studio automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a Microsoft ActiveX control when the control is added to a design surface.</span></span> <span data-ttu-id="28e66-128">下面的过程创建一个名为 AxInterop. WMPLib 的托管程序集。</span><span class="sxs-lookup"><span data-stu-id="28e66-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

### <a name="to-create-the-activex-control"></a><span data-ttu-id="28e66-129">创建 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="28e66-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="28e66-130">在 Windows 窗体设计器中打开 WmpAxControl 或 WmpAxControl.cs。</span><span class="sxs-lookup"><span data-stu-id="28e66-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="28e66-131">从 "**工具箱**" 中，将 "Windows Media Player" 控件添加到设计图面。</span><span class="sxs-lookup"><span data-stu-id="28e66-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="28e66-132">在属性窗口中，将 Windows Media Player 控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 "<xref:System.Windows.Forms.DockStyle.Fill>"。</span><span class="sxs-lookup"><span data-stu-id="28e66-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="28e66-133">生成 WmpAxLib 控件库项目。</span><span class="sxs-lookup"><span data-stu-id="28e66-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="28e66-134">在 WPF 页上承载 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="28e66-134">Hosting the ActiveX Control on a WPF Page</span></span>

### <a name="to-host-the-activex-control"></a><span data-ttu-id="28e66-135">承载 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="28e66-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="28e66-136">在 HostingAxInWpf 项目中，添加对生成的 ActiveX 互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="28e66-136">In the HostingAxInWpf project, add a reference to the generated ActiveX interoperability assembly.</span></span>

     <span data-ttu-id="28e66-137">此程序集命名为 AxInterop，并在导入 Windows Media Player 控件时添加到 WmpAxLib 项目的 Debug 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="28e66-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="28e66-138">添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。</span><span class="sxs-lookup"><span data-stu-id="28e66-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="28e66-139">添加对 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 程序集的引用，该程序集名为 System.object。</span><span class="sxs-lookup"><span data-stu-id="28e66-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="28e66-140">在 WPF 设计器中打开 Mainwindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="28e66-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="28e66-141">将 <xref:System.Windows.Controls.Grid> 元素命名为 `grid1`。</span><span class="sxs-lookup"><span data-stu-id="28e66-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="28e66-142">在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 元素。</span><span class="sxs-lookup"><span data-stu-id="28e66-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="28e66-143">在属性窗口中，单击 "**事件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="28e66-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="28e66-144">双击 "<xref:System.Windows.FrameworkElement.Loaded>" 事件。</span><span class="sxs-lookup"><span data-stu-id="28e66-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="28e66-145">插入以下代码来处理 <xref:System.Windows.FrameworkElement.Loaded> 事件。</span><span class="sxs-lookup"><span data-stu-id="28e66-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="28e66-146">此代码将创建 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的实例，并将 `AxWindowsMediaPlayer` 控件的一个实例添加为其子级。</span><span class="sxs-lookup"><span data-stu-id="28e66-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="28e66-147">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="28e66-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e66-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="28e66-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="28e66-149">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="28e66-149">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="28e66-150">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="28e66-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="28e66-151">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="28e66-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
