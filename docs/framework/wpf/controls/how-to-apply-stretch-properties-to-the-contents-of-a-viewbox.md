---
title: "如何：向 Viewbox 的内容应用 Stretch 属性"
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
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93e61783f70ee501266a68785350ee0810dff255
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a>如何：向 Viewbox 的内容应用 Stretch 属性
## <a name="example"></a>示例  
 此示例演示如何更改的值<xref:System.Windows.Controls.Viewbox.StretchDirection%2A>和<xref:System.Windows.Controls.Viewbox.Stretch%2A>属性<xref:System.Windows.Controls.Viewbox>。  
  
 第一个示例使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定义<xref:System.Windows.Controls.Viewbox>元素。 它将分配<xref:System.Windows.FrameworkElement.MaxWidth%2A>和<xref:System.Windows.FrameworkElement.MaxHeight%2A>的 400。 示例嵌套<xref:System.Windows.Controls.Image>中的元素<xref:System.Windows.Controls.Viewbox>。 <xref:System.Windows.Controls.Button>对应的属性值的元素<xref:System.Windows.Controls.Viewbox.Stretch%2A>和<xref:System.Windows.Controls.StretchDirection>枚举操作的嵌套的拉伸行为<xref:System.Windows.Controls.Image>。  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 下面的代码隐藏文件句柄<xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件的上一个[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例定义。  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Viewbox>  
 <xref:System.Windows.Media.Stretch>  
 <xref:System.Windows.Controls.StretchDirection>
