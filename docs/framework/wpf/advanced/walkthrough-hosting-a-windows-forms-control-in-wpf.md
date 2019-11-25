---
title: 演练：在 WPF 中承载 Windows 窗体控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: e353c35e9989e5887e038371672adbb6c2d3598d
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976530"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="09925-102">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="09925-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="09925-103">提供了许多具有丰富功能集的控件。</span><span class="sxs-lookup"><span data-stu-id="09925-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="09925-104">但是，有时您可能希望在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上使用 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。</span><span class="sxs-lookup"><span data-stu-id="09925-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="09925-105">例如，您可能在现有 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件中有大量投资，或者您可能有一个提供独特功能的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。</span><span class="sxs-lookup"><span data-stu-id="09925-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>

<span data-ttu-id="09925-106">本演练演示如何使用代码在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上承载 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 控件。</span><span class="sxs-lookup"><span data-stu-id="09925-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="09925-107">有关本演练中所示任务的完整代码列表，请参阅[在 WPF 中承载 Windows 窗体控件示例](https://go.microsoft.com/fwlink/?LinkID=160057)。</span><span class="sxs-lookup"><span data-stu-id="09925-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="09925-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="09925-108">Prerequisites</span></span>

<span data-ttu-id="09925-109">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="09925-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="09925-110">承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="09925-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="09925-111">承载 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="09925-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="09925-112">创建一个名为 `HostingWfInWpf`的 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="09925-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="09925-113">添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="09925-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="09925-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="09925-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="09925-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="09925-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="09925-116">在 WPF 设计器中打开 Mainwindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="09925-116">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="09925-117">将 <xref:System.Windows.Controls.Grid> 元素命名为 `grid1`。</span><span class="sxs-lookup"><span data-stu-id="09925-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="09925-118">在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 元素。</span><span class="sxs-lookup"><span data-stu-id="09925-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="09925-119">在属性窗口中，单击 "**事件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="09925-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="09925-120">双击 "<xref:System.Windows.FrameworkElement.Loaded>" 事件。</span><span class="sxs-lookup"><span data-stu-id="09925-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="09925-121">插入以下代码来处理 <xref:System.Windows.FrameworkElement.Loaded> 事件。</span><span class="sxs-lookup"><span data-stu-id="09925-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="09925-122">在该文件的顶部，添加以下 `Imports` 或 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="09925-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="09925-123">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="09925-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="09925-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="09925-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="09925-125">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="09925-125">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="09925-126">演练：使用 XAML 在 WPF 中托管 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="09925-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="09925-127">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="09925-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="09925-128">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="09925-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="09925-129">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="09925-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="09925-130">在 WPF 示例中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="09925-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160057)
