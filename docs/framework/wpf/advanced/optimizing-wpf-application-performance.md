---
title: 优化 WPF 应用程序性能
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: c1dd2587fb3642fb930fb7d5d6855a6e48c2ad2b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356385"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="a5af4-102">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="a5af4-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="a5af4-103">本部分旨在作为参考[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序开发人员正在寻找方法来提高他们的应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="a5af4-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="a5af4-104">如果你是开发人员是 Microsoft.NET Framework 中新增和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，您应该首先熟悉这两个平台。</span><span class="sxs-lookup"><span data-stu-id="a5af4-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="a5af4-105">本部分假定这两种知识并专为编程人员已经知道足以让他们的应用程序启动并运行。</span><span class="sxs-lookup"><span data-stu-id="a5af4-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5af4-106">在本部分中提供的性能数据基于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]RAM 和 ATI Radeon 9700，2.8 GHz PC 上使用 512 运行的应用程序的图形卡。</span><span class="sxs-lookup"><span data-stu-id="a5af4-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5af4-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="a5af4-107">In This Section</span></span>  
 [<span data-ttu-id="a5af4-108">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="a5af4-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="a5af4-109">利用硬件</span><span class="sxs-lookup"><span data-stu-id="a5af4-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="a5af4-110">布局和示例</span><span class="sxs-lookup"><span data-stu-id="a5af4-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="a5af4-111">2D 图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="a5af4-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="a5af4-112">对象行为</span><span class="sxs-lookup"><span data-stu-id="a5af4-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="a5af4-113">应用程序资源</span><span class="sxs-lookup"><span data-stu-id="a5af4-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="a5af4-114">文本</span><span class="sxs-lookup"><span data-stu-id="a5af4-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="a5af4-115">数据绑定</span><span class="sxs-lookup"><span data-stu-id="a5af4-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="a5af4-116">控件</span><span class="sxs-lookup"><span data-stu-id="a5af4-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="a5af4-117">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="a5af4-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="a5af4-118">应用程序启动时间</span><span class="sxs-lookup"><span data-stu-id="a5af4-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5af4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5af4-119">See also</span></span>
- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="a5af4-120">图形呈现层</span><span class="sxs-lookup"><span data-stu-id="a5af4-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="a5af4-121">WPF 图形呈现概述</span><span class="sxs-lookup"><span data-stu-id="a5af4-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="a5af4-122">布局</span><span class="sxs-lookup"><span data-stu-id="a5af4-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="a5af4-123">WPF 中的树</span><span class="sxs-lookup"><span data-stu-id="a5af4-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="a5af4-124">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="a5af4-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="a5af4-125">使用 DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="a5af4-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="a5af4-126">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="a5af4-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="a5af4-127">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="a5af4-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="a5af4-128">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="a5af4-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="a5af4-129">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="a5af4-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="a5af4-130">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="a5af4-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="a5af4-131">WPF 中的版式</span><span class="sxs-lookup"><span data-stu-id="a5af4-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="a5af4-132">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="a5af4-132">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="a5af4-133">导航概述</span><span class="sxs-lookup"><span data-stu-id="a5af4-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="a5af4-134">动画提示和技巧</span><span class="sxs-lookup"><span data-stu-id="a5af4-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="a5af4-135">演练：缓存在 WPF 应用程序的应用程序数据</span><span class="sxs-lookup"><span data-stu-id="a5af4-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
