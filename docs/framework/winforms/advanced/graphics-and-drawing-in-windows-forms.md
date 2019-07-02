---
title: Windows 窗体中的图形和绘制
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505543"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="33c4d-102">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="33c4d-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="33c4d-103">公共语言运行时使用的高级的实现的 Windows 图形设备接口 (GDI) 调用 GDI +。</span><span class="sxs-lookup"><span data-stu-id="33c4d-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="33c4d-104">使用 GDI + 可以创建图形、 绘制文本，并将图形图像作为对象操作。</span><span class="sxs-lookup"><span data-stu-id="33c4d-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="33c4d-105">GDI + 旨在提供的性能和易用性。</span><span class="sxs-lookup"><span data-stu-id="33c4d-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="33c4d-106">您可以使用 GDI + 呈现 Windows 窗体和控件上的图形图像。</span><span class="sxs-lookup"><span data-stu-id="33c4d-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="33c4d-107">虽然不能使用 GDI + 直接在 Web 窗体上，可以显示通过图像 Web 服务器控件的图形图像。</span><span class="sxs-lookup"><span data-stu-id="33c4d-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="33c4d-108">在本部分中，您将找到引入 GDI + 编程的基础知识的主题。</span><span class="sxs-lookup"><span data-stu-id="33c4d-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="33c4d-109">本节虽非全面的参考，但涵盖有关 <xref:System.Drawing.Graphics>、<xref:System.Drawing.Pen>、<xref:System.Drawing.Brush> 和 <xref:System.Drawing.Color> 对象的信息，并介绍了如何执行绘制形状、绘制文本或显示图像等任务。</span><span class="sxs-lookup"><span data-stu-id="33c4d-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="33c4d-110">有关详细信息，请参阅[GDI + 参考](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)。</span><span class="sxs-lookup"><span data-stu-id="33c4d-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="33c4d-111">若要立即开始，请参阅[图形编程入门](getting-started-with-graphics-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="33c4d-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="33c4d-112">其中包含如何使用代码在 Windows 窗体上绘制线、形状和文本等相关主题。</span><span class="sxs-lookup"><span data-stu-id="33c4d-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33c4d-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="33c4d-113">In This Section</span></span>  
 [<span data-ttu-id="33c4d-114">图形概述</span><span class="sxs-lookup"><span data-stu-id="33c4d-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="33c4d-115">介绍与与图形相关的托管类。</span><span class="sxs-lookup"><span data-stu-id="33c4d-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="33c4d-116">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="33c4d-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="33c4d-117">提供有关托管的 GDI + 类的信息。</span><span class="sxs-lookup"><span data-stu-id="33c4d-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="33c4d-118">使用托管图形类</span><span class="sxs-lookup"><span data-stu-id="33c4d-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="33c4d-119">演示如何为完整的各种任务使用 GDI + 托管类。</span><span class="sxs-lookup"><span data-stu-id="33c4d-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="33c4d-120">参考</span><span class="sxs-lookup"><span data-stu-id="33c4d-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="33c4d-121">提供了对 GDI + 基本图形功能的访问。</span><span class="sxs-lookup"><span data-stu-id="33c4d-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="33c4d-122">提供高级二维和矢量图形功能。</span><span class="sxs-lookup"><span data-stu-id="33c4d-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="33c4d-123">提供高级 GDI + 图像处理功能。</span><span class="sxs-lookup"><span data-stu-id="33c4d-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="33c4d-124">提供高级的 GDI + 排版功能。</span><span class="sxs-lookup"><span data-stu-id="33c4d-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="33c4d-125">此命名空间中的类可用于创建和使用字体集合。</span><span class="sxs-lookup"><span data-stu-id="33c4d-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="33c4d-126">提供打印功能。</span><span class="sxs-lookup"><span data-stu-id="33c4d-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="33c4d-127">相关章节</span><span class="sxs-lookup"><span data-stu-id="33c4d-127">Related Sections</span></span>  
 [<span data-ttu-id="33c4d-128">自定义控件的绘制和呈现</span><span class="sxs-lookup"><span data-stu-id="33c4d-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="33c4d-129">详细介绍如何为绘制控件提供代码。</span><span class="sxs-lookup"><span data-stu-id="33c4d-129">Details how to provide code for painting controls.</span></span>
