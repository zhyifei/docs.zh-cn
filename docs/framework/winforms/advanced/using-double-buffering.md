---
title: 使用双缓冲
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: ac6c9b7f2cc1fea86a75eaaf4a2dde1ea60e4f40
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716267"
---
# <a name="using-double-buffering"></a><span data-ttu-id="0f282-102">使用双缓冲</span><span class="sxs-lookup"><span data-stu-id="0f282-102">Using Double Buffering</span></span>
<span data-ttu-id="0f282-103">可以使用双缓冲的图形以包含复杂画图操作在应用程序中减少闪烁。</span><span class="sxs-lookup"><span data-stu-id="0f282-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="0f282-104">.NET Framework 包含的双缓冲的内置支持，也可以管理并手动呈现图形。</span><span class="sxs-lookup"><span data-stu-id="0f282-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f282-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="0f282-105">In This Section</span></span>  
 [<span data-ttu-id="0f282-106">双缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="0f282-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="0f282-107">引入了双缓冲的概念，并概述了.NET Framework 支持。</span><span class="sxs-lookup"><span data-stu-id="0f282-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="0f282-108">如何：减少对窗体和控件使用双缓冲图形闪烁</span><span class="sxs-lookup"><span data-stu-id="0f282-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="0f282-109">演示如何使用默认双缓冲支持.NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="0f282-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="0f282-110">如何：手动管理缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="0f282-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="0f282-111">演示如何管理应用程序中的双缓冲。</span><span class="sxs-lookup"><span data-stu-id="0f282-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="0f282-112">如何：手动呈现缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="0f282-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="0f282-113">演示如何呈现双缓冲的图形。</span><span class="sxs-lookup"><span data-stu-id="0f282-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0f282-114">参考</span><span class="sxs-lookup"><span data-stu-id="0f282-114">Reference</span></span>  
 <span data-ttu-id="0f282-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="0f282-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="0f282-116">启用双缓冲的控制方法。</span><span class="sxs-lookup"><span data-stu-id="0f282-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="0f282-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="0f282-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="0f282-118">提供用于创建图形缓冲区的方法。</span><span class="sxs-lookup"><span data-stu-id="0f282-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="0f282-119">提供对缓冲的图形上下文为应用程序域的访问。</span><span class="sxs-lookup"><span data-stu-id="0f282-119">Provides access to the buffered graphics context for a application domain.</span></span>
