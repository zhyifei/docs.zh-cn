---
title: "如何：使对象跟随鼠标指针移动"
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
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1991d2a4b43c679fe7e30f633742e01e281e19b3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>如何：使对象跟随鼠标指针移动
此示例演示如何更改对象的尺寸，当鼠标指针在屏幕上移动。  
  
 该示例包含[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]创建的文件[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]和创建事件处理程序的代码隐藏文件。  
  
## <a name="example"></a>示例  
 以下[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]创建[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，其中包括<xref:System.Windows.Shapes.Ellipse>内<xref:System.Windows.Controls.StackPanel>，并将附加的事件处理程序<xref:System.Windows.UIElement.MouseMove>事件。  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 下面的代码隐藏创建<xref:System.Windows.UIElement.MouseMove>事件处理程序。  当鼠标指针移动，高度和宽度<xref:System.Windows.Shapes.Ellipse>增加和减少。  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>另请参阅  
 [输入概述](../../../../docs/framework/wpf/advanced/input-overview.md)
