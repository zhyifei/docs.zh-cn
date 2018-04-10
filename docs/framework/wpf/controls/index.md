---
title: 控件
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66c6cc58423a2af8d0fd6de93b8884918888fb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="controls"></a>控件
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]附带了许多中几乎每个 Windows 应用程序，如使用的常见 UI 组件<xref:System.Windows.Controls.Button>， <xref:System.Windows.Controls.Label>， <xref:System.Windows.Controls.TextBox>， <xref:System.Windows.Controls.Menu>，和<xref:System.Windows.Controls.ListBox>。 以前，这些对象称为控件。 虽然[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]SDK 继续使用术语"控件"来松散意味着任何类表示可见对象的应用程序，务必要注意类不必继承自<xref:System.Windows.Controls.Control>该类具有可见状态。 继承自的类<xref:System.Windows.Controls.Control>类包含<xref:System.Windows.Controls.ControlTemplate>，它允许控件的使用者能够从根本上更改控件的外观，而无需创建新的子类。  本主题讨论如何控件 (继承自的这两个那些<xref:System.Windows.Controls.Control>类和一些未) 中常用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>创建控件的实例  
 你可以向应用程序添加控件，通过使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]或代码。  下面的示例演示如何创建一个向用户询问其姓名的简单应用程序。  此示例将创建六个控件： 两个标签、 两个文本框和两个按钮，其中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 所有控件均可使用相似方式创建。  
  
 [!code-xaml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 以下示例在代码中创建相同的应用程序。 为简洁起见，创建<xref:System.Windows.Controls.Grid>， `grid1`，已排除的示例。 `grid1`具有相同的列和行定义中前面所示[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例。  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>更改控件的外观  
 更改控件的外观以适应应用程序的外观，这是很常见的操作。 可以根据要达到的效果，通过执行以下操作之一来更改控件的外观：  
  
-   更改控件的属性值。  
  
-   创建<xref:System.Windows.Style>控件。  
  
-   创建一个新<xref:System.Windows.Controls.ControlTemplate>控件。  
  
### <a name="changing-a-controls-property-value"></a>更改控件的属性值  
 许多控件的一些属性，可用于更改控件的显示方式，如<xref:System.Windows.Controls.Control.Background%2A>的<xref:System.Windows.Controls.Button>。 你可以设置值属性中都[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]和代码。 下面的示例设置<xref:System.Windows.Controls.Control.Background%2A>， <xref:System.Windows.Controls.Control.FontSize%2A>，和<xref:System.Windows.Controls.Control.FontWeight%2A>属性<xref:System.Windows.Controls.Button>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
 [!code-xaml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 下面的示例在代码中设置相同的属性。  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>为控件创建样式  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使你能够指定控件的外观批发，而不是在应用程序，每个实例上设置属性，通过创建<xref:System.Windows.Style>。 下面的示例创建<xref:System.Windows.Style>，可应用于每个<xref:System.Windows.Controls.Button>应用程序中。 <xref:System.Windows.Style>定义通常在中定义[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中<xref:System.Windows.ResourceDictionary>，如<xref:System.Windows.FrameworkElement.Resources%2A>属性<xref:System.Windows.FrameworkElement>。  
  
 [!code-xaml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 你还可以将样式将密钥分配到样式并指定该注册表项中的应用到仅特定类型的某些控件`Style`控件的属性。  有关样式的详细信息，请参阅[样式和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。  
  
### <a name="creating-a-controltemplate"></a>创建 ControlTemplate  
 A<xref:System.Windows.Style>允许你一次在多个控件上设置属性，但有时你可能想要自定义的外观<xref:System.Windows.Controls.Control>超出可以通过创建执行的操作<xref:System.Windows.Style>。 继承自的类<xref:System.Windows.Controls.Control>类具有<xref:System.Windows.Controls.ControlTemplate>，后者定义的结构和外观<xref:System.Windows.Controls.Control>。 <xref:System.Windows.Controls.Control.Template%2A>属性<xref:System.Windows.Controls.Control>是公共的因此你可以为提供<xref:System.Windows.Controls.Control><xref:System.Windows.Controls.ControlTemplate>不同于其默认值。 你通常可以指定新<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Control>而不是从控件的外观进行自定义继承<xref:System.Windows.Controls.Control>。  
  
 请考虑很常见的控件， <xref:System.Windows.Controls.Button>。  主要行为<xref:System.Windows.Controls.Button>是使应用程序采取某项措施，当用户单击它。  默认情况下，<xref:System.Windows.Controls.Button>中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]显示为一个引发矩形。  在开发应用程序时，你可能想要充分利用的行为<xref:System.Windows.Controls.Button>-也就是说，通过处理按钮的 click 事件，但可能会更改超出你可以通过更改按钮的属性实现的操作的按钮的外观。  在这种情况下，你可以创建一个新<xref:System.Windows.Controls.ControlTemplate>。  
  
 下面的示例创建<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Button>。  <xref:System.Windows.Controls.ControlTemplate>创建<xref:System.Windows.Controls.Button>为圆的角和渐变背景。  <xref:System.Windows.Controls.ControlTemplate>包含<xref:System.Windows.Controls.Border>其<xref:System.Windows.Controls.Border.Background%2A>是<xref:System.Windows.Media.LinearGradientBrush>包含两个<xref:System.Windows.Media.GradientStop>对象。  第一个<xref:System.Windows.Media.GradientStop>使用数据绑定来绑定<xref:System.Windows.Media.GradientStop.Color%2A>属性<xref:System.Windows.Media.GradientStop>到按钮的背景的颜色。  当你将设置<xref:System.Windows.Controls.Control.Background%2A>属性<xref:System.Windows.Controls.Button>，此值的颜色将用作第一个<xref:System.Windows.Media.GradientStop>。 有关数据绑定的详细信息，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。 此示例还创建<xref:System.Windows.Trigger>更改的外观<xref:System.Windows.Controls.Button>时<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>是`true`。  
  
 [!code-xaml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Control.Background%2A>属性<xref:System.Windows.Controls.Button>必须设置为<xref:System.Windows.Media.SolidColorBrush>例如正常工作。  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>订阅事件  
 你可以通过使用订阅控件的事件[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]或代码，但你只能处理代码中的事件。  下面的示例演示`Click`事件<xref:System.Windows.Controls.Button>。  
  
 [!code-xaml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 下面的示例处理`Click`事件<xref:System.Windows.Controls.Button>。  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>控件中的丰富内容  
 继承自的大多数类<xref:System.Windows.Controls.Control>类足够容量来包含丰富的内容。 例如，<xref:System.Windows.Controls.Label>可以包含任何对象，例如字符串， <xref:System.Windows.Controls.Image>，或<xref:System.Windows.Controls.Panel>。  以下类支持丰富的内容，充当大部分中的控件的基类[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  
  
-   <xref:System.Windows.Controls.ContentControl>-从此类继承的类一些示例包括<xref:System.Windows.Controls.Label>， <xref:System.Windows.Controls.Button>，和<xref:System.Windows.Controls.ToolTip>。  
  
-   <xref:System.Windows.Controls.ItemsControl>-从此类继承的类一些示例包括<xref:System.Windows.Controls.ListBox>， <xref:System.Windows.Controls.Menu>，和<xref:System.Windows.Controls.Primitives.StatusBar>。  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>-从此类继承的类一些示例包括<xref:System.Windows.Controls.TabItem>， <xref:System.Windows.Controls.GroupBox>，和<xref:System.Windows.Controls.Expander>。  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>-从此类继承的类一些示例包括<xref:System.Windows.Controls.MenuItem>， <xref:System.Windows.Controls.TreeViewItem>，和<xref:System.Windows.Controls.ToolBar>。  
  
-  
  
 有关这些基类的类的详细信息，请参阅[WPF 内容模型](../../../../docs/framework/wpf/controls/wpf-content-model.md)。  
  
## <a name="see-also"></a>请参阅  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [按类别分类的控件](../../../../docs/framework/wpf/controls/controls-by-category.md)  
 [控件库](../../../../docs/framework/wpf/controls/control-library.md)  
 [数据模板化概述](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [输入](../../../../docs/framework/wpf/advanced/input-wpf.md)  
 [启用命令](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)  
 [演练：创建采用动画效果的自定义按钮](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)  
 [控件自定义](../../../../docs/framework/wpf/controls/control-customization.md)
