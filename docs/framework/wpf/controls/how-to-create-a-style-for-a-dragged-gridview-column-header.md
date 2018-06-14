---
title: 如何：为拖动的 GridView 列标题创建样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: 2e57b4cb1b8ddb90e8e6e0abc6db3e7f0b864cfa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554568"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>如何：为拖动的 GridView 列标题创建样式
此示例演示如何更改外观的拖动<xref:System.Windows.Controls.GridViewColumnHeader>当用户更改列的位置。  
  
## <a name="example"></a>示例  
 当将列标头拖动到另一位置<xref:System.Windows.Controls.ListView>使用<xref:System.Windows.Controls.GridView>作为其视图模式中，列移至新位置。 当您拖动列标题时，标头的浮点副本出现以及原始标头。 中的列标题<xref:System.Windows.Controls.GridView>由<xref:System.Windows.Controls.GridViewColumnHeader>对象。  
  
 若要自定义浮点型和原始标题的外观，你可以设置<xref:System.Windows.Controls.ControlTemplate.Triggers%2A>修改<xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>。 这些<xref:System.Windows.Controls.ControlTemplate.Triggers%2A>时应用<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>属性值是`true`和<xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>属性值是<xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>。  
  
 当用户按下鼠标按钮和鼠标悬停在按住<xref:System.Windows.Controls.GridViewColumnHeader>、<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>属性值更改为`true`。 同样，当用户开始拖动操作，<xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>属性更改为<xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>。  
  
 下面的示例演示如何设置<xref:System.Windows.Controls.ControlTemplate.Triggers%2A>更改<xref:System.Windows.Controls.Control.Foreground%2A>和<xref:System.Windows.Controls.Control.Background%2A>的原始窗口和浮动的标头时用户将列拖动到新位置的颜色。  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)
