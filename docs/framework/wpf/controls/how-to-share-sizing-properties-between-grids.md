---
title: "如何：在网格之间共享大小调整属性"
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
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8f80d93f9625ff962a3e3fab1f6647678ecf32f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-share-sizing-properties-between-grids"></a>如何：在网格之间共享大小调整属性
此示例演示如何共享列的大小调整数据和行之间<xref:System.Windows.Controls.Grid>元素，以便保留大小调整保持一致。  
  
## <a name="example"></a>示例  
 下面的示例引入了两个<xref:System.Windows.Controls.Grid>元素作为子元素的父<xref:System.Windows.Controls.DockPanel>。 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>附加属性的<xref:System.Windows.Controls.Grid>对父定义<xref:System.Windows.Controls.DockPanel>。  
  
 该示例通过使用两个操作的属性值<xref:System.Windows.Controls.Button>元素; 每个元素表示一个布尔属性值。 当<xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>属性值设置为`true`的每个列或行成员<xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>共享调整大小的信息，而不考虑行或列的内容。  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 下面的代码隐藏示例处理方法，该按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件引发。 此示例将对这些方法调用的结果<xref:System.Windows.Controls.TextBlock>元素使用与 get 方法以输出字符串的形式将新属性值。  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)
