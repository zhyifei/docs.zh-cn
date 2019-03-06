---
title: 演练：承载在 WPF 中的 Windows 窗体控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 8ef13ef89072f91c847a05facbcce344dda6ade2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374878"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="5a746-102">演练：承载在 WPF 中的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5a746-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="5a746-103">提供了许多具有丰富功能集的控件。</span><span class="sxs-lookup"><span data-stu-id="5a746-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="5a746-104">但是，您可能有时想要使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]上的控件在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页。</span><span class="sxs-lookup"><span data-stu-id="5a746-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="5a746-105">例如，可能有大量现有投入[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，或者您可能需[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，用于提供的独特功能。</span><span class="sxs-lookup"><span data-stu-id="5a746-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>

<span data-ttu-id="5a746-106">本演练演示如何承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>控制上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用代码页。</span><span class="sxs-lookup"><span data-stu-id="5a746-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="5a746-107">在本演练中所示的任务的完整代码列表，请参阅[承载 Windows 窗体控件在 WPF 示例中](https://go.microsoft.com/fwlink/?LinkID=160057)。</span><span class="sxs-lookup"><span data-stu-id="5a746-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a746-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="5a746-108">Prerequisites</span></span>

<span data-ttu-id="5a746-109">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="5a746-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="5a746-110">承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5a746-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="5a746-111">承载 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="5a746-111">To host the MaskedTextBox control</span></span>

1.  <span data-ttu-id="5a746-112">创建一个名为的 WPF 应用程序项目`HostingWfInWpf`。</span><span class="sxs-lookup"><span data-stu-id="5a746-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2.  <span data-ttu-id="5a746-113">添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="5a746-113">Add references to the following assemblies.</span></span>

    -   <span data-ttu-id="5a746-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="5a746-114">WindowsFormsIntegration</span></span>

    -   <span data-ttu-id="5a746-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="5a746-115">System.Windows.Forms</span></span>

3.  <span data-ttu-id="5a746-116">打开 MainWindow.xaml 中的[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5a746-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

4.  <span data-ttu-id="5a746-117">名称<xref:System.Windows.Controls.Grid>元素`grid1`。</span><span class="sxs-lookup"><span data-stu-id="5a746-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5.  <span data-ttu-id="5a746-118">在设计视图或 XAML 视图中，选择<xref:System.Windows.Window>元素。</span><span class="sxs-lookup"><span data-stu-id="5a746-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6.  <span data-ttu-id="5a746-119">在属性窗口中，单击**事件**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5a746-119">In the Properties window, click the **Events** tab.</span></span>

7.  <span data-ttu-id="5a746-120">双击<xref:System.Windows.FrameworkElement.Loaded>事件。</span><span class="sxs-lookup"><span data-stu-id="5a746-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8.  <span data-ttu-id="5a746-121">插入以下代码以处理<xref:System.Windows.FrameworkElement.Loaded>事件。</span><span class="sxs-lookup"><span data-stu-id="5a746-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="5a746-122">在文件顶部，添加以下`Imports`或`using`语句。</span><span class="sxs-lookup"><span data-stu-id="5a746-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="5a746-123">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="5a746-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a746-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a746-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="5a746-125">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="5a746-125">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="5a746-126">演练：使用 XAML 承载在 WPF 中的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5a746-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="5a746-127">演练：承载在 WPF 中的 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="5a746-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="5a746-128">演练：承载 WPF 复合控件在 Windows 窗体中</span><span class="sxs-lookup"><span data-stu-id="5a746-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="5a746-129">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="5a746-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="5a746-130">在 WPF 示例中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5a746-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160057)
