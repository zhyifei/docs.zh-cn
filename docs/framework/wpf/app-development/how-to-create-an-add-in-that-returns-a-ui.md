---
title: "如何：创建返回 UI 的外接程序"
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
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd6956f1934f8594a941b57066cc2d4d6214a9a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="b769e-102">如何：创建返回 UI 的外接程序</span><span class="sxs-lookup"><span data-stu-id="b769e-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="b769e-103">此示例演示如何创建返回的外接程序[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)][!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]到主机[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]独立的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b769e-103">This example shows how to create an add-in that returns a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)][!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to a host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application.</span></span>  
  
 <span data-ttu-id="b769e-104">外接程序返回[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]即[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]用户控件。</span><span class="sxs-lookup"><span data-stu-id="b769e-104">The add-in returns a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that is a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] user control.</span></span> <span data-ttu-id="b769e-105">用户控件的内容是单个按钮，单击时会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="b769e-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="b769e-106">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]独立的应用程序承载外接程序，并将用户控件 （由外接程序返回） 显示为应用程序主窗口的内容。</span><span class="sxs-lookup"><span data-stu-id="b769e-106">The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="b769e-107">**系统必备**</span><span class="sxs-lookup"><span data-stu-id="b769e-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="b769e-108">此示例重点介绍[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]扩展[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，启用此方案中，假设您具备以下：</span><span class="sxs-lookup"><span data-stu-id="b769e-108">This example highlights the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model that enable this scenario, and assumes the following:</span></span>  
  
-   <span data-ttu-id="b769e-109">知识[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，包括管道、 外接程序和主机开发。</span><span class="sxs-lookup"><span data-stu-id="b769e-109">Knowledge of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="b769e-110">如果你不熟悉这些概念，请参阅[外接程序和扩展性](../../../../docs/framework/add-ins/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b769e-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](../../../../docs/framework/add-ins/index.md).</span></span> <span data-ttu-id="b769e-111">有关演示如何实现管道、 外接程序和主机应用程序的教程，请参阅[演练： 创建可扩展应用程序](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)。</span><span class="sxs-lookup"><span data-stu-id="b769e-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
-   <span data-ttu-id="b769e-112">知识[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]扩展[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，这可在此处找到： [WPF 外接程序概述](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b769e-112">Knowledge of the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, which can be found here: [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b769e-113">示例</span><span class="sxs-lookup"><span data-stu-id="b769e-113">Example</span></span>  
 <span data-ttu-id="b769e-114">若要返回的外接程序创建[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]以及每个管道段外, 接程序时，主机应用程序需要特定的代码。</span><span class="sxs-lookup"><span data-stu-id="b769e-114">To create an add-in that returns a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="b769e-115">实现协定管道段</span><span class="sxs-lookup"><span data-stu-id="b769e-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="b769e-116">方法必须由返回的协定定义[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，且其返回值必须为类型<xref:System.AddIn.Contract.INativeHandleContract>。</span><span class="sxs-lookup"><span data-stu-id="b769e-116">A method must be defined by the contract for returning a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="b769e-117">说明了这一点通过`GetAddInUI`方法`IWPFAddInContract`在下面的代码协定。</span><span class="sxs-lookup"><span data-stu-id="b769e-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="b769e-118">实现外接程序视图管道段</span><span class="sxs-lookup"><span data-stu-id="b769e-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="b769e-119">因为外接程序实现[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]它作为的子类提供<xref:System.Windows.FrameworkElement>，与容量相关联的外接程序视图上的方法`IWPFAddInView.GetAddInUI`必须返回类型的值<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="b769e-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="b769e-120">以下代码显示作为接口实现的协定的外接程序视图。</span><span class="sxs-lookup"><span data-stu-id="b769e-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="b769e-121">实现外接程序端适配器管道段</span><span class="sxs-lookup"><span data-stu-id="b769e-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="b769e-122">该协定方法返回<xref:System.AddIn.Contract.INativeHandleContract>，但外接程序返回<xref:System.Windows.FrameworkElement>（所指定的外接程序视图）。</span><span class="sxs-lookup"><span data-stu-id="b769e-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="b769e-123">因此，<xref:System.Windows.FrameworkElement>必须转换为<xref:System.AddIn.Contract.INativeHandleContract>在越过隔离边界之前。</span><span class="sxs-lookup"><span data-stu-id="b769e-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="b769e-124">通过调用执行此工作的外接程序端适配器<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="b769e-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="b769e-125">实现主机视图管道段</span><span class="sxs-lookup"><span data-stu-id="b769e-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="b769e-126">因为主机应用程序将显示<xref:System.Windows.FrameworkElement>，与容量相关联的主机视图上的方法`IWPFAddInHostView.GetAddInUI`必须返回类型的值<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="b769e-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="b769e-127">以下代码显示作为接口实现的协定的主机视图。</span><span class="sxs-lookup"><span data-stu-id="b769e-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="b769e-128">实现主机端适配器管道段</span><span class="sxs-lookup"><span data-stu-id="b769e-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="b769e-129">该协定方法返回<xref:System.AddIn.Contract.INativeHandleContract>，但主机应用程序需要<xref:System.Windows.FrameworkElement>（所指定的主机视图）。</span><span class="sxs-lookup"><span data-stu-id="b769e-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="b769e-130">因此，<xref:System.AddIn.Contract.INativeHandleContract>必须转换为<xref:System.Windows.FrameworkElement>越过隔离边界之后。</span><span class="sxs-lookup"><span data-stu-id="b769e-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="b769e-131">通过调用执行此工作的主机端适配器<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="b769e-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="b769e-132">实现外接程序</span><span class="sxs-lookup"><span data-stu-id="b769e-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="b769e-133">使用外接程序端适配器和外接程序中创建视图外, 接程序 (`WPFAddIn1.AddIn`) 必须实现`IWPFAddInView.GetAddInUI`方法以返回<xref:System.Windows.FrameworkElement>对象 (<xref:System.Windows.Controls.UserControl>在此示例中)。</span><span class="sxs-lookup"><span data-stu-id="b769e-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="b769e-134">实现<xref:System.Windows.Controls.UserControl>， `AddInUI`，通过以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="b769e-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="b769e-135">实现`IWPFAddInView.GetAddInUI`通过外接程序只需返回的新实例`AddInUI`，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="b769e-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="b769e-136">实现主机应用程序</span><span class="sxs-lookup"><span data-stu-id="b769e-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="b769e-137">主机端适配器和创建主机视图中，主机应用程序可以使用[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型来打开管道，可获取的宿主视图的外接程序，并调用`IWPFAddInHostView.GetAddInUI`方法。</span><span class="sxs-lookup"><span data-stu-id="b769e-137">With the host-side adapter and host view created, the host application can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="b769e-138">这些步骤在以下代码中显示。</span><span class="sxs-lookup"><span data-stu-id="b769e-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="b769e-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b769e-139">See Also</span></span>  
 [<span data-ttu-id="b769e-140">外接程序和扩展性</span><span class="sxs-lookup"><span data-stu-id="b769e-140">Add-ins and Extensibility</span></span>](../../../../docs/framework/add-ins/index.md)  
 [<span data-ttu-id="b769e-141">WPF 外接程序概述</span><span class="sxs-lookup"><span data-stu-id="b769e-141">WPF Add-Ins Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
