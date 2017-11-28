---
title: "如何：更改光标类型"
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
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41cd8c9cd647c7efbc4e6cf13517ed638245e51c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-cursor-type"></a>如何：更改光标类型
此示例演示如何更改<xref:System.Windows.Input.Cursor>鼠标指针的特定元素和应用程序。  
  
 此示例组成[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。  
  
## <a name="example"></a>示例  
 创建用户界面，其中包括<xref:System.Windows.Controls.ComboBox>选择所需<xref:System.Windows.Input.Cursor>，一对<xref:System.Windows.Controls.RadioButton>对象以确定是否游标更改适用于仅包含单个元素或适用于整个应用程序，和一个<xref:System.Windows.Controls.Border>这是新光标将应用于的元素。  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 下面的代码隐藏创建<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>中更改的游标类型时调用事件处理程序<xref:System.Windows.Controls.ComboBox>。  Switch 语句的筛选器上的游标名称和集<xref:System.Windows.FrameworkElement.Cursor%2A>属性<xref:System.Windows.Controls.Border>名*DisplayArea*。  
  
 如果光标更改设置为"整个应用程序"，<xref:System.Windows.Input.Mouse.OverrideCursor%2A>属性设置为<xref:System.Windows.FrameworkElement.Cursor%2A>属性<xref:System.Windows.Controls.Border>控件。  这将强制更改对整个应用程序的光标。  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>另请参阅  
 [输入概述](../../../../docs/framework/wpf/advanced/input-overview.md)
