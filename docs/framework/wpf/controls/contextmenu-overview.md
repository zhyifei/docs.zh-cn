---
title: ContextMenu 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185915"
---
# <a name="contextmenu-overview"></a>ContextMenu 概述
类<xref:System.Windows.Controls.ContextMenu>表示使用特定于<xref:System.Windows.Controls.Menu>上下文的 公开功能的元素。 通常，用户[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]通过右键单击<xref:System.Windows.Controls.ContextMenu>鼠标按钮来公开 中的。 本主题介绍该<xref:System.Windows.Controls.ContextMenu>元素，并提供如何在 和 代码中使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]该元素的示例。  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a>ContextMenu 控件  
 附加到<xref:System.Windows.Controls.ContextMenu>特定控件。 该<xref:System.Windows.Controls.ContextMenu>元素使您能够向用户显示指定与特定控件关联的命令或选项的项列表，例如<xref:System.Windows.Controls.Button>。 用户通过右键单击控件来显示菜单。 通常，单击<xref:System.Windows.Controls.MenuItem>将打开子菜单或导致应用程序执行命令。  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a>创建 ContextMenus  
 以下示例演示如何使用子菜单创建<xref:System.Windows.Controls.ContextMenu>。 控件<xref:System.Windows.Controls.ContextMenu>附加到按钮控件。  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a>将样式应用于 ContextMenu  
 通过使用 控件<xref:System.Windows.Style>，可以显著更改 的外观<xref:System.Windows.Controls.ContextMenu>和行为，而无需编写自定义控件。 除了设置可视化属性以外，还可以将样式应用于控件的各个部分。 例如，可以使用 属性更改控件的各个部分的行为，也可以向 或 更改<xref:System.Windows.Controls.ContextMenu>的布局添加部件。 以下示例显示了向<xref:System.Windows.Controls.ContextMenu>控件添加样式的几种方法。  
  
 第一个示例定义一个名为 `SimpleSysResources` 的样式，它演示如何在样式中使用当前的系统设置。 该示例将指定<xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A>为<xref:System.Windows.Controls.Control.Background%2A>颜色和<xref:System.Windows.SystemColors.MenuTextBrushKey%2A><xref:System.Windows.Controls.Control.Foreground%2A>颜色<xref:System.Windows.Controls.ContextMenu>。  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 下面的示例使用 元素<xref:System.Windows.Trigger>更改 的外观<xref:System.Windows.Controls.Menu>，以响应在 上引发的事件<xref:System.Windows.Controls.ContextMenu>。 当用户将鼠标移到菜单上时，<xref:System.Windows.Controls.ContextMenu>项目的外观会发生变化。  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [ContextMenu](contextmenu.md)
- [ContextMenu 样式和模板](contextmenu-styles-and-templates.md)
- [WPF 控件库示例](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
