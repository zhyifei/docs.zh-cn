---
title: RelativeSource MarkupExtension
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 6301299da966ade9b5cc7ccd105c8269a486744e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646227"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="bfb88-102">RelativeSource MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="bfb88-102">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="bfb88-103">指定<xref:System.Windows.Data.RelativeSource>绑定源的属性，用于[绑定标记扩展](binding-markup-extension.md)中，或在设置 XAML 中建立<xref:System.Windows.Data.Binding.RelativeSource%2A><xref:System.Windows.Data.Binding>的元素的属性时。</span><span class="sxs-lookup"><span data-stu-id="bfb88-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="bfb88-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="bfb88-104">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="bfb88-105">XAML 属性用法（嵌套在 Binding 扩展内）</span><span class="sxs-lookup"><span data-stu-id="bfb88-105">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="bfb88-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="bfb88-106">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="bfb88-107">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="bfb88-107">-or-</span></span>

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

## <a name="xaml-values"></a><span data-ttu-id="bfb88-108">XAML 值</span><span class="sxs-lookup"><span data-stu-id="bfb88-108">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="bfb88-109">下列类型作之一：</span><span class="sxs-lookup"><span data-stu-id="bfb88-109">One of the following:</span></span><br /><br /> <span data-ttu-id="bfb88-110">- 字符串令牌`Self`;对应于<xref:System.Windows.Data.RelativeSource>为其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.Self>的 创建的 as</span><span class="sxs-lookup"><span data-stu-id="bfb88-110">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="bfb88-111">- 字符串令牌`TemplatedParent`;对应于<xref:System.Windows.Data.RelativeSource>为其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>的 创建的 as</span><span class="sxs-lookup"><span data-stu-id="bfb88-111">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="bfb88-112">- 字符串令牌`PreviousData`;对应于<xref:System.Windows.Data.RelativeSource>为其<xref:System.Windows.Data.RelativeSource.Mode%2A>属性设置为<xref:System.Windows.Data.RelativeSourceMode.PreviousData>的 创建的 as</span><span class="sxs-lookup"><span data-stu-id="bfb88-112">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="bfb88-113">- 有关模式的信息，`FindAncestor`请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="bfb88-113">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="bfb88-114">字符串标记 `FindAncestor`。</span><span class="sxs-lookup"><span data-stu-id="bfb88-114">The string token `FindAncestor`.</span></span> <span data-ttu-id="bfb88-115">使用此标记可输入一个模式，以便 `RelativeSource` 指定上级类型和可选的上级级别。</span><span class="sxs-lookup"><span data-stu-id="bfb88-115">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="bfb88-116">它对应于通过将 <xref:System.Windows.Data.RelativeSource> 属性设置为 <xref:System.Windows.Data.RelativeSource.Mode%2A> 而创建的 <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>。</span><span class="sxs-lookup"><span data-stu-id="bfb88-116">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="bfb88-117">对于 `FindAncestor` 模式是必需的。</span><span class="sxs-lookup"><span data-stu-id="bfb88-117">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="bfb88-118">类型的名称，用于填充 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="bfb88-118">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="bfb88-119">对于 `FindAncestor` 模式是可选的。</span><span class="sxs-lookup"><span data-stu-id="bfb88-119">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="bfb88-120">上级级别（在逻辑树中向父级方向计算）。</span><span class="sxs-lookup"><span data-stu-id="bfb88-120">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="bfb88-121">备注</span><span class="sxs-lookup"><span data-stu-id="bfb88-121">Remarks</span></span>

<span data-ttu-id="bfb88-122">`{RelativeSource TemplatedParent}`绑定用法是一种关键技术，它解决了控件的 UI 和控件逻辑分离的较大概念。</span><span class="sxs-lookup"><span data-stu-id="bfb88-122">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="bfb88-123">这可以实现从模板定义内绑定到模板化父级（在其中应用模板的运行时对象实例）。</span><span class="sxs-lookup"><span data-stu-id="bfb88-123">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="bfb88-124">在这种情况下，[模板绑定标记扩展](templatebinding-markup-extension.md)实际上是以下绑定表达式的缩写： `{Binding RelativeSource={RelativeSource TemplatedParent}}`。</span><span class="sxs-lookup"><span data-stu-id="bfb88-124">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="bfb88-125">`TemplateBinding`或`{RelativeSource TemplatedParent}`用法都只与定义模板的 XAML 中相关。</span><span class="sxs-lookup"><span data-stu-id="bfb88-125">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="bfb88-126">有关详细信息，请参阅[模板绑定标记扩展](templatebinding-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb88-126">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="bfb88-127">`{RelativeSource FindAncestor}`主要用于控件模板或可预测的自包含 UI 组合，用于始终预期控件位于特定祖先类型的可视树中的情况。</span><span class="sxs-lookup"><span data-stu-id="bfb88-127">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="bfb88-128">例如，项控件的项可能使用 `FindAncestor` 用法绑定到其项控件父级/祖先级。</span><span class="sxs-lookup"><span data-stu-id="bfb88-128">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="bfb88-129">或者，属于模板中控件组合一部分的元素可使用 `FindAncestor` 绑定到同一组合结构中的父元素。</span><span class="sxs-lookup"><span data-stu-id="bfb88-129">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="bfb88-130">在 XAML 语法章节显示的 `FindAncestor` 模式的对象元素语法中，第二个对象元素语法专门用于 `FindAncestor` 模式。</span><span class="sxs-lookup"><span data-stu-id="bfb88-130">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="bfb88-131">`FindAncestor` 模式需要 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="bfb88-131">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="bfb88-132">您必须<xref:System.Windows.Data.RelativeSource.AncestorType%2A>使用[x：Type 标记扩展](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)引用设置为要查找的祖先类型的属性。</span><span class="sxs-lookup"><span data-stu-id="bfb88-132">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="bfb88-133">当在运行时处理绑定请求时，将会用到 <xref:System.Windows.Data.RelativeSource.AncestorType%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="bfb88-133">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="bfb88-134">对于 `FindAncestor` 模式，当元素树中可能存在多个该类型的上级时，可以使用可选属性 <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> 帮助消除上级查找的歧义。</span><span class="sxs-lookup"><span data-stu-id="bfb88-134">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="bfb88-135">有关如何使用 `FindAncestor` 模式的详细信息，请参阅 <xref:System.Windows.Data.RelativeSource>。</span><span class="sxs-lookup"><span data-stu-id="bfb88-135">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="bfb88-136">`{RelativeSource Self}`实例的一个属性应依赖于同一实例的另一个属性的值，并且这两个属性之间不存在常规依赖项属性关系（如强制），则非常有用。</span><span class="sxs-lookup"><span data-stu-id="bfb88-136">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="bfb88-137">尽管在对象上存在两个属性，使值完全相同（并且类型相同）的情况很少见，但也可以将参数`Converter`应用于具有`{RelativeSource Self}`的绑定，并使用转换器在源类型和目标类型之间转换。</span><span class="sxs-lookup"><span data-stu-id="bfb88-137">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="bfb88-138">的另`{RelativeSource Self}`一个方案是作为 的<xref:System.Windows.MultiDataTrigger>一部分。</span><span class="sxs-lookup"><span data-stu-id="bfb88-138">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="bfb88-139">例如，以下 XAML 定义了一个 <xref:System.Windows.Shapes.Rectangle> 元素，以便无论为 <xref:System.Windows.FrameworkElement.Width%2A> 输入什么值，都确保 <xref:System.Windows.Shapes.Rectangle> 始终是一个方形：`<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="bfb88-139">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="bfb88-140">`{RelativeSource PreviousData}`在数据模板中，或者在绑定使用集合作为数据源的情况下非常有用。</span><span class="sxs-lookup"><span data-stu-id="bfb88-140">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="bfb88-141">可以使用`{RelativeSource PreviousData}`突出显示集合中相邻数据项之间的关系。</span><span class="sxs-lookup"><span data-stu-id="bfb88-141">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="bfb88-142">相关技术是在数据源中的当前项和前一个项之间建立 <xref:System.Windows.Data.MultiBinding>，并使用此绑定上的转换器来确定这两个项及其属性的差异。</span><span class="sxs-lookup"><span data-stu-id="bfb88-142">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="bfb88-143">在下面的示例中，项目模板中的第一个 <xref:System.Windows.Controls.TextBlock> 可显示当前编号。</span><span class="sxs-lookup"><span data-stu-id="bfb88-143">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="bfb88-144">第二<xref:System.Windows.Controls.TextBlock>个绑定是<xref:System.Windows.Data.MultiBinding>名义上有两<xref:System.Windows.Data.Binding>个成分的绑定：当前记录和使用 故意使用`{RelativeSource PreviousData}`以前的数据记录的绑定。</span><span class="sxs-lookup"><span data-stu-id="bfb88-144">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="bfb88-145">然后，<xref:System.Windows.Data.MultiBinding> 上的转换器将计算差异，并将其返回到绑定。</span><span class="sxs-lookup"><span data-stu-id="bfb88-145">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

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

<span data-ttu-id="bfb88-146">此处不介绍将数据绑定描述为概念，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb88-146">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="bfb88-147">在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XAML 处理器实现中，此标记扩展的处理由<xref:System.Windows.Data.RelativeSource>类定义。</span><span class="sxs-lookup"><span data-stu-id="bfb88-147">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="bfb88-148">`RelativeSource` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="bfb88-148">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="bfb88-149">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="bfb88-149">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="bfb88-150">XAML 中的所有标记扩展在其属性语法中使用`{``}`和 字符，这是 XAML 处理器识别标记扩展必须处理该属性的约定。</span><span class="sxs-lookup"><span data-stu-id="bfb88-150">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="bfb88-151">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb88-151">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bfb88-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfb88-152">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="bfb88-153">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="bfb88-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="bfb88-154">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="bfb88-154">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="bfb88-155">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="bfb88-155">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="bfb88-156">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="bfb88-156">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="bfb88-157">绑定声明概述</span><span class="sxs-lookup"><span data-stu-id="bfb88-157">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="bfb88-158">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="bfb88-158">x:Type Markup Extension</span></span>](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
