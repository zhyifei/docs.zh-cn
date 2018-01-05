---
title: "ProgressBar 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6809ce2f51af8a1baf535afa8fe80f4e5b5f53e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-styles-and-templates"></a>ProgressBar 样式和模板
本主题介绍的样式和模板的<xref:System.Windows.Controls.ProgressBar>控件。 你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。 有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
## <a name="progressbar-parts"></a>ProgressBar 部件  
 下表列出的命名的部件<xref:System.Windows.Controls.ProgressBar>控件。  
  
|部件|类型|描述|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|一个对象，它指示进度。|  
|PART_Track|<xref:System.Windows.FrameworkElement>|定义进度指示器的路径的对象。|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|一个对象，修饰进度栏。|  
  
## <a name="progressbar-states"></a>进度栏状态  
 下表列出的可视状态<xref:System.Windows.Controls.ProgressBar>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|确定|CommonStates|<xref:System.Windows.Controls.ProgressBar>报告进度基于<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>属性。|  
|不确定|CommonStates|<xref:System.Windows.Controls.ProgressBar>报告使用重复的模式的泛型进度。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="progressbar-controltemplate-example"></a>ProgressBar ControlTemplate 示例  
 下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ProgressBar>控件。  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 上一示例使用了一个或多个以下资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [控件样式和模板](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [控件自定义](../../../../docs/framework/wpf/controls/control-customization.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
