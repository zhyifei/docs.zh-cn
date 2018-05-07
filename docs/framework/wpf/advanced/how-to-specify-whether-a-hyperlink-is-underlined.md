---
title: 如何：指定是否为超链接添加下划线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 3d57039d959aa63c031ef467cd2f8398fc3ffd96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>如何：指定是否为超链接添加下划线
<xref:System.Windows.Documents.Hyperlink>对象是允许你在流内容中承载超链接的内联级别流内容元素。 默认情况下，<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象来显示下划线。 <xref:System.Windows.TextDecoration> 对象可以是实例化，大幅降低性能，特别是当你有许多<xref:System.Windows.Documents.Hyperlink>对象。 如果你进行大量使用<xref:System.Windows.Documents.Hyperlink>元素，你可能想要显示下划线，仅当如触发事件时，请考虑<xref:System.Windows.ContentElement.MouseEnter>事件。  
  
 在下面的示例中，"我 MSN"链接的下划线是动态的 — 它只会显示时<xref:System.Windows.ContentElement.MouseEnter>触发事件。  
  
 ![显示 Textdecoration 的超](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
定义与 Textdecoration 的超链接  
  
## <a name="example"></a>示例  
 下面的标记示例演示<xref:System.Windows.Documents.Hyperlink>使用和未使用下划线定义：  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 下面的代码示例演示如何创建为下划线<xref:System.Windows.Documents.Hyperlink>上<xref:System.Windows.ContentElement.MouseEnter>事件，并将其删除上<xref:System.Windows.ContentElement.MouseLeave>事件。  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [优化 WPF 应用程序性能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [创建文本效果](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
