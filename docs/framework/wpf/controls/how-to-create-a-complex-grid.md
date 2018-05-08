---
title: 如何：创建复杂网格
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: 49bf9781d56b93fd4529f3c9b62deb171e69155f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-complex-grid"></a>如何：创建复杂网格
此示例演示如何使用<xref:System.Windows.Controls.Grid>创建如下所示的每月的日历的布局。  
  
## <a name="example"></a>示例  
 下面的示例通过定义八个行和八个列<xref:System.Windows.Controls.RowDefinition>和<xref:System.Windows.Controls.ColumnDefinition>类。 它使用<xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType>和<xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType>附加属性，连同<xref:System.Windows.Shapes.Rectangle>元素，用于填充的各个列和行的背景。 此设计是可能的因为多个元素可以存在于每个单元格中<xref:System.Windows.Controls.Grid>，主要区别<xref:System.Windows.Controls.Grid>和<xref:System.Windows.Documents.Table>。  
  
 该示例使用垂直渐变来<xref:System.Windows.Shapes.Shape.Fill%2A>为了改进直观显示和日历的可读性的行和列。 风格<xref:System.Windows.Controls.TextBlock>元素表示的日期和星期几。 <xref:System.Windows.Controls.TextBlock> 元素绝对定位在其单元格内使用<xref:System.Windows.FrameworkElement.Margin%2A>属性和在应用程序的样式中定义的对齐方式属性。  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [表概述](../../../../docs/framework/wpf/advanced/table-overview.md)
