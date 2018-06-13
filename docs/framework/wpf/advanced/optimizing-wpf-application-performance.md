---
title: 优化 WPF 应用程序性能
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: faa06e4558401c1d0e9335fbc630c5371d1bc516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546323"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="98d1c-102">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="98d1c-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="98d1c-103">本部分旨在作为的参考[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序开发人员正在寻找方法来提高其应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="98d1c-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="98d1c-104">如果你是开发人员是新的 Microsoft.NET framework 和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，你应该首先熟悉这两个平台。</span><span class="sxs-lookup"><span data-stu-id="98d1c-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="98d1c-105">本部分假定知识两种方法，并为已经知道不足以获得其应用程序启动并正在运行的程序员编写。</span><span class="sxs-lookup"><span data-stu-id="98d1c-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98d1c-106">本部分中提供的性能数据基于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]RAM 和 ATI Radeon 9700，2.8 GHz 电脑上使用 512 运行应用程序图形卡。</span><span class="sxs-lookup"><span data-stu-id="98d1c-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98d1c-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="98d1c-107">In This Section</span></span>  
 [<span data-ttu-id="98d1c-108">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="98d1c-108">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [<span data-ttu-id="98d1c-109">利用硬件</span><span class="sxs-lookup"><span data-stu-id="98d1c-109">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="98d1c-110">布局和示例</span><span class="sxs-lookup"><span data-stu-id="98d1c-110">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="98d1c-111">2D 图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="98d1c-111">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="98d1c-112">对象行为</span><span class="sxs-lookup"><span data-stu-id="98d1c-112">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="98d1c-113">应用程序资源</span><span class="sxs-lookup"><span data-stu-id="98d1c-113">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="98d1c-114">文本</span><span class="sxs-lookup"><span data-stu-id="98d1c-114">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [<span data-ttu-id="98d1c-115">数据绑定</span><span class="sxs-lookup"><span data-stu-id="98d1c-115">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="98d1c-116">控件</span><span class="sxs-lookup"><span data-stu-id="98d1c-116">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [<span data-ttu-id="98d1c-117">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="98d1c-117">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="98d1c-118">应用程序启动时间</span><span class="sxs-lookup"><span data-stu-id="98d1c-118">Application Startup Time</span></span>](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="98d1c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="98d1c-119">See Also</span></span>  
 <xref:System.Windows.Media.RenderOptions>  
 <xref:System.Windows.Media.RenderCapability>  
 [<span data-ttu-id="98d1c-120">图形呈现层</span><span class="sxs-lookup"><span data-stu-id="98d1c-120">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)  
 [<span data-ttu-id="98d1c-121">WPF 图形呈现概述</span><span class="sxs-lookup"><span data-stu-id="98d1c-121">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="98d1c-122">布局</span><span class="sxs-lookup"><span data-stu-id="98d1c-122">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
 [<span data-ttu-id="98d1c-123">WPF 中的树</span><span class="sxs-lookup"><span data-stu-id="98d1c-123">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [<span data-ttu-id="98d1c-124">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="98d1c-124">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="98d1c-125">使用 DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="98d1c-125">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)  
 [<span data-ttu-id="98d1c-126">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="98d1c-126">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="98d1c-127">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="98d1c-127">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="98d1c-128">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="98d1c-128">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="98d1c-129">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="98d1c-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="98d1c-130">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="98d1c-130">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [<span data-ttu-id="98d1c-131">WPF 中的版式</span><span class="sxs-lookup"><span data-stu-id="98d1c-131">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="98d1c-132">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="98d1c-132">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="98d1c-133">导航概述</span><span class="sxs-lookup"><span data-stu-id="98d1c-133">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [<span data-ttu-id="98d1c-134">动画提示和技巧</span><span class="sxs-lookup"><span data-stu-id="98d1c-134">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)  
 [<span data-ttu-id="98d1c-135">演练：在 WPF 应用程序中缓存应用程序数据</span><span class="sxs-lookup"><span data-stu-id="98d1c-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
