---
title: 演练：在 Windows 窗体中承载 3-D WPF 复合控件
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: a35f2b4062edb18914c55046a69dcd9b8825d778
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353850"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="6ff14-102">演练：在 Windows 窗体中承载 3-D WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="6ff14-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="6ff14-103">本演练演示如何使用 @no__t 2 控件创建 @no__t 0 复合控件，并将其托管在 @no__t 1 控件和窗体中。</span><span class="sxs-lookup"><span data-stu-id="6ff14-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="6ff14-104">在本演练中，您将实现一个 @no__t 0 <xref:System.Windows.Controls.UserControl>，其中包含两个子控件。</span><span class="sxs-lookup"><span data-stu-id="6ff14-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="6ff14-105">@No__t-0 将显示一个三维（3-d）圆锥。</span><span class="sxs-lookup"><span data-stu-id="6ff14-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="6ff14-106">与 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 相比，用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 呈示三维对象更容易。</span><span class="sxs-lookup"><span data-stu-id="6ff14-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="6ff14-107">因此，有必要托管一个 @no__t 0 @no__t 类，以便在 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 中创建三维图形。</span><span class="sxs-lookup"><span data-stu-id="6ff14-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="6ff14-108">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="6ff14-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="6ff14-109">创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] @no__t。</span><span class="sxs-lookup"><span data-stu-id="6ff14-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="6ff14-110">正在创建 Windows 窗体主机项目。</span><span class="sxs-lookup"><span data-stu-id="6ff14-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="6ff14-111">承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] @no__t。</span><span class="sxs-lookup"><span data-stu-id="6ff14-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ff14-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="6ff14-112">Prerequisites</span></span>

<span data-ttu-id="6ff14-113">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="6ff14-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="6ff14-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6ff14-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="6ff14-115">创建 UserControl</span><span class="sxs-lookup"><span data-stu-id="6ff14-115">Create the UserControl</span></span>

1. <span data-ttu-id="6ff14-116">创建一个名为 `HostingWpfUserControlInWf` 的**WPF 用户控件库**项目。</span><span class="sxs-lookup"><span data-stu-id="6ff14-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="6ff14-117">在 @no__t 中打开 UserControl1。</span><span class="sxs-lookup"><span data-stu-id="6ff14-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="6ff14-118">将生成的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="6ff14-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="6ff14-119">此代码定义一个 @no__t 0，其中包含两个子控件。</span><span class="sxs-lookup"><span data-stu-id="6ff14-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="6ff14-120">第一个子控件是 @no__t 0 控件;第二个是用于显示三维圆锥的 @no__t 1 控件。</span><span class="sxs-lookup"><span data-stu-id="6ff14-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="6ff14-121">创建主机项目</span><span class="sxs-lookup"><span data-stu-id="6ff14-121">Create the host project</span></span>

1. <span data-ttu-id="6ff14-122">将名为 `WpfUserControlHost` 的**Windows 窗体应用（.NET Framework）** 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="6ff14-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="6ff14-123">在**解决方案资源管理器**中，添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。</span><span class="sxs-lookup"><span data-stu-id="6ff14-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="6ff14-124">添加对以下 @no__t 的程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="6ff14-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="6ff14-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="6ff14-125">PresentationCore</span></span>

    - <span data-ttu-id="6ff14-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="6ff14-126">PresentationFramework</span></span>

    - <span data-ttu-id="6ff14-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="6ff14-127">WindowsBase</span></span>

4. <span data-ttu-id="6ff14-128">添加对 @no__t 项目的引用。</span><span class="sxs-lookup"><span data-stu-id="6ff14-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="6ff14-129">在解决方案资源管理器中，将 @no__t 的项目设置为启动项目。</span><span class="sxs-lookup"><span data-stu-id="6ff14-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="6ff14-130">承载 UserControl</span><span class="sxs-lookup"><span data-stu-id="6ff14-130">Host the UserControl</span></span>

1. <span data-ttu-id="6ff14-131">在 Windows 窗体设计器中，打开 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="6ff14-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="6ff14-132">在属性窗口中，单击 "**事件**"，然后双击 "@no__t" 事件以创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ff14-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="6ff14-133">"代码编辑器" 将打开新生成的 @no__t 0 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ff14-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="6ff14-134">将 Form1.cs 中的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="6ff14-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="6ff14-135">@No__t 0 事件处理程序创建 @no__t 为1的实例，并将内部控件的子控件集合添加 @no__t 到该集合。</span><span class="sxs-lookup"><span data-stu-id="6ff14-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="6ff14-136">将 @no__t 0 控件添加到窗体的子控件集合。</span><span class="sxs-lookup"><span data-stu-id="6ff14-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="6ff14-137">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ff14-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ff14-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ff14-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6ff14-139">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="6ff14-139">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6ff14-140">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="6ff14-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="6ff14-141">演练：在 WPF 中承载 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="6ff14-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="6ff14-142">在 Windows 窗体示例中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="6ff14-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
