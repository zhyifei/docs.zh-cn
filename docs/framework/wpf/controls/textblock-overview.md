---
title: TextBlock 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: ce7da2b9c9c8e2a3a24d3acf18396ca447ac3f27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791009"
---
# <a name="textblock-overview"></a>TextBlock 概述
<xref:System.Windows.Controls.TextBlock>控件提供了灵活的文本支持[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。 该元素主要面向不需要多个文本段落的基本 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 方案。 它支持多个属性启用精确控制呈现，例如<xref:System.Windows.Controls.TextBlock.FontFamily%2A>， <xref:System.Windows.Controls.TextBlock.FontSize%2A>， <xref:System.Windows.Controls.TextBlock.FontWeight%2A>， <xref:System.Windows.Controls.TextBlock.TextEffects%2A>，和<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>。 可以使用添加文本内容<xref:System.Windows.Controls.TextBlock.Text%2A>属性。 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中使用时，开始标记和结束标记之间的内容隐式添加为元素的文本。  
  
 一个<xref:System.Windows.Controls.TextBlock>可以非常轻松地实例化元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 同样，使用情况的<xref:System.Windows.Controls.TextBlock>在代码中的元素是相对简单。  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Label>
