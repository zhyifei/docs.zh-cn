---
title: 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 2aab0fc8adaf17a8e9820a6269a740ef09540cda
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646486"
---
# <a name="controls"></a>控件
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]附带许多常用的 UI 组件，这些组件用于几乎每个 Windows 应用程序，例如<xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Label>、<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.Menu> <xref:System.Windows.Controls.ListBox>。 以前，这些对象称为控件。 虽然[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]SDK 继续使用术语"控件"来松散地表示表示应用程序中可见对象的任何类，但请务必注意，类不需要从<xref:System.Windows.Controls.Control>类继承来具有可见状态。 从类继承的<xref:System.Windows.Controls.Control>类包含 ，<xref:System.Windows.Controls.ControlTemplate>它允许控件的使用者从根本上改变控件的外观，而无需创建新的子类。  本主题讨论如何在 中<xref:System.Windows.Controls.Control>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]常用控件（从类继承的控件和未从类继承的控件）  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>创建控件的实例  
 可以使用 任一或[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]代码向应用程序添加控件。  下面的示例演示如何创建一个向用户询问其姓名的简单应用程序。  本示例在 中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]创建六个控件：两个标签、两个文本框和两个按钮。 所有控件均可使用相似方式创建。  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 以下示例在代码中创建相同的应用程序。 为简洁起见，从样本中排除了<xref:System.Windows.Controls.Grid>的`grid1`创建。 `grid1`具有与上例[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]所示相同的列和行定义。  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>更改控件的外观  
 更改控件的外观以适应应用程序的外观，这是很常见的操作。 可以根据要达到的效果，通过执行以下操作之一来更改控件的外观：  
  
- 更改控件的属性值。  
  
- 为控件<xref:System.Windows.Style>创建 。  
  
- <xref:System.Windows.Controls.ControlTemplate>为控件创建新控件。  
  
### <a name="changing-a-controls-property-value"></a>更改控件的属性值  
 许多控件具有允许您更改控件显示方式的属性，例如<xref:System.Windows.Controls.Control.Background%2A>。 <xref:System.Windows.Controls.Button> 您可以在 和[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]代码中设置值属性。 下面的示例在<xref:System.Windows.Controls.Control.Background%2A><xref:System.Windows.Controls.Control.FontSize%2A><xref:System.Windows.Controls.Control.FontWeight%2A><xref:System.Windows.Controls.Button>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]设置 、 和 属性。  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 下面的示例在代码中设置相同的属性。  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>为控件创建样式  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通过创建 ，可以大规模指定控件的外观，而不是设置应用程序中每个实例的属性<xref:System.Windows.Style>。 下面的示例创建<xref:System.Windows.Style>应用于应用程序中每个应用<xref:System.Windows.Controls.Button>的 。 <xref:System.Windows.Style>定义[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]通常在 中<xref:System.Windows.ResourceDictionary>定义，如<xref:System.Windows.FrameworkElement.Resources%2A>的属性。 <xref:System.Windows.FrameworkElement>  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 还可以通过将键分配给样式并在控件`Style`的属性中指定该键，仅将样式应用于特定类型的特定控件。  有关样式的详细信息，请参阅[样式和模板](../../../desktop-wpf/fundamentals/styles-templates-overview.md)化。  
  
### <a name="creating-a-controltemplate"></a>创建 ControlTemplate  
 允许您<xref:System.Windows.Style>一次在多个控件上设置属性，但有时您可能希望自定义 的外观<xref:System.Windows.Controls.Control>，超出通过创建 可以执行的内容。 <xref:System.Windows.Style> 从类继承的<xref:System.Windows.Controls.Control>类具有 ，<xref:System.Windows.Controls.ControlTemplate>它定义 的<xref:System.Windows.Controls.Control>结构和外观。 的属性<xref:System.Windows.Controls.Control.Template%2A><xref:System.Windows.Controls.Control>是公共的，因此您可以给出与其默认值不同的 。 <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> 通常可以为 指定<xref:System.Windows.Controls.ControlTemplate><xref:System.Windows.Controls.Control>new，而不是从控件继承以自定义 的外观。 <xref:System.Windows.Controls.Control>  
  
 请考虑很常见的控制。 <xref:System.Windows.Controls.Button>  的主要行为<xref:System.Windows.Controls.Button>是使应用程序能够在用户单击时执行某些操作。  默认情况下，in<xref:System.Windows.Controls.Button>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]显示为凸起的矩形。  在开发应用程序时，您可能希望利用<xref:System.Windows.Controls.Button>-- -- 即通过处理按钮的单击事件来利用 " 的行为"，但您可以通过更改按钮的属性来更改按钮的外观， 超出您可以执行的操作。  在这种情况下，您可以创建一个新的<xref:System.Windows.Controls.ControlTemplate>。  
  
 下面的示例为 创建<xref:System.Windows.Controls.ControlTemplate>。 <xref:System.Windows.Controls.Button>  创建<xref:System.Windows.Controls.ControlTemplate>具有<xref:System.Windows.Controls.Button>圆角和渐变背景的 。  <xref:System.Windows.Controls.ControlTemplate>包含<xref:System.Windows.Controls.Border>其<xref:System.Windows.Controls.Border.Background%2A>是 具有两<xref:System.Windows.Media.LinearGradientBrush>个<xref:System.Windows.Media.GradientStop>对象的 的 。  第一<xref:System.Windows.Media.GradientStop>个使用数据绑定将<xref:System.Windows.Media.GradientStop.Color%2A>的属性<xref:System.Windows.Media.GradientStop>绑定到按钮背景的颜色。  设置 的属性<xref:System.Windows.Controls.Control.Background%2A><xref:System.Windows.Controls.Button>时，该值的颜色将用作第一个<xref:System.Windows.Media.GradientStop>。 有关数据绑定的详细信息，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。 该示例还创建<xref:System.Windows.Trigger>一个，用于更改<xref:System.Windows.Controls.Button>时<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>的外观`true`。  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> 必须<xref:System.Windows.Controls.Control.Background%2A>将 的属性<xref:System.Windows.Controls.Button>设置为 ，<xref:System.Windows.Media.SolidColorBrush>以便示例正常工作。  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>订阅事件  
 可以使用 任一[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]或代码订阅控件的事件，但只能在代码中处理事件。  下面的示例演示如何订阅 的事件`Click`<xref:System.Windows.Controls.Button>。  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 下面的示例处理`Click`的事件<xref:System.Windows.Controls.Button>。  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>控件中的丰富内容  
 从<xref:System.Windows.Controls.Control>类继承的大多数类都具有包含丰富内容的能力。 例如，可以<xref:System.Windows.Controls.Label>包含任何对象，如字符串、或<xref:System.Windows.Controls.Image>。 <xref:System.Windows.Controls.Panel>  以下类支持丰富的内容，并充当 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]大多数控件的基类。  
  
- <xref:System.Windows.Controls.ContentControl>-- 从此类继承的类的一些示例<xref:System.Windows.Controls.Label>是<xref:System.Windows.Controls.Button>，<xref:System.Windows.Controls.ToolTip>和 。  
  
- <xref:System.Windows.Controls.ItemsControl>-- 从此类继承的类的一些示例<xref:System.Windows.Controls.ListBox>是<xref:System.Windows.Controls.Menu>，<xref:System.Windows.Controls.Primitives.StatusBar>和 。  
  
- <xref:System.Windows.Controls.HeaderedContentControl>-- 从此类继承的类的一些示例<xref:System.Windows.Controls.TabItem>是<xref:System.Windows.Controls.GroupBox>，<xref:System.Windows.Controls.Expander>和 。  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>-- 从此类继承的类的一些示例<xref:System.Windows.Controls.MenuItem>是<xref:System.Windows.Controls.TreeViewItem>，<xref:System.Windows.Controls.ToolBar>和 。  

 有关这些基类的详细信息，请参阅[WPF 内容模型](wpf-content-model.md)。  
  
## <a name="see-also"></a>另请参阅

- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [按类别分类的控件](controls-by-category.md)
- [控件库](control-library.md)
- [数据模板化概述](../data/data-templating-overview.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [输入](../advanced/input-wpf.md)
- [启用命令](../advanced/how-to-enable-a-command.md)
- [演练：创建自定义的动画按钮](walkthroughs-create-a-custom-animated-button.md)
- [控件自定义](control-customization.md)
