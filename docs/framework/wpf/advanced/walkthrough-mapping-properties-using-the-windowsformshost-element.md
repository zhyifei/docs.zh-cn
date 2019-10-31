---
title: 演练：使用 WindowsFormsHost 元素映射属性
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: c8a83dd3f7327d00979431ca7fa801ff642a4eef
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197810"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>演练：使用 WindowsFormsHost 元素映射属性

本演练演示如何使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 属性将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性映射到寄宿 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件上的相应属性。

本演练涉及以下任务：

- 创建项目。

- 定义应用程序布局。

- 定义新的属性映射。

- 删除默认属性映射。

- 替换默认属性映射。

- 扩展默认属性映射。

有关本演练中所述任务的完整代码列表，请参阅[使用 System.windows.forms.integration.windowsformshost> 元素映射属性示例](https://go.microsoft.com/fwlink/?LinkID=160019)。

完成后，你将能够将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性映射到托管 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件上的相应属性。

## <a name="prerequisites"></a>Prerequisites

你需要以下组件来完成本演练：

- Visual Studio 2017

## <a name="create-and-set-up-the-project"></a>创建和设置项目

1. 创建一个名为 `PropertyMappingWithWfhSample`的**WPF 应用程序**项目。

2. 在**解决方案资源管理器**中，添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。

3. 在**解决方案资源管理器**中，添加对 System.web 和 system.web 程序集的引用。

## <a name="defining-the-application-layout"></a>定义应用程序布局

基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素来承载 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。

### <a name="to-define-the-application-layout"></a>定义应用程序布局

1. 在 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]中打开 Window1.xaml。

2. 用下面的代码替换现有代码。

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. 在代码编辑器中打开 Window1.xaml.cs。

4. 在该文件顶部导入以下命名空间。

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a>定义新的属性映射

<xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素提供了几个默认属性映射。 通过对 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>调用 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 方法，可以添加新的属性映射。

### <a name="to-define-a-new-property-mapping"></a>定义新的属性映射

- 将以下代码复制到 `Window1` 类的定义中。

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     `AddClipMapping` 方法为 <xref:System.Windows.UIElement.Clip%2A> 属性添加新映射。

     `OnClipChange` 方法将 <xref:System.Windows.UIElement.Clip%2A> 属性转换为 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> 属性。

     `Window1_SizeChanged` 方法处理窗口的 <xref:System.Windows.FrameworkElement.SizeChanged> 事件，并调整剪辑区域的大小以适合应用程序窗口。

## <a name="removing-a-default-property-mapping"></a>删除默认属性映射

通过对 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>调用 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 方法来删除默认属性映射。

### <a name="to-remove-a-default-property-mapping"></a>删除默认属性映射

- 将以下代码复制到 `Window1` 类的定义中。

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     `RemoveCursorMapping` 方法将删除 <xref:System.Windows.FrameworkElement.Cursor%2A> 属性的默认映射。

## <a name="replacing-a-default-property-mapping"></a>替换默认属性映射

通过删除默认映射并对 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>调用 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 方法来替换默认属性映射。

### <a name="to-replace-a-default-property-mapping"></a>替换默认属性映射

- 将以下代码复制到 `Window1` 类的定义中。

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     `ReplaceFlowDirectionMapping` 方法替换 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性的默认映射。

     `OnFlowDirectionChange` 方法将 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性转换为 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> 属性。

     `cb_CheckedChanged` 方法处理 <xref:System.Windows.Forms.CheckBox> 控件上的 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 事件。 它基于 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 属性的值分配 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性

## <a name="extending-a-default-property-mapping"></a>扩展默认属性映射

可以使用默认属性映射，并使用自己的映射对其进行扩展。

### <a name="to-extend-a-default-property-mapping"></a>扩展默认属性映射

- 将以下代码复制到 `Window1` 类的定义中。

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     `ExtendBackgroundMapping` 方法将自定义属性转换器添加到现有 <xref:System.Windows.Controls.Control.Background%2A> 属性映射。

     `OnBackgroundChange` 方法将特定的图像分配给寄宿控件的 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性。 应用默认属性映射后，将调用 `OnBackgroundChange` 方法。

## <a name="initializing-your-property-mappings"></a>初始化属性映射

通过调用 <xref:System.Windows.FrameworkElement.Loaded> 事件处理程序中前面所述的方法来设置属性映射。

### <a name="to-initialize-your-property-mappings"></a>初始化属性映射

1. 将以下代码复制到 `Window1` 类的定义中。

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     `WindowLoaded` 方法处理 <xref:System.Windows.FrameworkElement.Loaded> 事件并执行以下初始化。

    - 创建 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> 控件。

    - 调用先前在演练中定义的方法来设置属性映射。

    - 将初始值分配给映射的属性。

2. 按 F5 生成并运行该应用程序。 单击该复选框可以查看 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 映射的效果。 单击复选框时，布局会反转其左右方向。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Windows 窗体和 WPF 属性映射](windows-forms-and-wpf-property-mapping.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [演练：在 WPF 中承载 Windows 窗体控件](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
