---
title: "TextBlock 概述"
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
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 404f5677bca0df45d4f7dbf689a297499b36bbab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="textblock-overview"></a>TextBlock 概述
<xref:System.Windows.Controls.TextBlock>控件提供灵活的文本支持[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。 该元素主要面向不需要多个文本段落的基本 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 方案。 它支持多个属性可以启用精确地控制演示文稿，例如<xref:System.Windows.Controls.TextBlock.FontFamily%2A>， <xref:System.Windows.Controls.TextBlock.FontSize%2A>， <xref:System.Windows.Controls.TextBlock.FontWeight%2A>， <xref:System.Windows.Controls.TextBlock.TextEffects%2A>，和<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>。 可以使用添加文本内容<xref:System.Windows.Controls.TextBlock.Text%2A>属性。 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中使用时，开始标记和结束标记之间的内容隐式添加为元素的文本。  
  
 A<xref:System.Windows.Controls.TextBlock>可以非常轻松地实例化元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
 [!code-xaml[TextBlockSnip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 同样，使用情况的<xref:System.Windows.Controls.TextBlock>在代码中的元素是相对简单。  
  
 [!code-csharp[TextBlockSnip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Label>
