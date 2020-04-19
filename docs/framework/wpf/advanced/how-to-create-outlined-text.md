---
title: 如何：创建空心文字
ms.date: 03/30/2017
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
ms.openlocfilehash: 86bfa396a2aa44eb511c014687501d60e170a396
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278920"
---
# <a name="how-to-create-outlined-text"></a>如何：创建大纲文本

在大多数情况下，当您在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序中向文本字符串添加修饰时，您将使用文本作为离散字符或字形的集合。 例如，您可以创建线性渐变画笔并将其应用于<xref:System.Windows.Controls.Control.Foreground%2A><xref:System.Windows.Controls.TextBox>对象的属性。 显示或编辑文本框时，线性渐变画笔将自动应用于文本字符串中的当前字符集。  
  
 ![使用线性渐变画笔显示的文本](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 但是，您还可以将文本转换为<xref:System.Windows.Media.Geometry>对象，从而创建其他类型的视觉丰富的文本。 例如，可以基于文本字符串的<xref:System.Windows.Media.Geometry>轮廓创建对象。  
  
 ![使用线性渐变画笔的文本轮廓](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 将文本转换为对象时<xref:System.Windows.Media.Geometry>，它不再是字符的集合，无法修改文本字符串中的字符。 但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。 笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。  
  
 以下示例说明了通过修改描边和填充转换文本来创建视觉效果的几种方法。  
  
 ![对填充和笔画使用不同颜色的文本](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 还可以修改转换文本的边界框矩形或高光。 下面的示例说明了通过修改转换文本的描边和高光来创建视觉效果的方法。  
  
 ![应用图像画笔进行描边和高光的文本](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>示例  
 将文本转换为<xref:System.Windows.Media.Geometry>对象的键是使用该<xref:System.Windows.Media.FormattedText>对象。 创建此对象后，可以使用<xref:System.Windows.Media.FormattedText.BuildGeometry%2A>和<xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A>方法将文本转换为<xref:System.Windows.Media.Geometry>对象。 第一种方法返回格式化文本的几何体;第二种方法返回格式化文本的边界框的几何体。 以下代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象并检索格式化文本及其边界框的几何体。  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 为了显示检索到<xref:System.Windows.Media.Geometry>的对象，您需要访问<xref:System.Windows.Media.DrawingContext>显示转换文本的对象。 在这些代码示例中，通过创建从支持用户定义的呈现的类派生的自定义控件对象来实现此访问。  
  
 要在<xref:System.Windows.Media.Geometry>自定义控件中显示对象，请为<xref:System.Windows.UIElement.OnRender%2A>方法提供重写。 重写的方法应使用 方法<xref:System.Windows.Media.DrawingContext.DrawGeometry%2A>绘制<xref:System.Windows.Media.Geometry>对象。  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  有关示例自定义用户控件对象的源，请参阅[C# 和](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs)[大纲文本控制.vb 的 OutlineTextControl.cs。](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)
  
## <a name="see-also"></a>另请参阅

- [绘制格式化文本](drawing-formatted-text.md)
