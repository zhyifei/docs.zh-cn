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
ms.openlocfilehash: 3d3032326a0cedc01b4a7ec8e6546044353d6b4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-controltemplate-generated-elements"></a>如何：查找由 ControlTemplate 生成的元素
此示例演示如何查找元素所生成的<xref:System.Windows.Controls.ControlTemplate>。  
  
## <a name="example"></a>示例  
 下面的示例演示创建一个简单样式<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Button>类：  
  
 [!code-xaml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 若在应用该模板后，需要查找模板内的元素，可以调用该<xref:System.Windows.FrameworkTemplate.FindName%2A>的<xref:System.Windows.Controls.Control.Template%2A>方法。 下面的示例创建一个消息框，显示控件模板中<xref:System.Windows.Controls.Grid>的实际宽度值：  下面的示例创建一个消息框，显示的实际宽度值<xref:System.Windows.Controls.Grid>控件模板中：  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>请参阅  
 [查找由 DataTemplate 生成的元素](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [WPF XAML 名称范围](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [WPF 中的树](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
