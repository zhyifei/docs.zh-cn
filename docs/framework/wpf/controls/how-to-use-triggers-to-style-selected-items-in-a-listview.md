---
title: 如何：使用触发器在 ListView 中设置选定项的样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: ad64382b871bae9114a1e63257de3f8595376923
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145400"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>如何：使用触发器在 ListView 中设置选定项的样式
此示例演示如何定义<xref:System.Windows.Style.Triggers%2A>有关<xref:System.Windows.Controls.ListViewItem>控件，以便时的属性值<xref:System.Windows.Controls.ListViewItem>更改，<xref:System.Windows.Style>的<xref:System.Windows.Controls.ListViewItem>响应中的更改。  
  
## <a name="example"></a>示例  
 如果你想<xref:System.Windows.Style>的<xref:System.Windows.Controls.ListViewItem>若要更改以响应属性更改，请定义<xref:System.Windows.Style.Triggers%2A>为<xref:System.Windows.Style>更改。  
  
 下面的示例定义<xref:System.Windows.Trigger>，用于设置<xref:System.Windows.Controls.Control.Foreground%2A>属性设置为<xref:System.Windows.Media.Brushes.Blue%2A>，并更改<xref:System.Windows.FrameworkElement.Cursor%2A>以显示<xref:System.Windows.Input.CursorType.Hand>时<xref:System.Windows.UIElement.IsMouseOver%2A>属性更改为`true`。  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 下面的示例定义<xref:System.Windows.MultiTrigger>，用于设置<xref:System.Windows.Controls.Control.Foreground%2A>的属性<xref:System.Windows.Controls.ListViewItem>到<xref:System.Windows.Media.Brushes.Yellow%2A>时<xref:System.Windows.Controls.ListViewItem>是选定的项且具有键盘焦点。  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [帮助主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
