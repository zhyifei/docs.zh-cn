---
title: "如何：使用焦点事件更改元素的颜色"
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
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64b1b788ddebe77704a7d34f31ad82b10da34a5a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>如何：使用焦点事件更改元素的颜色
此示例演示如何获取和使用失去焦点时更改元素的颜色<xref:System.Windows.UIElement.GotFocus>和<xref:System.Windows.UIElement.LostFocus>事件。  
  
 此示例组成[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。  
  
## <a name="example"></a>示例  
 以下[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]创建用户界面，包含两个界面<xref:System.Windows.Controls.Button>对象，并将事件处理程序附加<xref:System.Windows.UIElement.GotFocus>和<xref:System.Windows.UIElement.LostFocus>事件<xref:System.Windows.Controls.Button>对象。  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 下面的代码隐藏创建<xref:System.Windows.UIElement.GotFocus>和<xref:System.Windows.UIElement.LostFocus>事件处理程序。  当<xref:System.Windows.Controls.Button>提升键盘焦点，<xref:System.Windows.Controls.Control.Background%2A>的<xref:System.Windows.Controls.Button>将变为红色。  当<xref:System.Windows.Controls.Button>失去键盘焦点时，<xref:System.Windows.Controls.Control.Background%2A>的<xref:System.Windows.Controls.Button>将变回为空白。  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>另请参阅  
 [输入概述](../../../../docs/framework/wpf/advanced/input-overview.md)
