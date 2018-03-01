---
title: "如何：使用触发器为 ListView 中的选定项设置样式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f8965ee524d6a5cb03a54ac07d8889ff9801440
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>如何：使用触发器为 ListView 中的选定项设置样式
此示例演示如何定义<xref:System.Windows.Style.Triggers%2A>为<xref:System.Windows.Controls.ListViewItem>控件，以便的属性值时<xref:System.Windows.Controls.ListViewItem>更改，<xref:System.Windows.Style>的<xref:System.Windows.Controls.ListViewItem>相应地发生变化。  
  
## <a name="example"></a>示例  
 如果你想<xref:System.Windows.Style>的<xref:System.Windows.Controls.ListViewItem>若要更改以响应属性更改，请定义<xref:System.Windows.Style.Triggers%2A>为<xref:System.Windows.Style>更改。  
  
 下面的示例定义<xref:System.Windows.Trigger>设置<xref:System.Windows.Controls.Control.Foreground%2A>属性<xref:System.Windows.Media.Brushes.Blue%2A>并更改<xref:System.Windows.FrameworkElement.Cursor%2A>以显示<xref:System.Windows.Input.CursorType.Hand>时<xref:System.Windows.UIElement.IsMouseOver%2A>属性更改为`true`。  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 下面的示例定义<xref:System.Windows.MultiTrigger>设置<xref:System.Windows.Controls.Control.Foreground%2A>属性<xref:System.Windows.Controls.ListViewItem>到<xref:System.Windows.Media.Brushes.Yellow%2A>时<xref:System.Windows.Controls.ListViewItem>是选定的项和具有键盘焦点。  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)
