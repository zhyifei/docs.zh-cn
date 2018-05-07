---
title: 如何：使用 ScrollViewer 创建 Expander
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 6c014d4f6a12bfb58c2ae68f580f632c9478c82f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>如何：使用 ScrollViewer 创建 Expander
此示例演示如何创建<xref:System.Windows.Controls.Expander>包含复杂内容，如图像和文本的控件。 该示例还包含的内容<xref:System.Windows.Controls.Expander>中<xref:System.Windows.Controls.ScrollViewer>控件。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建<xref:System.Windows.Controls.Expander>。 该示例使用<xref:System.Windows.Controls.Primitives.BulletDecorator>控件，它包含的图像和文本，为了定义<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>。 A<xref:System.Windows.Controls.ScrollViewer>控件提供了滚动扩展的内容的方法。  
  
 请注意，该示例将<xref:System.Windows.FrameworkElement.Height%2A>属性<xref:System.Windows.Controls.ScrollViewer>而不是对内容。 如果<xref:System.Windows.FrameworkElement.Height%2A>于内容而设置<xref:System.Windows.Controls.ScrollViewer>不允许用户滚动内容。 <xref:System.Windows.FrameworkElement.Width%2A>上设置属性<xref:System.Windows.Controls.Expander>控件和此设置也适用于<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>和扩展的内容。  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Expander>  
 [扩展器概述](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
