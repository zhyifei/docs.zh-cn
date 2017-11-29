---
title: "演练：在 Windows 窗体中承载 3-D WPF 复合控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c5af705509d30f7dfd50ade0c07aca242deff4dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="d3eee-102">演练：在 Windows 窗体中承载 3-D WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="d3eee-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>
<span data-ttu-id="d3eee-103">本演练演示如何创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]复合控件并将其在托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件和窗体使用<xref:System.Windows.Forms.Integration.ElementHost>控件。</span><span class="sxs-lookup"><span data-stu-id="d3eee-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
 <span data-ttu-id="d3eee-104">在本演练中，你将实施[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> ，其中包含两个子控件。</span><span class="sxs-lookup"><span data-stu-id="d3eee-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="d3eee-105"><xref:System.Windows.Controls.UserControl>显示三维 (3-D) 圆锥。</span><span class="sxs-lookup"><span data-stu-id="d3eee-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="d3eee-106">呈现三维对象就可以很容易与[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]比使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3eee-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="d3eee-107">因此，对主机的意义上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl>类，以创建中的 3d 图形[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3eee-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
 <span data-ttu-id="d3eee-108">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="d3eee-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="d3eee-109">创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="d3eee-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>  
  
-   <span data-ttu-id="d3eee-110">创建 Windows 窗体主机项目。</span><span class="sxs-lookup"><span data-stu-id="d3eee-110">Creating the Windows Forms host project.</span></span>  
  
-   <span data-ttu-id="d3eee-111">承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="d3eee-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>  
  
 <span data-ttu-id="d3eee-112">本演练的任务的完整代码清单，请参阅[承载 Windows 窗体示例中的三维 WPF 复合控件](http://go.microsoft.com/fwlink/?LinkID=160001)。</span><span class="sxs-lookup"><span data-stu-id="d3eee-112">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a 3-D WPF Composite Control in Windows Forms Sample](http://go.microsoft.com/fwlink/?LinkID=160001).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3eee-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="d3eee-113">Prerequisites</span></span>  
 <span data-ttu-id="d3eee-114">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="d3eee-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="d3eee-115">。</span><span class="sxs-lookup"><span data-stu-id="d3eee-115">.</span></span>  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a><span data-ttu-id="d3eee-116">创建用户控件</span><span class="sxs-lookup"><span data-stu-id="d3eee-116">Creating the UserControl</span></span>  
  
#### <a name="to-create-the-usercontrol"></a><span data-ttu-id="d3eee-117">若要创建用户控件</span><span class="sxs-lookup"><span data-stu-id="d3eee-117">To create the UserControl</span></span>  
  
1.  <span data-ttu-id="d3eee-118">创建一个名为的 WPF 用户控件库项目`HostingWpfUserControlInWf`。</span><span class="sxs-lookup"><span data-stu-id="d3eee-118">Create a WPF User Control Library project named `HostingWpfUserControlInWf`.</span></span>  
  
2.  <span data-ttu-id="d3eee-119">打开 UserControl1.xaml 在[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3eee-119">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
3.  <span data-ttu-id="d3eee-120">生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="d3eee-120">Replace the generated code with the following code.</span></span>  
  
     <span data-ttu-id="d3eee-121">此代码定义<xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>，其中包含两个子控件。</span><span class="sxs-lookup"><span data-stu-id="d3eee-121">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="d3eee-122">第一个子控件是<xref:System.Windows.Controls.Label?displayProperty=nameWithType>控件; 第二个是<xref:System.Windows.Controls.Viewport3D>显示三维锥体的控件。</span><span class="sxs-lookup"><span data-stu-id="d3eee-122">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="d3eee-123">创建 Windows 窗体宿主项目</span><span class="sxs-lookup"><span data-stu-id="d3eee-123">Creating the Windows Forms Host Project</span></span>  
  
#### <a name="to-create-the-host-project"></a><span data-ttu-id="d3eee-124">创建宿主项目</span><span class="sxs-lookup"><span data-stu-id="d3eee-124">To create the host project</span></span>  
  
1.  <span data-ttu-id="d3eee-125">添加一个名为的 Windows 应用程序项目`WpfUserControlHost`到解决方案。</span><span class="sxs-lookup"><span data-stu-id="d3eee-125">Add a Windows application project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="d3eee-126">有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。</span><span class="sxs-lookup"><span data-stu-id="d3eee-126">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="d3eee-127">在解决方案资源管理器，将添加到名为 WindowsFormsIntegration.dll 的 WindowsFormsIntegration 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d3eee-127">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="d3eee-128">将引用添加到以下[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]程序集：</span><span class="sxs-lookup"><span data-stu-id="d3eee-128">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>  
  
    -   <span data-ttu-id="d3eee-129">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="d3eee-129">PresentationCore</span></span>  
  
    -   <span data-ttu-id="d3eee-130">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="d3eee-130">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="d3eee-131">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="d3eee-131">WindowsBase</span></span>  
  
4.  <span data-ttu-id="d3eee-132">添加对的引用`HostingWpfUserControlInWf`项目。</span><span class="sxs-lookup"><span data-stu-id="d3eee-132">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>  
  
5.  <span data-ttu-id="d3eee-133">在解决方案资源管理器，设置`WpfUserControlHost`项目为启动项目。</span><span class="sxs-lookup"><span data-stu-id="d3eee-133">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a><span data-ttu-id="d3eee-134">承载 Windows Presentation Foundation UserControl</span><span class="sxs-lookup"><span data-stu-id="d3eee-134">Hosting the Windows Presentation Foundation UserControl</span></span>  
  
#### <a name="to-host-the-usercontrol"></a><span data-ttu-id="d3eee-135">若要托管的 UserControl</span><span class="sxs-lookup"><span data-stu-id="d3eee-135">To host the UserControl</span></span>  
  
1.  <span data-ttu-id="d3eee-136">在 Windows 窗体设计器中，打开 form1。</span><span class="sxs-lookup"><span data-stu-id="d3eee-136">In the Windows Forms Designer, open Form1.</span></span>  
  
2.  <span data-ttu-id="d3eee-137">在属性窗口中，单击**事件**，然后双击<xref:System.Windows.Forms.Form.Load>事件创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d3eee-137">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>  
  
     <span data-ttu-id="d3eee-138">代码编辑器随即打开到新生成`Form1_Load`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d3eee-138">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>  
  
3.  <span data-ttu-id="d3eee-139">Form1.cs 中的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="d3eee-139">Replace the code in Form1.cs with the following code.</span></span>  
  
     <span data-ttu-id="d3eee-140">`Form1_Load`事件处理程序创建的实例`UserControl1`，并将它添加<xref:System.Windows.Forms.Integration.ElementHost>的子控件的控件的集合。</span><span class="sxs-lookup"><span data-stu-id="d3eee-140">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="d3eee-141"><xref:System.Windows.Forms.Integration.ElementHost>控件添加到的子控件的窗体的集合。</span><span class="sxs-lookup"><span data-stu-id="d3eee-141">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="d3eee-142">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3eee-142">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3eee-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3eee-143">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="d3eee-144">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="d3eee-144">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="d3eee-145">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="d3eee-145">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="d3eee-146">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="d3eee-146">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="d3eee-147">承载 Windows 窗体示例中的 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="d3eee-147">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160001)
