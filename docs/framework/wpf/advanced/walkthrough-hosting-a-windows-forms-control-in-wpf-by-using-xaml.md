---
title: 使用 XAML 在 WPF 中承载 Windows 窗体控件
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: a0a88c39a25e5292365a6447cefdd8f31db5e5c3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744919"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="18491-102">연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="18491-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="18491-103">에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="18491-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="18491-104">但是，有时您可能希望在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上使用 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。</span><span class="sxs-lookup"><span data-stu-id="18491-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="18491-105">例如，您可能在现有 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件中有大量投资，或者您可能有一个提供独特功能的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。</span><span class="sxs-lookup"><span data-stu-id="18491-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="18491-106">本演练演示如何使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上承载 Windows 窗体 <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 控件。</span><span class="sxs-lookup"><span data-stu-id="18491-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="18491-107">有关本演练中所示任务的完整代码列表，请参阅[使用 XAML 在 WPF 中承载 Windows 窗体控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)。</span><span class="sxs-lookup"><span data-stu-id="18491-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="18491-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="18491-108">Prerequisites</span></span>  

<span data-ttu-id="18491-109">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="18491-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="18491-110">Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="18491-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="18491-111">MaskedTextBox 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="18491-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="18491-112">创建一个名为 `HostingWfInWpfWithXaml`的 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="18491-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="18491-113">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="18491-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="18491-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="18491-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="18491-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="18491-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="18491-116">在 WPF 设计器中打开 Mainwindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="18491-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="18491-117">在 <xref:System.Windows.Window> 元素中，添加以下命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="18491-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="18491-118">`wf` 命名空间映射将建立对包含 Windows 窗体控件的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="18491-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="18491-119">在 <xref:System.Windows.Controls.Grid> 元素中添加以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="18491-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="18491-120"><xref:System.Windows.Forms.MaskedTextBox> 控件创建为 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的子控件。</span><span class="sxs-lookup"><span data-stu-id="18491-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="18491-121">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18491-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18491-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18491-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="18491-123">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="18491-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="18491-124">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="18491-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="18491-125">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="18491-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="18491-126">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="18491-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="18491-127">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="18491-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="18491-128">使用 XAML 在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="18491-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
