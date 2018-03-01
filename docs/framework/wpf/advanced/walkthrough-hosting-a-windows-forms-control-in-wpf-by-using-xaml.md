---
title: "演练：使用 XAML 在 WPF 中承载 Windows 窗体控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65afce3e5a5b113b5243d68fd3b35231e2d92f86
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="66f6f-102">演练：使用 XAML 在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="66f6f-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="66f6f-103"> 提供了许多具有丰富功能集的控件。</span><span class="sxs-lookup"><span data-stu-id="66f6f-103"> provides many controls with a rich feature set.</span></span> <span data-ttu-id="66f6f-104">但是，你可能有时想要使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]上的控件你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页。</span><span class="sxs-lookup"><span data-stu-id="66f6f-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="66f6f-105">例如，您可能必须在存在大量的投资[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，或你可能具有[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]提供唯一的功能的控件。</span><span class="sxs-lookup"><span data-stu-id="66f6f-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="66f6f-106">本演练演示如何承载 Windows 窗体<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>控制上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页上通过使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66f6f-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="66f6f-107">在本演练中所示的任务的完整代码清单，请参阅[承载 Windows 窗体控件在 WPF 中使用的 XAML 示例](http://go.microsoft.com/fwlink/?LinkID=160000)。</span><span class="sxs-lookup"><span data-stu-id="66f6f-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="66f6f-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="66f6f-108">Prerequisites</span></span>  
 <span data-ttu-id="66f6f-109">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="66f6f-109">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="66f6f-110">。</span><span class="sxs-lookup"><span data-stu-id="66f6f-110">.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="66f6f-111">承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="66f6f-111">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="66f6f-112">承载 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="66f6f-112">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="66f6f-113">创建一个名为的 WPF 应用程序项目`HostingWfInWpfWithXaml`。</span><span class="sxs-lookup"><span data-stu-id="66f6f-113">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2.  <span data-ttu-id="66f6f-114">添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="66f6f-114">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="66f6f-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="66f6f-115">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="66f6f-116">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="66f6f-116">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="66f6f-117">打开在 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66f6f-117">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="66f6f-118">在<xref:System.Windows.Window>元素中，添加以下命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="66f6f-118">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="66f6f-119">`wf`命名空间映射建立对包含的程序集的引用[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="66f6f-119">The `wf` namespace mapping establishes a reference to the assembly that contains the [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="66f6f-120">在<xref:System.Windows.Controls.Grid>元素中添加以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="66f6f-120">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="66f6f-121"><xref:System.Windows.Forms.MaskedTextBox>创建控件的子级<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件。</span><span class="sxs-lookup"><span data-stu-id="66f6f-121">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  <span data-ttu-id="66f6f-122">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="66f6f-122">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f6f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="66f6f-123">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="66f6f-124">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="66f6f-124">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="66f6f-125">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="66f6f-125">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="66f6f-126">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="66f6f-126">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="66f6f-127">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="66f6f-127">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="66f6f-128">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="66f6f-128">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [<span data-ttu-id="66f6f-129">通过使用 XAML 示例中承载 WPF 中的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="66f6f-129">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160000)
