---
title: 如何：获取或设置 Dock 值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: b792c8b2342416fb380827b702efa28885145d66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554776"
---
# <a name="how-to-get-or-set-a-dock-value"></a>如何：获取或设置 Dock 值
下面的示例演示如何分配<xref:System.Windows.Controls.Dock>是对象的值。 该示例使用<xref:System.Windows.Controls.DockPanel.GetDock%2A>和<xref:System.Windows.Controls.DockPanel.SetDock%2A>方法<xref:System.Windows.Controls.DockPanel>。  
  
## <a name="example"></a>示例  
 该示例创建的实例<xref:System.Windows.Controls.TextBlock>元素， `txt1`，并将分配<xref:System.Windows.Controls.Dock>值`Top`使用<xref:System.Windows.Controls.DockPanel.SetDock%2A>方法<xref:System.Windows.Controls.DockPanel>。 然后追加的值<xref:System.Windows.Controls.Dock>属性<xref:System.Windows.Controls.TextBlock.Text%2A>的<xref:System.Windows.Controls.TextBlock>元素中的使用<xref:System.Windows.Controls.DockPanel.GetDock%2A>方法。 最后，该示例将添加<xref:System.Windows.Controls.TextBlock>到父元素<xref:System.Windows.Controls.DockPanel>， `dp1`。  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>  
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)
