---
title: 如何：查找由 ControlTemplate 生成的元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 232ee7d2859059591c9beff753f45781598a8127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460705"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>如何：查找由 ControlTemplate 生成的元素
此示例演示如何查找 <xref:System.Windows.Controls.ControlTemplate>生成的元素。  
  
## <a name="example"></a>示例  
 下面的示例演示了一个样式，该样式创建 <xref:System.Windows.Controls.Button> 类的简单 <xref:System.Windows.Controls.ControlTemplate>：  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 若要在应用模板后查找模板中的元素，可以调用 <xref:System.Windows.Controls.Control.Template%2A>的 <xref:System.Windows.FrameworkTemplate.FindName%2A> 方法。 下面的示例创建一个消息框，该消息框显示控件模板内 <xref:System.Windows.Controls.Grid> 的实际宽度值：  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>请参阅

- [查找由 DataTemplate 生成的元素](../data/how-to-find-datatemplate-generated-elements.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [WPF XAML 名称范围](../advanced/wpf-xaml-namescopes.md)
- [WPF 中的树](../advanced/trees-in-wpf.md)
