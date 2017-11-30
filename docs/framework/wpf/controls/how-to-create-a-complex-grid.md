---
title: "如何：创建复杂网格"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c0008a7379feefd9b3fe719f85b3205a72fb51d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-complex-grid"></a>如何：创建复杂网格
此示例演示如何使用<xref:System.Windows.Controls.Grid>创建如下所示的每月的日历的布局。  
  
## <a name="example"></a>示例  
 下面的示例通过定义八个行和八个列<xref:System.Windows.Controls.RowDefinition>和<xref:System.Windows.Controls.ColumnDefinition>类。 它使用<xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType>和<xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType>附加属性，连同<xref:System.Windows.Shapes.Rectangle>元素，用于填充的各个列和行的背景。 此设计是可能的因为多个元素可以存在于每个单元格中<xref:System.Windows.Controls.Grid>，主要区别<xref:System.Windows.Controls.Grid>和<xref:System.Windows.Documents.Table>。  
  
 该示例使用垂直渐变来<xref:System.Windows.Shapes.Shape.Fill%2A>为了改进直观显示和日历的可读性的行和列。 风格<xref:System.Windows.Controls.TextBlock>元素表示的日期和星期几。 <xref:System.Windows.Controls.TextBlock>元素绝对定位在其单元格内使用<xref:System.Windows.FrameworkElement.Margin%2A>属性和在应用程序的样式中定义的对齐方式属性。  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [表概述](../../../../docs/framework/wpf/advanced/table-overview.md)
