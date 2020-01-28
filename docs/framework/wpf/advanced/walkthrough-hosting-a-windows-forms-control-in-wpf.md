---
title: 在 WPF 中承载 Windows 窗体控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: f7e925529f1bf194664c4f776bcc0322314f8857
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744915"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="241c3-102">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="241c3-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="241c3-103">에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="241c3-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="241c3-104">但是，有时您可能希望在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上使用 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。</span><span class="sxs-lookup"><span data-stu-id="241c3-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="241c3-105">例如，您可能在现有 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件中有大量投资，或者您可能有一个提供独特功能的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。</span><span class="sxs-lookup"><span data-stu-id="241c3-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>

<span data-ttu-id="241c3-106">本演练演示如何使用代码在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上承载 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 控件。</span><span class="sxs-lookup"><span data-stu-id="241c3-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="241c3-107">有关本演练中所示任务的完整代码列表，请参阅[在 WPF 中承载 Windows 窗体控件示例](https://go.microsoft.com/fwlink/?LinkID=160057)。</span><span class="sxs-lookup"><span data-stu-id="241c3-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="241c3-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="241c3-108">Prerequisites</span></span>

<span data-ttu-id="241c3-109">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="241c3-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="241c3-110">Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="241c3-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="241c3-111">MaskedTextBox 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="241c3-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="241c3-112">创建一个名为 `HostingWfInWpf`的 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="241c3-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="241c3-113">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="241c3-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="241c3-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="241c3-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="241c3-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="241c3-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="241c3-116">在 WPF 设计器中打开 Mainwindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="241c3-116">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="241c3-117">将 <xref:System.Windows.Controls.Grid> 元素命名为 `grid1`。</span><span class="sxs-lookup"><span data-stu-id="241c3-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="241c3-118">在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 元素。</span><span class="sxs-lookup"><span data-stu-id="241c3-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="241c3-119">在属性窗口中，单击 "**事件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="241c3-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="241c3-120">双击 "<xref:System.Windows.FrameworkElement.Loaded>" 事件。</span><span class="sxs-lookup"><span data-stu-id="241c3-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="241c3-121">插入以下代码来处理 <xref:System.Windows.FrameworkElement.Loaded> 事件。</span><span class="sxs-lookup"><span data-stu-id="241c3-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="241c3-122">在该文件的顶部，添加以下 `Imports` 或 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="241c3-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="241c3-123">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="241c3-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="241c3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="241c3-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="241c3-125">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="241c3-125">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="241c3-126">연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="241c3-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="241c3-127">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="241c3-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="241c3-128">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="241c3-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="241c3-129">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="241c3-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="241c3-130">WPF에서 Windows Forms 컨트롤 호스팅 샘플</span><span class="sxs-lookup"><span data-stu-id="241c3-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160057)
