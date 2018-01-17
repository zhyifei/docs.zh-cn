---
title: "如何：使用 IScrollInfo 接口来滚动内容"
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
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae6d9439ad76258105d615960bd05ecf458eb613
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>如何：使用 IScrollInfo 接口来滚动内容
此示例演示如何通过使用滚动内容<xref:System.Windows.Controls.Primitives.IScrollInfo>接口。  
  
## <a name="example"></a>示例  
 下面的示例演示的功能<xref:System.Windows.Controls.Primitives.IScrollInfo>接口。 该示例创建<xref:System.Windows.Controls.StackPanel>中的元素[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]嵌套在父<xref:System.Windows.Controls.ScrollViewer>。 子元素<xref:System.Windows.Controls.StackPanel>可通过使用由定义的方法逻辑上滚动<xref:System.Windows.Controls.Primitives.IScrollInfo>接口和强制转换为的实例<xref:System.Windows.Controls.StackPanel>(`sp1`) 在代码中。  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 每个<xref:System.Windows.Controls.Button>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件触发控制滚动行为中的关联自定义方法<xref:System.Windows.Controls.StackPanel>。 下面的示例演示如何使用<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A>和<xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>方法; 它还大致演示了如何使用所有定位方法的<xref:System.Windows.Controls.Primitives.IScrollInfo>类定义。  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 <xref:System.Windows.Controls.StackPanel>  
 [ScrollViewer 概述](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)
