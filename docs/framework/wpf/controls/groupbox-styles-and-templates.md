---
title: GroupBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187480"
---
# <a name="groupbox-styles-and-templates"></a>GroupBox 样式和模板
<a name="introduction"></a>本主题介绍控件的<xref:System.Windows.Controls.GroupBox>样式和模板。 您可以修改默认值<xref:System.Windows.Controls.ControlTemplate>，为控件提供唯一的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a>组盒零件  
 该<xref:System.Windows.Controls.GroupBox>控件没有任何命名部件。  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a>组盒状态  
 下表列出了控件的<xref:System.Windows.Controls.GroupBox>可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|说明|  
|-|-|-|  
|有效|ValidationStates|控件使用 类<xref:System.Windows.Controls.Validation>，<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性为`false`。|  
|InvalidFocused|ValidationStates|附加<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>属性具有`true`控件具有焦点。|  
|InvalidUnfocused|ValidationStates|附加<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>属性是`true`具有控件没有焦点。|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a>组盒控制模板示例  
 下面的示例演示如何为<xref:System.Windows.Controls.ControlTemplate><xref:System.Windows.Controls.GroupBox>控件定义 。  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 使用<xref:System.Windows.Controls.ControlTemplate>以下一个或多个资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [控件样式和模板](control-styles-and-templates.md)
- [控件自定义](control-customization.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [为控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)
