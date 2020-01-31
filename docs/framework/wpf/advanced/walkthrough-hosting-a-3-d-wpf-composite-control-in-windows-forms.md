---
title: 在 Windows 窗体中托管 3D WPF 复合控件
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: 07222809d62b207730ddad3c87b8fb60e1602bc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744450"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="8875c-102">演练：在 Windows 窗体中托管 3D WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="8875c-102">Walkthrough: Host a 3D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="8875c-103">本演练演示如何创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 复合控件，并使用 <xref:System.Windows.Forms.Integration.ElementHost> 控件将其承载于 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件和窗体中。</span><span class="sxs-lookup"><span data-stu-id="8875c-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="8875c-104">在本演练中，您将实现一个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>，其中包含两个子控件。</span><span class="sxs-lookup"><span data-stu-id="8875c-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="8875c-105"><xref:System.Windows.Controls.UserControl> 显示三维（3D）圆锥。</span><span class="sxs-lookup"><span data-stu-id="8875c-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3D) cone.</span></span> <span data-ttu-id="8875c-106">与 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]相比，呈现3D 对象更容易 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8875c-106">Rendering 3D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="8875c-107">因此，在 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 类来创建3D 图形是有意义的。</span><span class="sxs-lookup"><span data-stu-id="8875c-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="8875c-108">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8875c-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="8875c-109">创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="8875c-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="8875c-110">正在创建 Windows 窗体主机项目。</span><span class="sxs-lookup"><span data-stu-id="8875c-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="8875c-111">承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="8875c-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8875c-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="8875c-112">Prerequisites</span></span>

<span data-ttu-id="8875c-113">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8875c-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="8875c-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8875c-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="8875c-115">创建 UserControl</span><span class="sxs-lookup"><span data-stu-id="8875c-115">Create the UserControl</span></span>

1. <span data-ttu-id="8875c-116">创建一个名为 `HostingWpfUserControlInWf`的**WPF 用户控件库**项目。</span><span class="sxs-lookup"><span data-stu-id="8875c-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="8875c-117">在 WPF 设计器中打开 UserControl1。</span><span class="sxs-lookup"><span data-stu-id="8875c-117">Open UserControl1.xaml in the WPF Designer.</span></span>

3. <span data-ttu-id="8875c-118">将生成的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="8875c-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="8875c-119">此代码定义一个包含两个子控件的 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="8875c-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="8875c-120">第一个子控件是 <xref:System.Windows.Controls.Label?displayProperty=nameWithType> 控件;第二个是显示三维圆锥的 <xref:System.Windows.Controls.Viewport3D> 控件。</span><span class="sxs-lookup"><span data-stu-id="8875c-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="8875c-121">创建主机项目</span><span class="sxs-lookup"><span data-stu-id="8875c-121">Create the host project</span></span>

1. <span data-ttu-id="8875c-122">将名为 `WpfUserControlHost` 的**Windows 窗体应用（.NET Framework）** 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="8875c-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="8875c-123">在**解决方案资源管理器**中，添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。</span><span class="sxs-lookup"><span data-stu-id="8875c-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="8875c-124">添加对以下 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="8875c-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="8875c-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="8875c-125">PresentationCore</span></span>

    - <span data-ttu-id="8875c-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="8875c-126">PresentationFramework</span></span>

    - <span data-ttu-id="8875c-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="8875c-127">WindowsBase</span></span>

4. <span data-ttu-id="8875c-128">添加对 `HostingWpfUserControlInWf` 项目的引用。</span><span class="sxs-lookup"><span data-stu-id="8875c-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="8875c-129">在解决方案资源管理器中，将 `WpfUserControlHost` 项目设置为启动项目。</span><span class="sxs-lookup"><span data-stu-id="8875c-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="8875c-130">承载 UserControl</span><span class="sxs-lookup"><span data-stu-id="8875c-130">Host the UserControl</span></span>

1. <span data-ttu-id="8875c-131">在 Windows 窗体设计器中，打开 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="8875c-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="8875c-132">在属性窗口中，单击 "**事件**"，然后双击 <xref:System.Windows.Forms.Form.Load> 事件创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="8875c-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="8875c-133">"代码编辑器" 将打开新生成的 `Form1_Load` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="8875c-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="8875c-134">将 Form1.cs 中的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="8875c-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="8875c-135">`Form1_Load` 事件处理程序将创建 `UserControl1` 的实例，并将内部添加到 <xref:System.Windows.Forms.Integration.ElementHost> 控件的子控件集合。</span><span class="sxs-lookup"><span data-stu-id="8875c-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="8875c-136"><xref:System.Windows.Forms.Integration.ElementHost> 控件将添加到窗体的子控件集合。</span><span class="sxs-lookup"><span data-stu-id="8875c-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="8875c-137">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8875c-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="8875c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8875c-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="8875c-139">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="8875c-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="8875c-140">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="8875c-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="8875c-141">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="8875c-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="8875c-142">在 Windows 窗体示例中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="8875c-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
