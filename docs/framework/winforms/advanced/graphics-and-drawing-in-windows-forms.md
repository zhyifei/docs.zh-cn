---
title: 图形和绘图
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 10ad18d38c84f6e447601ab6c8bf1a953dabb7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746401"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="4117a-102">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="4117a-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="4117a-103">公共语言运行时使用名为 GDI + 的 Windows 图形设备接口（GDI）的高级实现。</span><span class="sxs-lookup"><span data-stu-id="4117a-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="4117a-104">利用 GDI +，你可以创建图形、绘制文本以及将图形图像作为对象进行操作。</span><span class="sxs-lookup"><span data-stu-id="4117a-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="4117a-105">GDI + 旨在提供性能和易用性。</span><span class="sxs-lookup"><span data-stu-id="4117a-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="4117a-106">可以使用 GDI + 在 Windows 窗体和控件上呈现图形图像。</span><span class="sxs-lookup"><span data-stu-id="4117a-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="4117a-107">尽管不能直接在 Web 窗体上使用 GDI +，但你可以通过图像 Web 服务器控件显示图形图像。</span><span class="sxs-lookup"><span data-stu-id="4117a-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="4117a-108">在本部分中，你将找到介绍 GDI + 编程基础知识的主题。</span><span class="sxs-lookup"><span data-stu-id="4117a-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="4117a-109">포괄적인 참조는 아니지만 이 섹션은 <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Color> 개체에 대한 정보를 포함하며 도형 그리기, 텍스트 그리기 또는 이미지 표시와 같은 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4117a-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="4117a-110">有关详细信息，请参阅[Gdi + Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)。</span><span class="sxs-lookup"><span data-stu-id="4117a-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="4117a-111">바로 시작하려면 [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4117a-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="4117a-112">Windows Forms에서 코드를 사용하여 선, 도형, 텍스트 등을 그리는 방법에 대한 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4117a-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4117a-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4117a-113">In This Section</span></span>  
 [<span data-ttu-id="4117a-114">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="4117a-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="4117a-115">그래픽 관련 관리되는 클래스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="4117a-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="4117a-116">GDI + 관리 코드 정보</span><span class="sxs-lookup"><span data-stu-id="4117a-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="4117a-117">提供有关托管 GDI + 类的信息。</span><span class="sxs-lookup"><span data-stu-id="4117a-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="4117a-118">관리되는 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="4117a-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="4117a-119">演示如何使用 GDI + 托管类完成各种任务。</span><span class="sxs-lookup"><span data-stu-id="4117a-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4117a-120">참조</span><span class="sxs-lookup"><span data-stu-id="4117a-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="4117a-121">提供对 GDI + 基本图形功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4117a-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="4117a-122">고급 2D 및 벡터 그래픽 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4117a-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="4117a-123">提供高级 GDI + 图像处理功能。</span><span class="sxs-lookup"><span data-stu-id="4117a-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="4117a-124">提供高级 GDI + 版式功能。</span><span class="sxs-lookup"><span data-stu-id="4117a-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="4117a-125">이 네임스페이스의 클래스를 통해 글꼴 컬렉션을 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4117a-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="4117a-126">인쇄 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4117a-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4117a-127">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="4117a-127">Related Sections</span></span>  
 [<span data-ttu-id="4117a-128">사용자 지정 컨트롤 그리기 및 렌더링</span><span class="sxs-lookup"><span data-stu-id="4117a-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="4117a-129">컨트롤을 그리기 위한 코드를 제공하는 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4117a-129">Details how to provide code for painting controls.</span></span>
