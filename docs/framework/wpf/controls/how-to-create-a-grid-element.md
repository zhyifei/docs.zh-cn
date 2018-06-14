---
title: 如何：创建网格元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: 9fc70b8f15c4ecb4844c9c2ff4f7eeab94e7b906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551161"
---
# <a name="how-to-create-a-grid-element"></a>如何：创建网格元素
## <a name="example"></a>示例  
 下面的示例演示如何创建和使用的实例<xref:System.Windows.Controls.Grid>使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]或代码。 此示例使用三个<xref:System.Windows.Controls.ColumnDefinition>对象和三个<xref:System.Windows.Controls.RowDefinition>对象创建具有九个网格单元格，例如在工作表。 每个单元格包含<xref:System.Windows.Controls.TextBlock>元素，它表示数据和最上面一行包含<xref:System.Windows.Controls.TextBlock>与<xref:System.Windows.Controls.Grid.ColumnSpan%2A>应用的属性。 若要显示的每个单元格边界<xref:System.Windows.Controls.Grid.ShowGridLines%2A>启用属性。  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Grid>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)
