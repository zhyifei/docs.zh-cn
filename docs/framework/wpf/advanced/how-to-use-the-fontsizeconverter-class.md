---
title: "如何：使用 FontSizeConverter 类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe6988f21c2e40c65a7e8acd48727ab48bd58e05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>如何：使用 FontSizeConverter 类
## <a name="example"></a>示例  
 此示例演示如何创建的实例<xref:System.Windows.FontSizeConverter>并使用它来将字体大小更改。  
  
 该示例定义的自定义的方法调用`changeSize`，用于将转换的内容<xref:System.Windows.Controls.ListBoxItem>，如在单独定义[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件、 实例<xref:System.Double>，然后再转换<xref:System.String>。 此方法将传递<xref:System.Windows.Controls.ListBoxItem>到<xref:System.Windows.FontSizeConverter>对象，后者将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>到实例<xref:System.Double>。 此值然后传递的值作为<xref:System.Windows.Controls.TextBlock.FontSize%2A>属性<xref:System.Windows.Controls.TextBlock>元素。  
  
 此示例还定义称为的第二个自定义方法`changeFamily`。 此方法将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>到<xref:System.String>，然后将传递到该值<xref:System.Windows.Controls.TextBlock.FontFamily%2A>属性<xref:System.Windows.Controls.TextBlock>元素。  
  
 此示例不运行。  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.FontSizeConverter>
