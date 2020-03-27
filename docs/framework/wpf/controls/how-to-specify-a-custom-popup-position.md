---
title: 如何：指定自定义 Popup 位置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: ea8d73c51dd018608b95104f00bf341ff434225c
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344955"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="d18e1-102">如何：指定自定义 Popup 位置</span><span class="sxs-lookup"><span data-stu-id="d18e1-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="d18e1-103">此示例演示如何在<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>时为控件指定自定义位置。</span><span class="sxs-lookup"><span data-stu-id="d18e1-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d18e1-104">示例</span><span class="sxs-lookup"><span data-stu-id="d18e1-104">Example</span></span>  
 <span data-ttu-id="d18e1-105">当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>时，<xref:System.Windows.Controls.Primitives.Popup>调用<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托的已定义实例。</span><span class="sxs-lookup"><span data-stu-id="d18e1-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="d18e1-106">此委托返回一组相对于目标区域左上角和 左<xref:System.Windows.Controls.Primitives.Popup>上角的可能点。</span><span class="sxs-lookup"><span data-stu-id="d18e1-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="d18e1-107">放置<xref:System.Windows.Controls.Primitives.Popup>发生在提供最佳可见性的点。</span><span class="sxs-lookup"><span data-stu-id="d18e1-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="d18e1-108">下面的示例演示如何通过将<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>来定义 的位置。</span><span class="sxs-lookup"><span data-stu-id="d18e1-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="d18e1-109">它还演示如何创建和分配<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托，以便定位 。 <xref:System.Windows.Controls.Primitives.Popup></span><span class="sxs-lookup"><span data-stu-id="d18e1-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="d18e1-110">回调委托返回两<xref:System.Windows.Controls.Primitives.CustomPopupPlacement>个对象。</span><span class="sxs-lookup"><span data-stu-id="d18e1-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="d18e1-111"><xref:System.Windows.Controls.Primitives.Popup>如果在第一个位置由屏幕边缘隐藏，<xref:System.Windows.Controls.Primitives.Popup>则 将放置在第二个位置。</span><span class="sxs-lookup"><span data-stu-id="d18e1-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="d18e1-112">有关完整示例，请参阅[弹出放置示例](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)。</span><span class="sxs-lookup"><span data-stu-id="d18e1-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d18e1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d18e1-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="d18e1-114">Popup 概述</span><span class="sxs-lookup"><span data-stu-id="d18e1-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="d18e1-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="d18e1-115">How-to Topics</span></span>](popup-how-to-topics.md)
