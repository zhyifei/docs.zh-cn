---
title: 演练：在 WPF 中承载 Windows 窗体控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 515135893c0d6cf251977bbddc13241e8b6b60bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546824"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="d02d5-102">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d02d5-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="d02d5-103"> 提供了许多具有丰富功能集的控件。</span><span class="sxs-lookup"><span data-stu-id="d02d5-103"> provides many controls with a rich feature set.</span></span> <span data-ttu-id="d02d5-104">但是，你可能有时想要使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]上的控件你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页。</span><span class="sxs-lookup"><span data-stu-id="d02d5-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="d02d5-105">例如，您可能必须在存在大量的投资[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，或你可能具有[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]提供唯一的功能的控件。</span><span class="sxs-lookup"><span data-stu-id="d02d5-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="d02d5-106">本演练演示如何承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>控制上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通过使用代码页。</span><span class="sxs-lookup"><span data-stu-id="d02d5-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>  
  
 <span data-ttu-id="d02d5-107">在本演练中所示的任务的完整代码清单，请参阅[承载 Windows 窗体控件在 WPF 示例](http://go.microsoft.com/fwlink/?LinkID=160057)。</span><span class="sxs-lookup"><span data-stu-id="d02d5-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=160057).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d02d5-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="d02d5-108">Prerequisites</span></span>  
 <span data-ttu-id="d02d5-109">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="d02d5-109">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="d02d5-110">。</span><span class="sxs-lookup"><span data-stu-id="d02d5-110">.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="d02d5-111">承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d02d5-111">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="d02d5-112">承载 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="d02d5-112">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="d02d5-113">创建一个名为的 WPF 应用程序项目`HostingWfInWpf`。</span><span class="sxs-lookup"><span data-stu-id="d02d5-113">Create a WPF Application project named `HostingWfInWpf`.</span></span>  
  
2.  <span data-ttu-id="d02d5-114">添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d02d5-114">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="d02d5-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="d02d5-115">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="d02d5-116">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="d02d5-116">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="d02d5-117">打开在 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d02d5-117">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="d02d5-118">名称<xref:System.Windows.Controls.Grid>元素`grid1`。</span><span class="sxs-lookup"><span data-stu-id="d02d5-118">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>  
  
     [!code-xaml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]  
  
5.  <span data-ttu-id="d02d5-119">在设计视图或 XAML 视图中，选择<xref:System.Windows.Window>元素。</span><span class="sxs-lookup"><span data-stu-id="d02d5-119">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
6.  <span data-ttu-id="d02d5-120">在属性窗口中，单击**事件**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d02d5-120">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="d02d5-121">双击<xref:System.Windows.FrameworkElement.Loaded>事件。</span><span class="sxs-lookup"><span data-stu-id="d02d5-121">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
8.  <span data-ttu-id="d02d5-122">插入以下代码以处理<xref:System.Windows.FrameworkElement.Loaded>事件。</span><span class="sxs-lookup"><span data-stu-id="d02d5-122">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]  
  
9. <span data-ttu-id="d02d5-123">在文件的顶部，添加以下`Imports`或`using`语句。</span><span class="sxs-lookup"><span data-stu-id="d02d5-123">At the top of the file, add the following `Imports` or `using` statement.</span></span>  
  
     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]  
  
10. <span data-ttu-id="d02d5-124">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="d02d5-124">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d02d5-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="d02d5-125">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="d02d5-126">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="d02d5-126">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="d02d5-127">演练：使用 XAML 在 WPF 中托管 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d02d5-127">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)  
 [<span data-ttu-id="d02d5-128">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="d02d5-128">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="d02d5-129">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="d02d5-129">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="d02d5-130">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="d02d5-130">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [<span data-ttu-id="d02d5-131">在 WPF 示例中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d02d5-131">Hosting a Windows Forms Control in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160057)
