---
title: Windows 窗体中的图形和绘制
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 08f87436ade62bb54295b012a1c24dc177ea9667
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705413"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="ce044-102">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="ce044-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="ce044-103">公共语言运行时使用名为 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 的 Windows 图形设备接口的高级实现 ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) 。</span><span class="sxs-lookup"><span data-stu-id="ce044-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) called [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="ce044-104">通过 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你可以创建图形、绘制文本以及将图形图像作为对象进行操作。</span><span class="sxs-lookup"><span data-stu-id="ce044-104">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can create graphics, draw text, and manipulate graphical images as objects.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="ce044-105">旨在提供良好性能和易用性。</span><span class="sxs-lookup"><span data-stu-id="ce044-105">is designed to offer performance and ease of use.</span></span> <span data-ttu-id="ce044-106">可以使用 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 来呈现 Windows 窗体和控件上的图形图像。</span><span class="sxs-lookup"><span data-stu-id="ce044-106">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="ce044-107">虽然不能直接在 Web 窗体上使用 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，但可通过图像 Web 服务器控件显示图形图像。</span><span class="sxs-lookup"><span data-stu-id="ce044-107">Although you cannot use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="ce044-108">在本节中，你会发现介绍 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 编程基础知识的主题。</span><span class="sxs-lookup"><span data-stu-id="ce044-108">In this section, you will find topics that introduce the fundamentals of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] programming.</span></span> <span data-ttu-id="ce044-109">本节虽非全面的参考，但涵盖有关 <xref:System.Drawing.Graphics>、<xref:System.Drawing.Pen>、<xref:System.Drawing.Brush> 和 <xref:System.Drawing.Color> 对象的信息，并介绍了如何执行绘制形状、绘制文本或显示图像等任务。</span><span class="sxs-lookup"><span data-stu-id="ce044-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="ce044-110">有关详细信息，请参阅[GDI + 参考](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)。</span><span class="sxs-lookup"><span data-stu-id="ce044-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="ce044-111">若要立即开始，请参阅[图形编程入门](getting-started-with-graphics-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="ce044-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="ce044-112">其中包含如何使用代码在 Windows 窗体上绘制线、形状和文本等相关主题。</span><span class="sxs-lookup"><span data-stu-id="ce044-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce044-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="ce044-113">In This Section</span></span>  
 [<span data-ttu-id="ce044-114">图形概述</span><span class="sxs-lookup"><span data-stu-id="ce044-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="ce044-115">介绍与与图形相关的托管类。</span><span class="sxs-lookup"><span data-stu-id="ce044-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="ce044-116">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="ce044-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="ce044-117">提供有关托管 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 类的信息。</span><span class="sxs-lookup"><span data-stu-id="ce044-117">Provides information about the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span>  
  
 [<span data-ttu-id="ce044-118">使用托管图形类</span><span class="sxs-lookup"><span data-stu-id="ce044-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="ce044-119">演示如何使用 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 托管类完成各种任务。</span><span class="sxs-lookup"><span data-stu-id="ce044-119">Demonstrates how to complete a variety of tasks using the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ce044-120">参考</span><span class="sxs-lookup"><span data-stu-id="ce044-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="ce044-121">提供对 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 基本图形功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ce044-121">Provides access to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="ce044-122">提供高级二维和矢量图形功能。</span><span class="sxs-lookup"><span data-stu-id="ce044-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="ce044-123">提供高级 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 图像处理功能。</span><span class="sxs-lookup"><span data-stu-id="ce044-123">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="ce044-124">提供高级 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 板式功能。</span><span class="sxs-lookup"><span data-stu-id="ce044-124">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] typography functionality.</span></span> <span data-ttu-id="ce044-125">此命名空间中的类可用于创建和使用字体集合。</span><span class="sxs-lookup"><span data-stu-id="ce044-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="ce044-126">提供打印功能。</span><span class="sxs-lookup"><span data-stu-id="ce044-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ce044-127">相关章节</span><span class="sxs-lookup"><span data-stu-id="ce044-127">Related Sections</span></span>  
 [<span data-ttu-id="ce044-128">自定义控件的绘制和呈现</span><span class="sxs-lookup"><span data-stu-id="ce044-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="ce044-129">详细介绍如何为绘制控件提供代码。</span><span class="sxs-lookup"><span data-stu-id="ce044-129">Details how to provide code for painting controls.</span></span>
