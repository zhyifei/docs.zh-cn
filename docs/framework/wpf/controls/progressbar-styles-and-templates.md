---
title: ProgressBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 6551701e86dd6abcd42f143f146c7bdadfeabbcf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283456"
---
# <a name="progressbar-styles-and-templates"></a>ProgressBar 样式和模板
本主题介绍 <xref:System.Windows.Controls.ProgressBar> 控件的样式和模板。 您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。  
  
## <a name="progressbar-parts"></a>ProgressBar 部件  
 下表列出了 <xref:System.Windows.Controls.ProgressBar> 控件的已命名部分。  
  
|部件|类型|说明|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|指示进度的对象。|  
|PART_Track|<xref:System.Windows.FrameworkElement>|定义进度指示器的路径的对象。|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|Embellishes 进度栏的对象。|  
  
## <a name="progressbar-states"></a>ProgressBar 状态  
 下表列出了 <xref:System.Windows.Controls.ProgressBar> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|说明|  
|----------------------|---------------------------|-----------------|  
|确定性|CommonStates|<xref:System.Windows.Controls.ProgressBar> 基于 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 属性报告进度。|  
|尚|CommonStates|<xref:System.Windows.Controls.ProgressBar> 使用重复模式报告一般进度。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="progressbar-controltemplate-example"></a>ProgressBar System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.ProgressBar> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
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
