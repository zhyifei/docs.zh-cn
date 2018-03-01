---
title: "如何：确保 GridSplitter 可见"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b7587a093b2b43856a05693bb785a0465211782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="b5b8d-102">如何：确保 GridSplitter 可见</span><span class="sxs-lookup"><span data-stu-id="b5b8d-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="b5b8d-103">此示例演示如何确保<xref:System.Windows.Controls.GridSplitter>通过中的其他控件未隐藏控件<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5b8d-104">示例</span><span class="sxs-lookup"><span data-stu-id="b5b8d-104">Example</span></span>  
 <span data-ttu-id="b5b8d-105"><xref:System.Windows.Controls.Panel.Children%2A>的<xref:System.Windows.Controls.Grid>中标记或代码中定义的顺序呈现控件。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="b5b8d-106"><xref:System.Windows.Controls.GridSplitter>如果你没有定义它们中的最后一个元素，可以由其他控件隐藏控件<xref:System.Windows.Controls.Panel.Children%2A>集合或如果你为提供其他控制更高<xref:System.Windows.Controls.Panel.ZIndexProperty>。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="b5b8d-107">若要防止隐藏<xref:System.Windows.Controls.GridSplitter>控件，执行下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="b5b8d-108">请确保<xref:System.Windows.Controls.GridSplitter>控件是最后<xref:System.Windows.Controls.Panel.Children%2A>添加到<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="b5b8d-109">下面的示例演示<xref:System.Windows.Controls.GridSplitter>中的最后一个元素<xref:System.Windows.Controls.Panel.Children%2A>集合<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="b5b8d-110">设置<xref:System.Windows.Controls.Panel.ZIndexProperty>上<xref:System.Windows.Controls.GridSplitter>得高于的控件，否则将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="b5b8d-111">以下示例给出了<xref:System.Windows.Controls.GridSplitter>控制更高<xref:System.Windows.Controls.Panel.ZIndexProperty>比<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="b5b8d-112">否则将隐藏在控件上设置边距<xref:System.Windows.Controls.GridSplitter>以便<xref:System.Windows.Controls.GridSplitter>公开。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="b5b8d-113">下面的示例设置边距上的控件，否则将覆盖和隐藏<xref:System.Windows.Controls.GridSplitter>。</span><span class="sxs-lookup"><span data-stu-id="b5b8d-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="b5b8d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5b8d-114">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="b5b8d-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="b5b8d-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
