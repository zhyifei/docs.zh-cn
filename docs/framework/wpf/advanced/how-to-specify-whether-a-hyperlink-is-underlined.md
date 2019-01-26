---
title: 如何：指定是否为超链接添加下划线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 3199bce25d49bb471fe21735ebb919bbb7f5132c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576949"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>如何：指定是否为超链接添加下划线
<xref:System.Windows.Documents.Hyperlink>对象是允许您承载流内容中的超链接的内联级流内容元素。 默认情况下<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象来显示下划线。 <xref:System.Windows.TextDecoration> 对象可以是占用实例化，特别是当有许多<xref:System.Windows.Documents.Hyperlink>对象。 如果充分利用了<xref:System.Windows.Documents.Hyperlink>元素，您可能会考虑显示下划线，仅当触发事件，如<xref:System.Windows.ContentElement.MouseEnter>事件。  
  
 在以下示例中，"我的 MSN"链接的下划线是动态的 — 它时，才显示<xref:System.Windows.ContentElement.MouseEnter>触发事件。  
  
 ![显示 TextDecorations 的超](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
定义与 TextDecorations 的超链接  
  
## <a name="example"></a>示例  
 以下标记示例演示<xref:System.Windows.Documents.Hyperlink>使用和不使用下划线定义：  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 下面的代码示例演示如何创建为下划线<xref:System.Windows.Documents.Hyperlink>上<xref:System.Windows.ContentElement.MouseEnter>事件，并将其上删除<xref:System.Windows.ContentElement.MouseLeave>事件。  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [优化 WPF 应用程序性能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
- [创建文本效果](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
