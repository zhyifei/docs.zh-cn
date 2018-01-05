---
title: "如何：指定自定义 Popup 位置"
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
helpviewer_keywords: Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae10153f31b79a220b84cae7a6525eca0ce0bd9c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="17cf3-102">如何：指定自定义 Popup 位置</span><span class="sxs-lookup"><span data-stu-id="17cf3-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="17cf3-103">此示例演示如何指定一个自定义职位<xref:System.Windows.Controls.Primitives.Popup>控制<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>。</span><span class="sxs-lookup"><span data-stu-id="17cf3-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17cf3-104">示例</span><span class="sxs-lookup"><span data-stu-id="17cf3-104">Example</span></span>  
 <span data-ttu-id="17cf3-105">当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>、<xref:System.Windows.Controls.Primitives.Popup>调用的定义的实例<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托。</span><span class="sxs-lookup"><span data-stu-id="17cf3-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="17cf3-106">此委托返回一组可能是相对于目标区域的左上的角和的左上的角的点<xref:System.Windows.Controls.Primitives.Popup>。</span><span class="sxs-lookup"><span data-stu-id="17cf3-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="17cf3-107"><xref:System.Windows.Controls.Primitives.Popup>放置在提供最佳的可见性的点出现。</span><span class="sxs-lookup"><span data-stu-id="17cf3-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="17cf3-108">下面的示例演示如何定义的位置<xref:System.Windows.Controls.Primitives.Popup>通过设置<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>。</span><span class="sxs-lookup"><span data-stu-id="17cf3-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="17cf3-109">它还演示如何创建并分配<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托以定位<xref:System.Windows.Controls.Primitives.Popup>。</span><span class="sxs-lookup"><span data-stu-id="17cf3-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="17cf3-110">在回调委托返回两个<xref:System.Windows.Controls.Primitives.CustomPopupPlacement>对象。</span><span class="sxs-lookup"><span data-stu-id="17cf3-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="17cf3-111">如果<xref:System.Windows.Controls.Primitives.Popup>隐藏的第一个位置，在屏幕边缘<xref:System.Windows.Controls.Primitives.Popup>置于第二个位置。</span><span class="sxs-lookup"><span data-stu-id="17cf3-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="17cf3-112">有关完整的示例，请参阅[弹出窗口放置示例](http://go.microsoft.com/fwlink/?LinkID=160032)。</span><span class="sxs-lookup"><span data-stu-id="17cf3-112">For the complete sample, see [Popup Placement Sample](http://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17cf3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="17cf3-113">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="17cf3-114">Popup 概述</span><span class="sxs-lookup"><span data-stu-id="17cf3-114">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [<span data-ttu-id="17cf3-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="17cf3-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
