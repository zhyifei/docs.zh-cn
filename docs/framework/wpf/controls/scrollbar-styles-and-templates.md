---
title: ScrollBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 7093a78555aefd73f9bb05c0a7b5fab6b66176fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283417"
---
# <a name="scrollbar-styles-and-templates"></a>ScrollBar 样式和模板
本主题介绍 <xref:System.Windows.Controls.Primitives.ScrollBar> 控件的样式和模板。 您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。  
  
## <a name="scrollbar-parts"></a>滚动条部件  
 下表列出了 <xref:System.Windows.Controls.Primitives.ScrollBar> 控件的已命名部分。  
  
|部件|Type|描述|  
|-|-|-|  
|PART_Track|<xref:System.Windows.Controls.Primitives.Track>|指示 <xref:System.Windows.Controls.Primitives.ScrollBar>位置的元素的容器。|  
  
## <a name="scrollbar-states"></a>滚动条状态  
 下表列出了 <xref:System.Windows.Controls.Primitives.ScrollBar> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|一般|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针悬停在控件上。|  
|Disabled|CommonStates|已禁用控件。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 并且控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 的，该控件没有焦点。|  
  
## <a name="scrollbar-controltemplate-example"></a>滚动条 System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.Primitives.ScrollBar> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 上一示例使用了一个或多个以下资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [控件样式和模板](control-styles-and-templates.md)
- [控件自定义](control-customization.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [为控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)
