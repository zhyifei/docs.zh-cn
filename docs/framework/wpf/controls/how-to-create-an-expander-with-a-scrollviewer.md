---
title: 如何：使用 ScrollViewer 创建 Expander
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 8d21c7ec0172dca23f218a0d710c3976872f162c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681958"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>如何：使用 ScrollViewer 创建 Expander
此示例演示如何创建<xref:System.Windows.Controls.Expander>包含复杂内容，例如图像和文本的控件。 该示例还包含的内容<xref:System.Windows.Controls.Expander>在<xref:System.Windows.Controls.ScrollViewer>控件。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建<xref:System.Windows.Controls.Expander>。 该示例使用<xref:System.Windows.Controls.Primitives.BulletDecorator>控件，它包含图像和文本，为了定义<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>。 一个<xref:System.Windows.Controls.ScrollViewer>控件提供了用于滚动扩展的内容的方法。  
  
 请注意，该示例设置<xref:System.Windows.FrameworkElement.Height%2A>属性上的<xref:System.Windows.Controls.ScrollViewer>而不是对的内容。 如果<xref:System.Windows.FrameworkElement.Height%2A>内容，设置<xref:System.Windows.Controls.ScrollViewer>不允许用户滚动内容。 <xref:System.Windows.FrameworkElement.Width%2A>上设置属性<xref:System.Windows.Controls.Expander>控件，此设置适用于<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>和扩展的内容。  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Controls.Expander>
- [扩展器概述](../../../../docs/framework/wpf/controls/expander-overview.md)
- [帮助主题](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
