---
title: 如何：指定自定义 Popup 位置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: dc516f0eb1cfcbac6662497eb4019041eefec2a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911204"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="f14ce-102">如何：指定自定义 Popup 位置</span><span class="sxs-lookup"><span data-stu-id="f14ce-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="f14ce-103">此示例演示如何指定的自定义位置<xref:System.Windows.Controls.Primitives.Popup>控制何时<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>。</span><span class="sxs-lookup"><span data-stu-id="f14ce-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f14ce-104">示例</span><span class="sxs-lookup"><span data-stu-id="f14ce-104">Example</span></span>  
 <span data-ttu-id="f14ce-105">当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>，则<xref:System.Windows.Controls.Primitives.Popup>调用的定义的实例<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托。</span><span class="sxs-lookup"><span data-stu-id="f14ce-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="f14ce-106">此委托返回的可能是相对于目标区域的左上的角和的左上的角的点集<xref:System.Windows.Controls.Primitives.Popup>。</span><span class="sxs-lookup"><span data-stu-id="f14ce-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="f14ce-107"><xref:System.Windows.Controls.Primitives.Popup>位置出现在提供最佳的可见性的点。</span><span class="sxs-lookup"><span data-stu-id="f14ce-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="f14ce-108">下面的示例演示如何定义的位置<xref:System.Windows.Controls.Primitives.Popup>通过设置<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>。</span><span class="sxs-lookup"><span data-stu-id="f14ce-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="f14ce-109">它还演示如何创建和分配<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托以定位<xref:System.Windows.Controls.Primitives.Popup>。</span><span class="sxs-lookup"><span data-stu-id="f14ce-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="f14ce-110">回调委托返回两个<xref:System.Windows.Controls.Primitives.CustomPopupPlacement>对象。</span><span class="sxs-lookup"><span data-stu-id="f14ce-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="f14ce-111">如果<xref:System.Windows.Controls.Primitives.Popup>情况下的第一个位置，在屏幕边缘隐藏<xref:System.Windows.Controls.Primitives.Popup>放在第二个位置。</span><span class="sxs-lookup"><span data-stu-id="f14ce-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="f14ce-112">有关完整示例，请参阅[Popup 放置示例](https://go.microsoft.com/fwlink/?LinkID=160032)。</span><span class="sxs-lookup"><span data-stu-id="f14ce-112">For the complete sample, see [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14ce-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f14ce-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="f14ce-114">Popup 概述</span><span class="sxs-lookup"><span data-stu-id="f14ce-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="f14ce-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="f14ce-115">How-to Topics</span></span>](popup-how-to-topics.md)
