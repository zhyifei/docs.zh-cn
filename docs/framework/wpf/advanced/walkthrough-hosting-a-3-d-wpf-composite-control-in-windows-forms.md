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
ms.openlocfilehash: 74f82f9be734cb7dc5225dc4226e14c2cee317df
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605521"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="c08eb-102">演练：在 Windows 窗体中承载 3-D WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="c08eb-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="c08eb-103">本演练演示如何创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]复合控件并将其在托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件和窗体使用<xref:System.Windows.Forms.Integration.ElementHost>控件。</span><span class="sxs-lookup"><span data-stu-id="c08eb-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="c08eb-104">在本演练中，您将实现[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> ，其中包含两个子控件。</span><span class="sxs-lookup"><span data-stu-id="c08eb-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="c08eb-105"><xref:System.Windows.Controls.UserControl>显示三维 (3-D) 锥形区域。</span><span class="sxs-lookup"><span data-stu-id="c08eb-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="c08eb-106">呈现三维对象是变得更为简单[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]比使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c08eb-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="c08eb-107">因此，对主机有意义[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl>类，以创建 3d 图形[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c08eb-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="c08eb-108">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="c08eb-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="c08eb-109">创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="c08eb-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="c08eb-110">创建 Windows 窗体宿主项目。</span><span class="sxs-lookup"><span data-stu-id="c08eb-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="c08eb-111">承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="c08eb-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c08eb-112">系统必备</span><span class="sxs-lookup"><span data-stu-id="c08eb-112">Prerequisites</span></span>

<span data-ttu-id="c08eb-113">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="c08eb-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="c08eb-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c08eb-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="c08eb-115">创建用户控件</span><span class="sxs-lookup"><span data-stu-id="c08eb-115">Create the UserControl</span></span>

1. <span data-ttu-id="c08eb-116">创建**WPF 用户控件库**名为项目`HostingWpfUserControlInWf`。</span><span class="sxs-lookup"><span data-stu-id="c08eb-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="c08eb-117">打开 UserControl1.xaml 在[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c08eb-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="c08eb-118">生成的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="c08eb-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="c08eb-119">此代码定义<xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>，其中包含两个子控件。</span><span class="sxs-lookup"><span data-stu-id="c08eb-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="c08eb-120">第一个子控件是<xref:System.Windows.Controls.Label?displayProperty=nameWithType>控制; 第二个是<xref:System.Windows.Controls.Viewport3D>显示三维锥体控件。</span><span class="sxs-lookup"><span data-stu-id="c08eb-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="c08eb-121">创建宿主项目</span><span class="sxs-lookup"><span data-stu-id="c08eb-121">Create the host project</span></span>

1. <span data-ttu-id="c08eb-122">添加**WPF 应用 (.NET Framework)** 名为项目`WpfUserControlHost`到解决方案。</span><span class="sxs-lookup"><span data-stu-id="c08eb-122">Add a **WPF App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="c08eb-123">有关详细信息，请参见[演练：我第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c08eb-123">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="c08eb-124">在中**解决方案资源管理器**，添加对 WindowsFormsIntegration 程序集，它名为 WindowsFormsIntegration.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="c08eb-124">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="c08eb-125">将引用添加到以下[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]程序集：</span><span class="sxs-lookup"><span data-stu-id="c08eb-125">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="c08eb-126">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="c08eb-126">PresentationCore</span></span>

    - <span data-ttu-id="c08eb-127">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="c08eb-127">PresentationFramework</span></span>

    - <span data-ttu-id="c08eb-128">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="c08eb-128">WindowsBase</span></span>

4. <span data-ttu-id="c08eb-129">添加对引用`HostingWpfUserControlInWf`项目。</span><span class="sxs-lookup"><span data-stu-id="c08eb-129">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="c08eb-130">在解决方案资源管理器，设置`WpfUserControlHost`项目为启动项目。</span><span class="sxs-lookup"><span data-stu-id="c08eb-130">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="c08eb-131">托管用户控件</span><span class="sxs-lookup"><span data-stu-id="c08eb-131">Host the UserControl</span></span>

1. <span data-ttu-id="c08eb-132">在 Windows 窗体设计器中打开 Form1。</span><span class="sxs-lookup"><span data-stu-id="c08eb-132">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="c08eb-133">在属性窗口中，单击**事件**，然后双击<xref:System.Windows.Forms.Form.Load>事件创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c08eb-133">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="c08eb-134">在代码编辑器将打开到新生成`Form1_Load`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c08eb-134">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="c08eb-135">Form1.cs 中的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="c08eb-135">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="c08eb-136">`Form1_Load`事件处理程序创建的实例`UserControl1`，并将添加为<xref:System.Windows.Forms.Integration.ElementHost>子控件的控件的集合。</span><span class="sxs-lookup"><span data-stu-id="c08eb-136">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="c08eb-137"><xref:System.Windows.Forms.Integration.ElementHost>控件添加到的子控件的窗体的集合。</span><span class="sxs-lookup"><span data-stu-id="c08eb-137">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="c08eb-138">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c08eb-138">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="c08eb-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="c08eb-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="c08eb-140">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="c08eb-140">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="c08eb-141">演练：承载 WPF 复合控件在 Windows 窗体中</span><span class="sxs-lookup"><span data-stu-id="c08eb-141">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="c08eb-142">演练：承载在 WPF 中的 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="c08eb-142">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="c08eb-143">承载 WPF 复合控件在 Windows 窗体示例</span><span class="sxs-lookup"><span data-stu-id="c08eb-143">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)