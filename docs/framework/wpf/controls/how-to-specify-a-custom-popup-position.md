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
# <a name="how-to-specify-a-custom-popup-position"></a>如何：指定自定义 Popup 位置
此示例演示如何在<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>时为控件指定自定义位置。  
  
## <a name="example"></a>示例  
 当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>时，<xref:System.Windows.Controls.Primitives.Popup>调用<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托的已定义实例。 此委托返回一组相对于目标区域左上角和 左<xref:System.Windows.Controls.Primitives.Popup>上角的可能点。 放置<xref:System.Windows.Controls.Primitives.Popup>发生在提供最佳可见性的点。  
  
 下面的示例演示如何通过将<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>来定义 的位置。 它还演示如何创建和分配<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托，以便定位 。 <xref:System.Windows.Controls.Primitives.Popup>  回调委托返回两<xref:System.Windows.Controls.Primitives.CustomPopupPlacement>个对象。  <xref:System.Windows.Controls.Primitives.Popup>如果在第一个位置由屏幕边缘隐藏，<xref:System.Windows.Controls.Primitives.Popup>则 将放置在第二个位置。  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 有关完整示例，请参阅[弹出放置示例](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Primitives.Popup>
- [Popup 概述](popup-overview.md)
- [帮助主题](popup-how-to-topics.md)
