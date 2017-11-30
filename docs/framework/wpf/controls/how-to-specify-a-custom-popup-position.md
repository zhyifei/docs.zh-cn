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
ms.openlocfilehash: 0ab9baca1103adf8de96204bdb1b3353a5456b94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-a-custom-popup-position"></a>如何：指定自定义 Popup 位置
此示例演示如何指定一个自定义职位<xref:System.Windows.Controls.Primitives.Popup>控制<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>。  
  
## <a name="example"></a>示例  
 当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>、<xref:System.Windows.Controls.Primitives.Popup>调用的定义的实例<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托。 此委托返回一组可能是相对于目标区域的左上的角和的左上的角的点<xref:System.Windows.Controls.Primitives.Popup>。 <xref:System.Windows.Controls.Primitives.Popup>放置在提供最佳的可见性的点出现。  
  
 下面的示例演示如何定义的位置<xref:System.Windows.Controls.Primitives.Popup>通过设置<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>。 它还演示如何创建并分配<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>委托以定位<xref:System.Windows.Controls.Primitives.Popup>。  在回调委托返回两个<xref:System.Windows.Controls.Primitives.CustomPopupPlacement>对象。  如果<xref:System.Windows.Controls.Primitives.Popup>隐藏的第一个位置，在屏幕边缘<xref:System.Windows.Controls.Primitives.Popup>置于第二个位置。  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 有关完整的示例，请参阅[弹出窗口放置示例](http://go.microsoft.com/fwlink/?LinkID=160032)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Popup 概述](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
