---
title: 如何：使用 Grid 生成标准 UI 对话框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923421"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>如何：使用 Grid 生成标准 UI 对话框
此示例演示如何[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.Grid>使用元素创建标准对话框。  
  
## <a name="example"></a>示例  
 下面的示例创建一个对话框, 如 Windows 操作系统中的 "**运行**" 对话框。  
  
 该示例创建一个<xref:System.Windows.Controls.Grid> , 并<xref:System.Windows.Controls.ColumnDefinition>使用和<xref:System.Windows.Controls.RowDefinition>类定义五个列和四行。  
  
 然后, 该示例添加并定位<xref:System.Windows.Controls.Image>, `RunIcon.png`以表示在对话框中找到的图像。 图像位于<xref:System.Windows.Controls.Grid> (左上角) 的第一列和第一行。  
  
 接下来, 该示例向<xref:System.Windows.Controls.TextBlock>第一列添加一个元素, 该元素跨越第一行的其余列。 它将另<xref:System.Windows.Controls.TextBlock>一个元素添加到第一列中的第二行, 以表示**打开**的文本框。 下面<xref:System.Windows.Controls.TextBlock>是一个, 它表示数据输入区域。  
  
 最后, 此示例将三<xref:System.Windows.Controls.Button>个元素添加到最后一行, 该行表示 **"确定"、"** **取消**" 和 "**浏览**" 事件。  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [面板概述](panels-overview.md)
- [帮助主题](grid-how-to-topics.md)
