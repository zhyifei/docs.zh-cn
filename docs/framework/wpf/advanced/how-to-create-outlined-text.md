---
title: "如何：创建空心文字"
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
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76d0dcf63f9d8a66106f4bcdc52a2bf98c75cdc4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-outlined-text"></a>如何：创建空心文字
在大多数情况下，在对中的文本字符串添加装饰时你[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序中，使用离散字符或标志符号的集合形式的文本。 例如，你可以创建线性渐变画笔，并将其应用于<xref:System.Windows.Controls.Control.Foreground%2A>属性<xref:System.Windows.Controls.TextBox>对象。 当你显示或编辑文本框中时，线性渐变画笔自动应用于当前集文本字符串中的字符。  
  
 ![使用线性渐变画笔显示的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")  
线性渐变画笔应用到的文本框中的示例  
  
 但是，你还可以将转换到的文本<xref:System.Windows.Media.Geometry>对象，使你可以创建其他类型的可视化多格式文本。 例如，你可以创建<xref:System.Windows.Media.Geometry>对象基于轮廓的文本字符串。  
  
 ![使用线性渐变画笔的文本轮廓](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
线性渐变画笔应用于文本的大纲几何图形的示例  
  
 当文本转换为<xref:System.Windows.Media.Geometry>对象，它不再是字符的集合，无法修改的文本字符串中的字符。 但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。 笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。  
  
 下面的示例说明了多种方法可以通过修改的笔画和填充的已转换的文本来创建视觉效果。  
  
 ![对填充和笔画使用不同颜色的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
将笔划和填充设置为不同颜色的示例  
  
 ![笔画应用了图像画笔的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
笔划应用了图像画笔的示例  
  
 还有可能要修改的边界框矩形或突出显示，已转换的文本。 下面的示例演示通过修改笔划和突出显示的已转换的文本来创建视觉效果的方法。  
  
 ![笔画应用了图像画笔的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
笔划和突出显示应用了图像画笔的示例  
  
## <a name="example"></a>示例  
 将文本转换为密钥<xref:System.Windows.Media.Geometry>对象是使用<xref:System.Windows.Media.FormattedText>对象。 一旦你已创建此对象，就可以使用<xref:System.Windows.Media.FormattedText.BuildGeometry%2A>和<xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A>方法来将文本转换为<xref:System.Windows.Media.Geometry>对象。 第一种方法返回的几何图形的带格式的文本;第二种方法返回的几何图形的带格式的文本的边界框。 下面的代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象并检索带格式的文本和其边界框的几何图形。  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 为了显示检索<xref:System.Windows.Media.Geometry>你需要访问的对象<xref:System.Windows.Media.DrawingContext>显示转换后的文本的对象。 在这些代码示例，这可通过创建从支持用户定义的呈现的类派生的自定义控件对象。  
  
 若要显示<xref:System.Windows.Media.Geometry>在自定义控件中，对象提供的替代<xref:System.Windows.UIElement.OnRender%2A>方法。 重写的方法应使用<xref:System.Windows.Media.DrawingContext.DrawGeometry%2A>方法，以便绘制<xref:System.Windows.Media.Geometry>对象。  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a>另请参阅  
 [绘制格式化文本](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
