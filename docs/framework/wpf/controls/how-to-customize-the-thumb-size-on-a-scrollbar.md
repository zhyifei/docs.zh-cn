---
title: "如何：自定义滚动条上的滚动块大小"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c550aa425eedf4b434e061f05326bf6a6de91f9d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="6f0b8-102">如何：自定义滚动条上的滚动块大小</span><span class="sxs-lookup"><span data-stu-id="6f0b8-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="6f0b8-103">本主题说明如何设置<xref:System.Windows.Controls.Primitives.Thumb>的<xref:System.Windows.Controls.Primitives.ScrollBar>固定的大小以及如何指定的最小大小<xref:System.Windows.Controls.Primitives.Thumb>的<xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="6f0b8-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f0b8-104">示例</span><span class="sxs-lookup"><span data-stu-id="6f0b8-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="6f0b8-105">描述</span><span class="sxs-lookup"><span data-stu-id="6f0b8-105">Description</span></span>  
 <span data-ttu-id="6f0b8-106">下面的示例创建<xref:System.Windows.Controls.Primitives.ScrollBar>具有<xref:System.Windows.Controls.Primitives.Thumb>具有固定大小。</span><span class="sxs-lookup"><span data-stu-id="6f0b8-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="6f0b8-107">该示例设置<xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A>属性<xref:System.Windows.Controls.Primitives.Thumb>到<xref:System.Double.NaN>和设置的高度<xref:System.Windows.Controls.Primitives.Thumb>。</span><span class="sxs-lookup"><span data-stu-id="6f0b8-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="6f0b8-108">若要创建水平<xref:System.Windows.Controls.Primitives.ScrollBar>与<xref:System.Windows.Controls.Primitives.Thumb>具有固定的宽度，则设置的宽度<xref:System.Windows.Controls.Primitives.Thumb>。</span><span class="sxs-lookup"><span data-stu-id="6f0b8-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="6f0b8-109">代码</span><span class="sxs-lookup"><span data-stu-id="6f0b8-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="6f0b8-110">描述</span><span class="sxs-lookup"><span data-stu-id="6f0b8-110">Description</span></span>  
 <span data-ttu-id="6f0b8-111">下面的示例创建<xref:System.Windows.Controls.Primitives.ScrollBar>具有<xref:System.Windows.Controls.Primitives.Thumb>与最小大小。</span><span class="sxs-lookup"><span data-stu-id="6f0b8-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="6f0b8-112">该示例设置的值<xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="6f0b8-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="6f0b8-113">若要创建水平<xref:System.Windows.Controls.Primitives.ScrollBar>与<xref:System.Windows.Controls.Primitives.Thumb>具有最小宽度，设置<xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="6f0b8-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="6f0b8-114">代码</span><span class="sxs-lookup"><span data-stu-id="6f0b8-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6f0b8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f0b8-115">See Also</span></span>  
 [<span data-ttu-id="6f0b8-116">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="6f0b8-116">ScrollBar Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
