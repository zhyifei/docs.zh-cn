---
title: "如何：使用 Grid 来构建标准的 UI 对话框"
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
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69dba9b76f823e1779c4555521552b4a423c844c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>如何：使用 Grid 来构建标准的 UI 对话框
此示例演示如何创建标准[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]对话框中，通过使用<xref:System.Windows.Controls.Grid>元素。  
  
## <a name="example"></a>示例  
 下面的示例创建如下所示的对话框**运行**中的对话框[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]操作系统。  
  
 该示例创建<xref:System.Windows.Controls.Grid>并使用<xref:System.Windows.Controls.ColumnDefinition>和<xref:System.Windows.Controls.RowDefinition>类定义五列和四个行。  
  
 然后该示例将添加定位<xref:System.Windows.Controls.Image>， `RunIcon.png`，用于表示在对话框中找到的映像。 映像放置在第一列和行的<xref:System.Windows.Controls.Grid>（左上角）。  
  
 接下来，该示例将添加<xref:System.Windows.Controls.TextBlock>到第一个列跨越第一行的剩余列的元素。 它将添加另一个<xref:System.Windows.Controls.TextBlock>元素来表示第一列中的第二个行**打开**文本框。 A<xref:System.Windows.Controls.TextBlock>如下所示，它表示在数据输入区域。  
  
 最后，该示例将添加三个<xref:System.Windows.Controls.Button>元素到最后一行，后者表示**确定**，**取消**，和**浏览**事件。  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
