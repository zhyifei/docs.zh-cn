---
title: 使用双缓冲
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 9b09210eba0ac3a141219a7cdbff15f22c6ed003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523905"
---
# <a name="using-double-buffering"></a><span data-ttu-id="53991-102">使用双缓冲</span><span class="sxs-lookup"><span data-stu-id="53991-102">Using Double Buffering</span></span>
<span data-ttu-id="53991-103">可以使用双缓冲图形来减少闪烁包含复杂的绘制操作的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="53991-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="53991-104">.NET Framework 包含双缓冲的内置支持，或者你可以管理并手动呈现图形。</span><span class="sxs-lookup"><span data-stu-id="53991-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="53991-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="53991-105">In This Section</span></span>  
 [<span data-ttu-id="53991-106">双缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="53991-106">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 <span data-ttu-id="53991-107">引入了双缓冲的概念和概述了.NET Framework 支持。</span><span class="sxs-lookup"><span data-stu-id="53991-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="53991-108">如何：通过对窗体和控件使用双缓冲来减少图形闪烁</span><span class="sxs-lookup"><span data-stu-id="53991-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="53991-109">演示如何使用双缓冲支持.NET Framework 中的默认值。</span><span class="sxs-lookup"><span data-stu-id="53991-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="53991-110">如何：手动管理缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="53991-110">How to: Manually Manage Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="53991-111">演示如何管理应用程序中的双缓冲。</span><span class="sxs-lookup"><span data-stu-id="53991-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="53991-112">如何：手动呈现缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="53991-112">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="53991-113">演示如何呈现双缓冲图形。</span><span class="sxs-lookup"><span data-stu-id="53991-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="53991-114">参考</span><span class="sxs-lookup"><span data-stu-id="53991-114">Reference</span></span>  
 <span data-ttu-id="53991-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="53991-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="53991-116">启用双缓冲的控制方法。</span><span class="sxs-lookup"><span data-stu-id="53991-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="53991-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="53991-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="53991-118">提供用于创建图形缓冲区的方法。</span><span class="sxs-lookup"><span data-stu-id="53991-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="53991-119">您可以访问应用程序域的缓冲的图形上下文。</span><span class="sxs-lookup"><span data-stu-id="53991-119">Provides access to the buffered graphics context for a application domain.</span></span>
