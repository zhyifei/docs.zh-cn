---
title: "如何：以编程方式更改 TextWrapping 属性"
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
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 74ddcf55c8918602ecac866913f2007da143f443
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a>如何：以编程方式更改 TextWrapping 属性
## <a name="example"></a>示例  
 下面的代码示例演示如何更改的值<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>属性以编程方式。  
  
 三个<xref:System.Windows.Controls.Button>元素放在<xref:System.Windows.Controls.StackPanel>中的元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 每个<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件<xref:System.Windows.Controls.Button>对应与一个事件处理程序代码中。 事件处理程序使用相同的名称作为<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>值它们将应用于`txt2`时单击该按钮。 此外中的文本`txt1`(<xref:System.Windows.Controls.TextBlock>中不会显示[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) 更新以反映在属性中的更改。  
  
 [!code-xaml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>  
 <xref:System.Windows.TextWrapping>
