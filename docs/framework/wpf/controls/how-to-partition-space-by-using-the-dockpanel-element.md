---
title: "如何：使用 DockPanel 元素对空间进行分区"
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
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4adfabba76e9f6bf32e47fe4e52e42b68676bc0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>如何：使用 DockPanel 元素对空间进行分区
下面的示例创建一个简单[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]framework 使用<xref:System.Windows.Controls.DockPanel>元素。 <xref:System.Windows.Controls.DockPanel>分区到其子元素可用空间。  
  
## <a name="example"></a>示例  
 此示例使用<xref:System.Windows.Controls.DockPanel.Dock%2A>属性，它是附加的属性，若要将两个相同停靠<xref:System.Windows.Controls.Border>处的元素<xref:System.Windows.Controls.Dock.Top>的分区的空间。 第三个<xref:System.Windows.Controls.Border>元素沿停靠<xref:System.Windows.Controls.Dock.Left>，其宽度设置为 200 像素。 第四个<xref:System.Windows.Controls.Border>停靠<xref:System.Windows.Controls.Dock.Bottom>的屏幕。 最后一个<xref:System.Windows.Controls.Border>元素会自动填写剩余的空间。  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  默认情况下的最后一个子级<xref:System.Windows.Controls.DockPanel>元素填充剩余的未分配的空间。 如果不希望出现此行为，请设置 `LastChildFill="False"`。  
  
 已编译的应用程序将生成如下所示的新 UI。  
  
 ![典型的 DockPanel 方案。](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.DockPanel>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)
