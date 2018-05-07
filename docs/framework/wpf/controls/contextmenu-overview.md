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
ms.openlocfilehash: e862f02e736cb8507dde5036700d751f8af0a226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="contextmenu-overview"></a>ContextMenu 概述
<xref:System.Windows.Controls.ContextMenu>类表示一个元素，通过使用特定于上下文的公开功能<xref:System.Windows.Controls.Menu>。 通常情况下，用户公开<xref:System.Windows.Controls.ContextMenu>中[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]通过右键单击鼠标按钮。 本主题介绍<xref:System.Windows.Controls.ContextMenu>元素，并提供如何使用在示例[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]和代码。  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>ContextMenu 控件  
 A<xref:System.Windows.Controls.ContextMenu>附加到特定的控件。 <xref:System.Windows.Controls.ContextMenu>元素使您能够为用户提供的命令或例如，与特定控件关联的选项指定的项列表<xref:System.Windows.Controls.Button>。 用户通过右键单击控件来显示菜单。 通常情况下，单击<xref:System.Windows.Controls.MenuItem>打开一个子菜单或导致应用程序执行的命令。  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>创建 ContextMenus  
 下面的示例演示如何创建<xref:System.Windows.Controls.ContextMenu>具有子菜单。 <xref:System.Windows.Controls.ContextMenu>控件附加到按钮控件。  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>将样式应用于 ContextMenu  
 通过使用控件<xref:System.Windows.Style>，你可以显著改变的外观和行为<xref:System.Windows.Controls.ContextMenu>而无需编写自定义控件。 除了设置可视化属性以外，还可以将样式应用于控件的各个部分。 例如，你可以通过使用属性，更改控件的部件的行为也可以添加部分，或更改的布局， <xref:System.Windows.Controls.ContextMenu>。 下面的示例演示通过多种方式添加到样式<xref:System.Windows.Controls.ContextMenu>控件。  
  
 第一个示例定义一个名为 `SimpleSysResources` 的样式，它演示如何在样式中使用当前的系统设置。 该示例将指定<xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A>作为<xref:System.Windows.Controls.Control.Background%2A>颜色和<xref:System.Windows.SystemColors.MenuTextBrushKey%2A>作为<xref:System.Windows.Controls.Control.Foreground%2A>颜色<xref:System.Windows.Controls.ContextMenu>。  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 下面的示例使用<xref:System.Windows.Trigger>要更改的外观元素<xref:System.Windows.Controls.Menu>对引发的事件的响应<xref:System.Windows.Controls.ContextMenu>。 当用户将鼠标移动放置在菜单上的外观<xref:System.Windows.Controls.ContextMenu>项更改。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.Menu>  
 <xref:System.Windows.Controls.MenuItem>  
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)  
 [ContextMenu 样式和模板](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)  
 [WPF 控件库示例](http://go.microsoft.com/fwlink/?LinkID=160053)
