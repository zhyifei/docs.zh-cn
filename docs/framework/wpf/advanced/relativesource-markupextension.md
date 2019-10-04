---
title: RelativeSource MarkupExtension
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 7a9c9fe379f361dec0d65b71c4d883958be9ed2f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834821"
---
# <a name="relativesource-markupextension"></a>RelativeSource MarkupExtension

指定要在[绑定标记扩展](binding-markup-extension.md)中使用的 @no__t 0 绑定源的属性，或设置在 XAML 中建立的 <xref:System.Windows.Data.Binding> 元素的 @no__t 属性。

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
```

-或-

```xml
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
|`modeEnumValue`|以下项之一：<br /><br /> -字符串标记 `Self`;对应于创建的 <xref:System.Windows.Data.RelativeSource>，其 @no__t 属性设置为 <xref:System.Windows.Data.RelativeSourceMode.Self>。<br />-字符串标记 `TemplatedParent`;对应于创建的 <xref:System.Windows.Data.RelativeSource>，其 @no__t 属性设置为 <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>。<br />-字符串标记 `PreviousData`;对应于创建的 <xref:System.Windows.Data.RelativeSource>，其 @no__t 属性设置为 <xref:System.Windows.Data.RelativeSourceMode.PreviousData>。<br />-有关 @no__t 模式的信息，请参阅下文。|
|`FindAncestor`|字符串标记 `FindAncestor`。 使用此标记可输入一个模式，以便 `RelativeSource` 指定上级类型和可选的上级级别。 它对应于通过将 <xref:System.Windows.Data.RelativeSource> 属性设置为 <xref:System.Windows.Data.RelativeSource.Mode%2A> 而创建的 <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>。|
|`typeName`|对于 `FindAncestor` 模式是必需的。 类型的名称，用于填充 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 属性。|
|`intLevel`|对于 `FindAncestor` 模式是可选的。 上级级别（在逻辑树中向父级方向计算）。|

## <a name="remarks"></a>备注

`{RelativeSource TemplatedParent}` 绑定用法是一项关键技术，可解决控件的 UI 和控件的逻辑的更大分离。 这可以实现从模板定义内绑定到模板化父级（在其中应用模板的运行时对象实例）。 对于这种情况， [TemplateBinding 标记扩展](templatebinding-markup-extension.md)实际上是以下绑定表达式的简写形式： `{Binding RelativeSource={RelativeSource TemplatedParent}}`。 `TemplateBinding` 或 `{RelativeSource TemplatedParent}` 用法都仅在定义模板的 XAML 中相关。 有关详细信息，请参阅[TemplateBinding 标记扩展](templatebinding-markup-extension.md)。

`{RelativeSource FindAncestor}` 主要用于控件模板或可预测的自包含 UI 组合，适用于控件始终应位于特定上级类型的可视化树中的情况。 例如，项控件的项可能使用 `FindAncestor` 用法绑定到其项控件父级/祖先级。 或者，属于模板中控件组合一部分的元素可使用 `FindAncestor` 绑定到同一组合结构中的父元素。

在 XAML 语法章节显示的 `FindAncestor` 模式的对象元素语法中，第二个对象元素语法专门用于 `FindAncestor` 模式。 `FindAncestor` 模式需要 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 值。 必须将 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 设置为一个属性，该属性使用对要查找的上级类型的[X:Type 标记扩展](../../xaml-services/x-type-markup-extension.md)引用。 当在运行时处理绑定请求时，将会用到 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 值。

对于 `FindAncestor` 模式，当元素树中可能存在多个该类型的上级时，可以使用可选属性 <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> 帮助消除上级查找的歧义。

有关如何使用 `FindAncestor` 模式的详细信息，请参阅 <xref:System.Windows.Data.RelativeSource>。

如果实例的一个属性应依赖于同一个实例的另一个属性的值，并且这两个属性之间已存在常规依赖关系属性关系（如强制），则 @no__t 为0。 尽管对象很少存在两个属性，以便这些值按原义相同（并且类型相同），但也可以将 @no__t 0 参数应用到 @no__t 为1的绑定，并使用转换器在源和目标类型之间进行转换。 @No__t 的另一种情况是 @no__t 的一部分。

例如，以下 XAML 定义了一个 <xref:System.Windows.Shapes.Rectangle> 元素，以便无论为 <xref:System.Windows.FrameworkElement.Width%2A> 输入什么值，都确保 <xref:System.Windows.Shapes.Rectangle> 始终是一个方形：`<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

@no__t 在数据模板中，或在绑定使用集合作为数据源的情况下，。 您可以使用 `{RelativeSource PreviousData}` 来突出显示集合中相邻数据项之间的关系。 相关技术是在数据源中的当前项和前一个项之间建立 <xref:System.Windows.Data.MultiBinding>，并使用此绑定上的转换器来确定这两个项及其属性的差异。

在下面的示例中，项目模板中的第一个 <xref:System.Windows.Controls.TextBlock> 可显示当前编号。 第二个 <xref:System.Windows.Controls.TextBlock> 绑定是一个 <xref:System.Windows.Data.MultiBinding>，通常具有两个 <xref:System.Windows.Data.Binding> 要素：当前记录和通过使用 @no__t 有意使用以前数据记录的绑定。 然后，<xref:System.Windows.Data.MultiBinding> 上的转换器将计算差异，并将其返回到绑定。

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

此处未介绍如何将数据绑定描述为概念，请参阅[数据绑定概述](../data/data-binding-overview.md)。

在 @no__t 的 XAML 处理器实现中，对此标记扩展的处理由 @no__t 1 类定义。

`RelativeSource` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 XAML 中的所有标记扩展在其特性语法中使用 `{` 和 `}` 字符，这是 XAML 处理器识别标记扩展必须处理特性的约定。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.Binding>
- [样式设置和模板化](../controls/styling-and-templating.md)
- [XAML 概述 (WPF)](xaml-overview-wpf.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [数据绑定概述](../data/data-binding-overview.md)
- [绑定声明概述](../data/binding-declarations-overview.md)
- [x:Type 标记扩展](../../xaml-services/x-type-markup-extension.md)
