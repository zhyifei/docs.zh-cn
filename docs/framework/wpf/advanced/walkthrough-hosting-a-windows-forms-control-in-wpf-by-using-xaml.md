---
title: 演练：使用 XAML 在 WPF 中承载 Windows 窗体控件
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 2f13689a15e91ee0f80c0d7b6bc71c5f973b8333
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083863"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="a9724-102">演练：使用 XAML 在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="a9724-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="a9724-103"> 提供了许多具有丰富功能集的控件。</span><span class="sxs-lookup"><span data-stu-id="a9724-103"> provides many controls with a rich feature set.</span></span> <span data-ttu-id="a9724-104">但是，您可能有时想要使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]上的控件在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页。</span><span class="sxs-lookup"><span data-stu-id="a9724-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="a9724-105">例如，可能有大量现有投入[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，或者您可能需[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，用于提供的独特功能。</span><span class="sxs-lookup"><span data-stu-id="a9724-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="a9724-106">本演练演示如何承载 Windows 窗体<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>对的 control 权限[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页上通过使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9724-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="a9724-107">在本演练中所示的任务的完整代码列表，请参阅[承载 Windows 窗体控件在 WPF 中使用 XAML 示例](https://go.microsoft.com/fwlink/?LinkID=160000)。</span><span class="sxs-lookup"><span data-stu-id="a9724-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://go.microsoft.com/fwlink/?LinkID=160000).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a9724-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="a9724-108">Prerequisites</span></span>  
 <span data-ttu-id="a9724-109">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="a9724-109">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="a9724-110">。</span><span class="sxs-lookup"><span data-stu-id="a9724-110">.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="a9724-111">承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="a9724-111">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="a9724-112">承载 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="a9724-112">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="a9724-113">创建一个名为的 WPF 应用程序项目`HostingWfInWpfWithXaml`。</span><span class="sxs-lookup"><span data-stu-id="a9724-113">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2.  <span data-ttu-id="a9724-114">添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a9724-114">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="a9724-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="a9724-115">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="a9724-116">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="a9724-116">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="a9724-117">打开 MainWindow.xaml 中的[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9724-117">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="a9724-118">在<xref:System.Windows.Window>元素中，添加以下命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="a9724-118">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="a9724-119">`wf`命名空间映射建立对包含在 Windows 窗体控件的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a9724-119">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="a9724-120">在<xref:System.Windows.Controls.Grid>添加以下 XAML 元素。</span><span class="sxs-lookup"><span data-stu-id="a9724-120">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="a9724-121"><xref:System.Windows.Forms.MaskedTextBox>控件被创建为的子<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件。</span><span class="sxs-lookup"><span data-stu-id="a9724-121">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  <span data-ttu-id="a9724-122">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9724-122">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9724-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9724-123">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="a9724-124">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="a9724-124">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [<span data-ttu-id="a9724-125">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="a9724-125">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="a9724-126">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="a9724-126">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="a9724-127">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="a9724-127">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="a9724-128">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="a9724-128">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [<span data-ttu-id="a9724-129">通过使用 XAML 示例中承载 WPF 中的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="a9724-129">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
