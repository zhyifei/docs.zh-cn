---
title: RelativeSource MarkupExtension
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ea5d269c3d455a4fbe3a34dca4335e0d8999d80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="relativesource-markupextension"></a>RelativeSource MarkupExtension
指定属性<xref:System.Windows.Data.RelativeSource>绑定源，要在中使用[绑定标记扩展](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)，或在设置时<xref:System.Windows.Data.Binding.RelativeSource%2A>属性<xref:System.Windows.Data.Binding>建立在 XAML 中的元素。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xml  
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>  
```  
  
## <a name="xaml-attribute-usage-nested-within-binding-extension"></a>XAML 属性用法（嵌套在 Binding 扩展内）  
  
```xml  
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 对象元素用法  
  
```xml  
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource Mode="modeEnumValue"/>  
  </Binding.RelativeSource>  
</Binding>  
- or   
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource  
      Mode="FindAncestor"  
      AncestorType="{x:Type typeName}"  
      AncestorLevel="intLevel"  
    />  
  </Binding.RelativeSource>  
</Binding>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`modeEnumValue`|以下项之一：<br /><br /> -的字符串标记`Self`; 对应于<xref:System.Windows.Data.RelativeSource>与创建其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.Self>。<br />-的字符串标记`TemplatedParent`; 对应于<xref:System.Windows.Data.RelativeSource>与创建其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>。<br />-的字符串标记`PreviousData`; 对应于<xref:System.Windows.Data.RelativeSource>与创建其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.PreviousData>。<br />-请参阅下面有关信息有关`FindAncestor`模式。|  
|`FindAncestor`|字符串标记 `FindAncestor`。 使用此标记可输入一个模式，以便 `RelativeSource` 指定上级类型和可选的上级级别。 它对应于通过将 <xref:System.Windows.Data.RelativeSource> 属性设置为 <xref:System.Windows.Data.RelativeSource.Mode%2A> 而创建的 <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>。|  
|`typeName`|对于 `FindAncestor` 模式是必需的。 类型的名称，用于填充 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 属性。|  
|`intLevel`|对于 `FindAncestor` 模式是可选的。 上级级别（在逻辑树中向父级方向计算）。|  
  
## <a name="remarks"></a>备注  
 `{RelativeSource TemplatedParent}`绑定用法是将控件的 UI 和控件的逻辑分一大概念的关键方法。 这可以实现从模板定义内绑定到模板化父级（在其中应用模板的运行时对象实例）。 这种情况下， [TemplateBinding 标记扩展](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)实际上是以下绑定表达式的一种速记： `{Binding RelativeSource={RelativeSource TemplatedParent}}`。 `TemplateBinding`或`{RelativeSource TemplatedParent}`用法都在 XAML 中定义的模板内仅相关。 有关详细信息，请参阅[TemplateBinding 标记扩展](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)  
  
 `{RelativeSource FindAncestor}`主要用于在控件模板或可预测自包含的用户界面组合，其中控件始终预计会在某一祖先类型的可视化树中的情况。 例如，项控件的项可能使用 `FindAncestor` 用法绑定到其项控件父级/祖先级。 或者，属于模板中控件组合一部分的元素可使用 `FindAncestor` 绑定到同一组合结构中的父元素。  
  
 在 XAML 语法章节显示的 `FindAncestor` 模式的对象元素语法中，第二个对象元素语法专门用于 `FindAncestor` 模式。 `FindAncestor` 模式需要 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 值。 必须设置<xref:System.Windows.Data.RelativeSource.AncestorType%2A>作为特性使用[X:type 标记扩展](../../../../docs/framework/xaml-services/x-type-markup-extension.md)到要查找的上级节点的类型的引用。 当在运行时处理绑定请求时，将会用到 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 值。  
  
 对于 `FindAncestor` 模式，当元素树中可能存在多个该类型的上级时，可以使用可选属性 <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> 帮助消除上级查找的歧义。  
  
 有关如何使用 `FindAncestor` 模式的详细信息，请参阅 <xref:System.Windows.Data.RelativeSource>。  
  
 `{RelativeSource Self}`对于方案很有用其中一个属性的实例应依赖于相同的实例，以及任何常规的依赖项属性关系 （如强制） 的另一个属性的值已存在这两个属性之间。 虽然很少见，以便值按原义相同 （和相同类型化） 对象上存在两个属性，你还可以应用`Converter`已绑定到参数`{RelativeSource Self}`，并且使用转换器将转换源之间和目标类型。 另一方案`{RelativeSource Self}`作为的一部分是<xref:System.Windows.MultiDataTrigger>。  
  
 例如，以下 XAML 定义了一个 <xref:System.Windows.Shapes.Rectangle> 元素，以便无论为 <xref:System.Windows.FrameworkElement.Width%2A> 输入什么值，都确保 <xref:System.Windows.Shapes.Rectangle> 始终是一个方形：`<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`  
  
 `{RelativeSource PreviousData}`数据模板中或在其中，绑定将作为数据源使用集合的情况下很有用。 你可以使用`{RelativeSource PreviousData}`以突出显示相邻的数据集合中的项之间的关系。 相关技术是在数据源中的当前项和前一个项之间建立 <xref:System.Windows.Data.MultiBinding>，并使用此绑定上的转换器来确定这两个项及其属性的差异。  
  
 在下面的示例中，项目模板中的第一个 <xref:System.Windows.Controls.TextBlock> 可显示当前编号。 第二个<xref:System.Windows.Controls.TextBlock>绑定是<xref:System.Windows.Data.MultiBinding>，名义上有两个<xref:System.Windows.Data.Binding>要素： 当前记录，并有意通过使用以前的数据记录的绑定`{RelativeSource PreviousData}`。 然后，<xref:System.Windows.Data.MultiBinding> 上的转换器将计算差异，并将其返回到绑定。  
  
```xml  
<ListBox Name="fibolist">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <StackPanel Orientation="Horizontal">  
            <TextBlock Text="{Binding}"/>  
            <TextBlock>, difference = </TextBlock>  
                <TextBlock>  
                    <TextBlock.Text>  
                        <MultiBinding Converter="{StaticResource DiffConverter}">  
                            <Binding/>  
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>  
                        </MultiBinding>  
                    </TextBlock.Text>  
                </TextBlock>  
            </StackPanel>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
```  
  
 描述数据绑定，如概念未涵盖在这里，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XAML 处理器实现，对此标记扩展的处理定义的<xref:System.Windows.Data.RelativeSource>类。  
  
 `RelativeSource` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 XAML 使用中的所有标记扩展`{`和`}`其属性的语法，这是 XAML 处理器识别标记扩展必须处理该特性所依据的约定中的字符。 有关详细信息，请参阅[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.Binding>  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [绑定声明概述](../../../../docs/framework/wpf/data/binding-declarations-overview.md)  
 [x:Type 标记扩展](../../../../docs/framework/xaml-services/x-type-markup-extension.md)
