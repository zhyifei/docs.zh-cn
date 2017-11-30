---
title: "如何：在混合应用程序中启用视觉样式"
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
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e628835f0e5fb315f15b9e9946c48f7017092bae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="fdc33-102">如何：在混合应用程序中启用视觉样式</span><span class="sxs-lookup"><span data-stu-id="fdc33-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="fdc33-103">本主题演示如何启用[!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]视觉样式上[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件中托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdc33-103">This topic shows how to enable [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="fdc33-104">如果你的应用程序调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法，大部分你[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件自动将你的应用程序在运行时使用可视样式[!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fdc33-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles when your application is run on [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span></span> <span data-ttu-id="fdc33-105">有关详细信息，请参阅[以视觉样式呈现控件](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)。</span><span class="sxs-lookup"><span data-stu-id="fdc33-105">For more information, see [Rendering Controls with Visual Styles](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="fdc33-106">本主题中所示的任务的完整代码清单，请参阅[启用混合应用程序示例中的视觉样式](http://go.microsoft.com/fwlink/?LinkID=159986)。</span><span class="sxs-lookup"><span data-stu-id="fdc33-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](http://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="fdc33-107">启用 Windows 窗体视觉样式</span><span class="sxs-lookup"><span data-stu-id="fdc33-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="fdc33-108">启用 Windows 窗体视觉样式</span><span class="sxs-lookup"><span data-stu-id="fdc33-108">To enable Windows Forms visual styles</span></span>  
  
1.  <span data-ttu-id="fdc33-109">创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序项目中名为`HostingWfWithVisualStyles`。</span><span class="sxs-lookup"><span data-stu-id="fdc33-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2.  <span data-ttu-id="fdc33-110">在解决方案资源管理器中，添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fdc33-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="fdc33-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="fdc33-111">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="fdc33-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="fdc33-112">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="fdc33-113">在工具箱中，双击<xref:System.Windows.Controls.Grid>图标将<xref:System.Windows.Controls.Grid>设计图面上的元素。</span><span class="sxs-lookup"><span data-stu-id="fdc33-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4.  <span data-ttu-id="fdc33-114">在属性窗口中，设置的值<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>属性设置为**自动**。</span><span class="sxs-lookup"><span data-stu-id="fdc33-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5.  <span data-ttu-id="fdc33-115">在设计视图或 XAML 视图中，选择<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="fdc33-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6.  <span data-ttu-id="fdc33-116">在属性窗口中，单击**事件**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fdc33-116">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="fdc33-117">双击<xref:System.Windows.FrameworkElement.Loaded>事件。</span><span class="sxs-lookup"><span data-stu-id="fdc33-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8.  <span data-ttu-id="fdc33-118">在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，插入以下代码以处理<xref:System.Windows.FrameworkElement.Loaded>事件。</span><span class="sxs-lookup"><span data-stu-id="fdc33-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="fdc33-119">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdc33-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="fdc33-120">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]使用视觉样式绘制控件。</span><span class="sxs-lookup"><span data-stu-id="fdc33-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="fdc33-121">禁用 Windows 窗体视觉样式</span><span class="sxs-lookup"><span data-stu-id="fdc33-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="fdc33-122">若要禁用视觉样式，只需删除对的调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="fdc33-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="fdc33-123">禁用 Windows 窗体视觉样式</span><span class="sxs-lookup"><span data-stu-id="fdc33-123">To disable Windows Forms visual styles</span></span>  
  
1.  <span data-ttu-id="fdc33-124">在代码编辑器中打开 MainWindow.xaml.vb 或 MainWindow.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="fdc33-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="fdc33-125">注释掉对的调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="fdc33-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3.  <span data-ttu-id="fdc33-126">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdc33-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="fdc33-127">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]使用默认系统样式绘制控件。</span><span class="sxs-lookup"><span data-stu-id="fdc33-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc33-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdc33-128">See Also</span></span>  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="fdc33-129">使用视觉样式呈现控件</span><span class="sxs-lookup"><span data-stu-id="fdc33-129">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [<span data-ttu-id="fdc33-130">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="fdc33-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
