---
title: 如何：查找由 DataTemplate 生成的元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: 3b222880aa4eda32502e3dcece2fa5c0b57b7a51
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646437"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>如何：查找由 DataTemplate 生成的元素
此示例演示如何查找由 生成的元素<xref:System.Windows.DataTemplate>。  
  
## <a name="example"></a>示例  
 在此示例中，有绑定到某些<xref:System.Windows.Controls.ListBox>XML 数据的 a：  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 使用<xref:System.Windows.Controls.ListBox>以下内容<xref:System.Windows.DataTemplate>：  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 如果要检索<xref:System.Windows.Controls.TextBlock>由<xref:System.Windows.DataTemplate>某一元素<xref:System.Windows.Controls.ListBoxItem><xref:System.Windows.Controls.ListBoxItem>生成的元素，则需要获取 ， 找到<xref:System.Windows.Controls.ContentPresenter>内部<xref:System.Windows.Controls.ListBoxItem>的元素，然后调用<xref:System.Windows.FrameworkTemplate.FindName%2A><xref:System.Windows.DataTemplate>上设置 的元素 。 <xref:System.Windows.Controls.ContentPresenter> 下面的示例演示如何执行这些步骤。 出于演示目的，此示例创建一个显示<xref:System.Windows.DataTemplate>生成的文本块的文本内容的消息框。  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 以下是 的实现`FindVisualChild`，<xref:System.Windows.Media.VisualTreeHelper>它使用这些方法：  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>另请参阅

- [如何：查找由 ControlTemplate 生成的元素](../controls/how-to-find-controltemplate-generated-elements.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [操作指南主题](data-binding-how-to-topics.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [WPF XAML 名称范围](../advanced/wpf-xaml-namescopes.md)
- [WPF 中的树](../advanced/trees-in-wpf.md)
